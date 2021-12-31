---
title: program-with-loop
date: 2021-12-30
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)  
**See also**: [General considerations for non-linear control flow](embedded/nonlinear-control-flow.md)

## Code and instructions
### Code
```
int main()
{
  int counter = 0;
  
  while (counter < 10) {
  ++counter;
  }
  
  return 0;
}
```

### Disassembly
![](/embedded/_img/loop-disassembly.png)

### Comparison
| Original structure                       | Optimised structure                      |
| ---------------------------------------- | ---------------------------------------- |
| ![](embedded/_img/loop-original.png) | ![](embedded/_img/loop-optimised.png) |

* In the compiled code, the execution of the while loop is different than that given by the code.
* However, the effect of the loop on the calculation remains the same.
* The compiler proposes this order of instructions for increased efficiency, e.g. the `BLT.N`instruction steps back to `++counter` instead of forwards, which allows the `PC` register to naturally increment without having to use another branch instruction.


## Branching
* `B.N` (Branch) instruction modifies `PC` so that it skips to a different instruction
* `BLT.N` conditional branching
	* only modifies `PC` if the `N` bit in the `APSR` is set.
	* the instruction to jump to is encoded within the instruction itself: `0xFC = -4`, so jump back 4 instructions, from `0x8e` to `0x8a`
* Branching results in pipeline delays --> solution e.g. loop unrolling

## Compare
|        |                     |
| ------ | ------------------- |
| Before | ![](/embedded/_img/cmp-before.png) |
| After  | ![](/embedded/_img/cmp-after.png)  |


`CMP` modifies the `APSR` (Application Program Status Register)

`N` bit (negative) is set, because `R0 - #10` is negative

