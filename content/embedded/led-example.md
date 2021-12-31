---
title: led-example
date: 2021-12-31
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

# TM4C123G LED Example
## LED connection
![](/embedded/_img/tiva-led-schematic.png)

* The LEDs are connected to the GPIO port F pins of the microcontroller.
* To use the LEDs, the value of the GPIO port F need to be set --> address of GPIO PF needed.

## Memory map
![](/embedded/_img/tm4c123g-memory-map-gpio.png)

* Initially, this address range contains no data due to [clock gating](embedded/clock-gating.md).
* `RCGCGPIO` (Register for Clock Gating Control of GPIO) must be set to enabled for the GPIO module to be activated
	* The GPIO module gets a clock signal
	* Access to the GPIO module registers are allowed
* From the datasheet:
	> Note that each GPIO module clock must be enabled before the registers can be programmed.
	> 
	> There must be a delay of 3 system clocks after the GPIO module clock is enabled before any GPIO module registers are accessed.

## RCGCGPIO to remove clock gating
![](/embedded/_img/RCGCGPIO.png)  
![](/embedded/_img/clock-gating-port-f.png)
* The register address is the base + offset:  
	0x400F'E000 + 0x608 = 0x400F'E608
* The fifth bit (for waking up Port F) corresponds to:  
	$10000_{2} = 32_{10} = 20_{16} =$ 0x20
* Perform bit setting
	```
	unsigned int *RCGCGPIO = (unsigned int *)0x400FE608U;	
	*RCGCGPIO |= 0x20U;
	```
* Now clock gating is removed for GPIO Port F
* But the GPIO-F bits still need to be configured as digital outputs


## Bit-wise setting of the LED pins
| LED   | Pin number | Binary |   Hex |
| ----- |:----------:| ------:| -----:|
| Red   |     1      | `0010` | `0x2` |
| Blue  |     2      | `0100` | `0x4` |
| Green |     3      | `1000` | `0x8` |
| All   |  1, 2, 3   | `1110` | `0xE` |

Using [bit shift operations](embedded/bit-logic.md), the first, second and third bits can be defined as
```
#define LED_RED 	(1U << 1)
#define LED_BLUE 	(1U << 2)
#define LED_GREEN	(1U << 3)
```

This is a cleaner alternative to the hex values above.  

All the LEDs together would be
```
ALL_LEDS = LED_RED | LED_BLUE | LED_GREEN
```

## Configuring GPIO-F
### Set pins as output
* Use `GPIODIR` (GPIO direction) with offset `0x400`.
* Setting a bit in `GPIODIR` sets the corresponding pin to be an output.  
	![](/embedded/_img/tiva-gpio-dir.png)
* Perform [bit setting](embedded/bit-logic.md) for all LEDs
	```
	unsigned int *GPIODIR = (unsigned int *)0x40025400U;
	*GPIODIR |= ALL_LEDS;
	```
	
### Set pins to be digital outputs
* Default is tristate --> need to change to digital.
* Use `GPIODEN` (GPIO digital enable) with offset `0x51C`
* Perform bit setting for all LEDs
	```
	unsigned int *GPIODEN = (unsigned int *)0x4002551CU;
	*GPIODEN |= ALL_LEDS;
	```
## Setting the LED pins
Use `GPIO_PORTF_DATA_R` from the header file.

Initialising:
```
GPIO_PORTF_DATA_R = LED_BLUE;
```

Bit setting of a different LED without affecting the other bits (here: without changing the state of the blue LED):
```
GPIO_PORTF_DATA_R |= LED_RED; 	// red on
GPIO_PORTF_DATA_R &= ~LED_RED; 	// red off
```

In the above, assembly carries out a read-modify-write sequence:  
`LDR` -> (`ORR.W`, etc.) -> `STR`  
* This sequence is necessary because the GPIO pins data are stored within a single byte, hence, at a single memory address.
* What would be better: separate access of each bit at its own unique address
	* single atomic write operation to this unique address
	* true independent bit manipulation