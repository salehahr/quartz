---
title: local-vs-nonlocal-variables
date: 2021-12-30
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

Local variables are stored in the [register](embedded/registers-memory.md), while non-local variables can be found in [memory](embedded/registers-memory.md).

## Local variable
```
int main()
{
	int counter = 0;
	...
}
```

**Note**:
* All local variables on the stack go out of scope (get located outside of stack when the stack shrinks) when the function returns, so they can't be accessed.
* Therefore, it is a bad idea to return a local variable.
	* Make use of [pointers](embedded/pointers.md) instead.
	* Alternatively, use the `static` keyword to tell the compuler to allocate memory to the variable *outside* of the stack.

## Non-local variable
```
int counter = 0; 
int main()
{
	...
}
```

### Instruction set
| Local                                   | Non-local                                |
| --------------------------------------- | ---------------------------------------- |
| ![](/embedded/_img/loop-disassembly.png) | ![](/embedded/_img/nonlocal-disassembly.png) |

* More instructions as the CPU needs to load data from memory (in [RISC](embedded/risc-cisc.md) architectures)
	* Loading from memory
		* `LDR.N R0, memory` (load to register from memory) -- loads the memory address
		* `LDR R0, [R0]` (load to register) -- loads the value located at the address
	* Storing to memory
		* `LDR.N R1, memory` -- loads the memory address onto R1
		* `STR R0, [R1]` (store) -- stores the value from register R0 into the memory at address [R1]