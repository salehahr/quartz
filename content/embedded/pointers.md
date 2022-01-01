---
title: pointers
date: 2021-12-30
tags:
  - programming/c
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

# Pointers
* Variables which hold memory addresses.
* Can also be viewed as [arrays](embedded/arrays-in-c.md).

## Declaration
```
int *p_int;
```

## Assignment
Address/pointer assignment
```
p_int = &another_variable;
p_int = (unsigned int *)0x20000000U;
```

## Dereferencing
Value assignment
```
*p_int = 0xDEADBEEFU;
```

## Shortcut
Skips declaration, goes directly to value assignment.
```
*((unsigned int *)0x20000000U) = 0xDEADBEEFU;
```