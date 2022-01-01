---
title: stack
date: 2022-01-01
tags:
  - -definitions
  - programming/c
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

# Stack
* Area of [RAM](embedded/registers-memory.md) that can grow or shrink from one end.
* Analogous to a stack of dishes: new data/dishes can only be added to the top, and data/dishes can only be taken away from the top.
* In [ARM](arm.md), the stack grows towards the lower addresses.
* Pointed to by the [stack pointer](embedded/registers-memory.md).
* Initial values of the stack are random, therefore it is important, in function calls, to initialise variables correctly.
* Possible corruption of the stack: unintended modification of a previous return address, thus making the program unable to go back to the correct caller function.

## Functions
* Stores the return address of the caller function.
* Holds local variables of the current function being executed.

## Stack overflow
Stack grows out of bounds (out of the valid RAM allocation) / out of memory.