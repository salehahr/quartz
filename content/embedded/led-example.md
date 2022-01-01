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
* To use the LEDs, the values of the GPIO port F need to be set --> address of GPIO PF needed.

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

## Memory map
![](/embedded/_img/tm4c123g-memory-map-gpio.png)  
![](/embedded/_img/tm4c123g-memory-map-gpio-ahb.png)

The two different address ranges are because the GPIO are connected to two different peripheral [busses](bus.md):
* the APB (advanced peripheral bus) --default, but older and slower
* the AHB (advanced high-performance bus) -- newer, faster

![](/embedded/_img/tiva-apb-ahb.png)

Initially, the Port F address range contains no data due to [clock gating](embedded/clock-gating.md).
* `RCGCGPIO` (Register for Clock Gating Control of GPIO) must be set to enabled for the GPIO module to be activated
	* The GPIO module gets a clock signal
	* Access to the GPIO module registers are allowed
* From the datasheet:
	> Note that each GPIO module clock must be enabled before the registers can be programmed.
	> 
	> There must be a delay of 3 system clocks after the GPIO module clock is enabled before any GPIO module registers are accessed.

## Remove clock gating
![](/embedded/_img/RCGCGPIO.png)  
![](/embedded/_img/clock-gating-port-f.png)
* The register address is the base + offset:  
	0x400F'E000 + 0x608 = 0x400F'E608
* This register contains 32 bits = 4 bytes of data = 2 hex words
* Set the fifth bit to wake up Port F:  
	```
	unsigned int *RCGCGPIO = (unsigned int *)0x400FE608U;	
	*RCGCGPIO |= (1U << 5);
	```
* Now clock gating is removed for GPIO Port F
* But the GPIO-F bits still need to be configured as digital outputs

## Switch to AHB
Use `GPIOHBCTL` (GPIO High-Performance Bus Control) and set the corresponding bit for Port F (5th bit).

```
unsigned int *GPIOHBCTL = (unsigned int *)0x400FE06CU;
*GPIOHBCTL |= (1U << 5);
```

## Configuring GPIO-F
### Set pins as outputs
* Use `GPIODIR` (GPIO direction) with offset `0x400`.
* Setting a bit in `GPIODIR` sets the corresponding pin to be an output.  
	![](/embedded/_img/tiva-gpio-dir.png)
* Perform [bit setting](embedded/bit-logic.md) for all LEDs
	```
	unsigned int *GPIODIR = (unsigned int *)0x4005D400U;
	*GPIODIR |= ALL_LEDS;
	```
	
### Set pins to be digital outputs
* Default is tristate --> need to change to digital.
* Use `GPIODEN` (GPIO digital enable) with offset `0x51C`
* Perform bit setting for all LEDs
	```
	unsigned int *GPIODEN = (unsigned int *)0x4005D51CU;
	*GPIODEN |= ALL_LEDS;
	```
## Setting the LED pins
### Read-modify-write
Use `GPIO_PORTF_AHB_DATA_R` from the header file, which is defined to be
```
#define GPIO_PORTF_AHB_DATA_R (*((volatile unsigned long *)0x4005D3FC))
```

Hex `0x3FC` corresponds to $1111'1111'00_{2}$, which, using [bit masking](#bit-masking), corresponds to 'opening' up all the Port F pins for modification, i.e. setting all eight bits to be writable.

Initialising the blue light to be on:
```
GPIO_PORTF_AHB_DATA_R = LED_BLUE;
```

Bit setting of a different LED without affecting the other bits (here: without changing the state of the blue LED):
```
GPIO_PORTF_AHB_DATA_R |= LED_RED; 	// red on
GPIO_PORTF_AHB_DATA_R &= ~LED_RED; 	// red off
```

In the above, assembly carries out a read-modify-write sequence:  
`LDR` -> (`ORR.W`, etc.) -> `STR`  
* This sequence is necessary because the GPIO pins data are stored within a single byte, hence, at a single memory address.
* What would be better: separate access of each bit at its own unique address
	* Single atomic write operation to this unique address.
	* True independent bit manipulation.
	* In [interrupt routines](embedded/interrupts.md), GPIO bits may be modified.
		* If a read-modify-write cycle for GPIO bit setting is used, and the ISR happens after the read and before the modify, the changes made by the ISR will be discarded.
		* This behaviour may not be desired, hence the read-modify-write cycle is often replaced with the single write operation
	* --> Bit masking

### Bit masking
* Uses the bits of the address bus as a mask.
* Allows modifications of individual GPIO pins without affecting the others, in a single instruction.
* Is [interrupt](embedded/interrupts.md)-safe.

![](/embedded/_img/bit-masking-bus.png)

* GPIO bits are connected to CPU by a bus (address lines + data lines)
* Each GPIO bit is connected to its down
	* data line
	* address line
* The first two bits of the address line are unused, as the hardware requires all addresses to be divisible by four.
* Each bit combination has its own address -- therefore, this hardware design requires many registers with unique addresses. 
* The GPIO bit can only be modified when the corresponding address line has been set, regardless of the value of the data line.

In this example, there are 256 x 32-bit `DATA` registers for GPIO Port F.

#### Address arithmetic
e.g. for the red LED
```
/*calculate the address*/
LED_RED = 1U << 1;
GPIO_PORTF_BASE = 0x40005D00U;

LED_RED_ADDRESS = GPIO_PORTF_BASE + (LED_RED << 2)

/*assign the value*/
unsigned long volatile *p_LED_RED = (unsigned long volatile *)LED_RED_ADDRESS;
*p_LED_RED = LED_RED;
```

**Note**: the 2 bit shifts are to skip the unused address lines

#### Pointer arithmetic, or array indexing
Alternatively, [array indexing](embedded/arrays-in-c.md#address-arithmetic-vs-pointer-arithmetic) of the defined macro `GPIO_PORTF_AHB_DATA_BITS_R` can be used.
```
GPIO_PORTF_AHB_DATA_BITS_R[LED_RED] = LED_RED;
```

## Final code
```
#include "lm4f120h5qr.h"
#include "delay.h"

#define PORT_F 		(1U << 5);

#define LED_RED 	(1U << 1)
#define LED_BLUE 	(1U << 2)
#define LED_GREEN	(1U << 3)
#define ALL_LEDS	(LED_RED | LED_BLUE | LED_GREEN)

int main(){
	SYSCTL_RCGCGPIO_R |= PORT_F;	// enable clock
	SYSCTL_GPIOHBCTL_R |= PORT_F; 	// enable AHB
	
	// set LED GPIO to digital outputs
	GPIO_PORTF_AHB_DIR_R |= ALL_LEDS;
	GPIO_PORTF_AHB_DEN_R |= ALL_LEDS;
	
	// set blue LED to on
	GPIO_PORTF_AHB_DATA_BITS_R[LED_BLUE] = LED_BLUE;
	
	while(1){
		GPIO_PORTF_AHB_DATA_BITS_R[LED_RED] = LED_RED;
		delay();
		
		GPIO_PORTF_AHB_DATA_BITS_R[LED_RED] = 0;
		delay();		
	}
	
	return 0;
}
```