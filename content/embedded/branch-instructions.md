---
title: branch-instructions
date: 2022-01-01
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

# Branch instructions
* `B.N` (Branch) instruction modifies the [`PC` register](embedded/registers-memory.md#program-counter-pc) so that it skips to a different instruction
* `BLT.N` conditional branching
	* only modifies `PC` if the `N` bit in the `APSR` is set.
	* the instruction to jump to is encoded within the instruction itself: `0xFC = -4`, so jump back 4 instructions, from `0x8e` to `0x8a`
* Branching results in [pipeline delays](embedded/nonlinear-control-flow.md) --> solution e.g. loop unrolling

## BL (branch and link)
* `BL` saves the address of the next instruction into the [`LR` link register](embedded/registers-memory.md#link-register-lr).
	* The previous value of `LR` (i.e. previous function return address) must also be saved somehow.
	* The previous return address is saved to the [stack](embedded/stack.md).
* Example of a main function executing (branching off into) the `delay` subfunction:  
	```
	int main(){
		GPIO_PORTF_DATA_BITS_R[LED_RED] = LED_RED;
		delay();	
		GPIO_PORTF_DATA_BITS_R[LED_RED] = 0;
	}
	```

|                  | Disassembly                                | Register                             |
| ---------------- | ------------------------------------------ | ------------------------------------ |
| Before `BL`      | ![](/embedded/_img/bl-disassembly.png)     | ![](/embedded/_img/bl-lr-before.png) |
| After `BL`       | ![](/embedded/_img/bl-step-into-delay.png) | ![](/embedded/_img/bl-lr-after.png)  |

**Notes**:
* After branching off into the subfunction `delay`, the [stack](embedded/stack.md) is expanded by 4 memory units, as can be seen in the `SUB SP, SP, #0X4` instruction.  
	```
	0xF0 - 0x4 = 0xEC
	```
* At the end of `delay()`, the reverse occurs. The stack is shrunk by 4 memory units: `ADD SP, SP, #0X4` and points to `0xF0` again, just like before `delay()` was executed.
* The return of the `delay()` function is given by the [`BX` branch instruction](#bx-branch-and-exchange).
* It would be expected that, right after `BL`, `LR` stores the instruction address `0x94`, but instead `0x95` is stored.
	* This is also at odds with the fact that the ARM instructions must be aligned at even addresses.
	* This is a legacy behaviour explained in the [`BX` section](#bx-branch-and-exchange).
	* At the end of the subfunction (after executing `BX`), the `PC` register is indeed updated to the correct instruction `0x94`.

## BX (branch and exchange)
* Performed upon return of a function.
* Sets `PC` to the value of `LR`.
	* However, not all bits of `LR` are transferred to `PC`.
	* The least significant bit of `PC` is always set to zero, as the return address must be even.
	* Therefore, the least significant bit of `LR` is not used for addressing.
	* Instead, it is used as the instruction set exchange bit.
		* If 1: processor switches to the THUMB instruction set.
		* If 0: processor switches to the ARM instruction set.
	* This behavour, however, moot in Cortex-M (no possibility to switch to ARM instructions), and is therefore just a legacy behaviour.	