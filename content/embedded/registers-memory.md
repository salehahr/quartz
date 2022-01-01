---
title: registers-memory
date: 2021-12-30
tags:
  - embedded
---

**See also:** [Local vs non-local variables](embedded/local-vs-nonlocal-variables.md)


| Register                                             | Memory                                                                                                                        |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Contains [local] data currently being processed      | Contains program instructions and data that the  whole program requires for execution (data that must survive function calls) |
| Small amount of data                                 | Larger amount of data                                                                                                         |
| Memory locations that are directly accessible by CPU | RAM (primary memory, internal to CPU) and hard drive (secondary memory, external to CPU)                                      |
| Faster access by CPU (one CPU clock cycle)           | Slower access by CPU                                                                                                          |

---
**Source**: [samek-embedded](bibliography/samek-embedded.md)

## Registers
Some special registers are described in the following.

### Program counter (PC)
* The `PC` (Program Counter) register holds the memory address of the current instruction to be executed.
* Every instruction increments `PC` as a side effect.

### Link register (LR)
* The `LR` link register remembers the place in the code to return to after a branch function completes
* Modified as a result of the [`BL` instruction](embedded/branch-instructions.md#bl-branch-and-link)

### Stack pointer (SP)
* Points to the top of the [stack](embedded/stack.md).

## Memory
RAM, [stack](embedded/stack.md), [heap](embedded/heap.md) etc.

### Visualisation of memory
![](embedded/_img/memory-vis.png)

Each address holds one unit of memory (a byte)

### Example: the RAM on TM4C123G
![](/embedded/_img/tm4c123g-memory-map-ram.png)
* RAM is located from the address 0x2000'0000 up to 0x2000'7FFFF
* The RAM contains $8000_{16} = 32768_{10}$ units of memory (bytes)  
	$$
	\begin{aligned}
		32 768 \text{~B}
	&= \frac{32 768}{2^{10}} \text{~KB}
		= \frac{32 768}{1024} \text{~KB}\\
	&= 32 \text{~KB or } 32 \text{~KiB}
	\end{aligned}
	$$