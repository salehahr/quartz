---
title: simple-program
date: 2021-12-30
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

```
int main() {
	int counter = 0;
	++counter;
	++counter;
	return 0;
}
```

## Machine code
![](/embedded/_img/disassembly-simple.png)

## Instructions

| Code              | Instruction       | Description                                |
| ----------------- | ----------------- | ------------------------------------------ |
| `int counter = 0` | `MOVS R0, #0`     | Move value 0 to register R0                |
| `++counter;`      | `ADDS R0, R0, #1` | Add value 1 to register R0, store it in R0 |

## Registers and memory

| Register                                 | Memory                                   |
| ---------------------------------------- | ---------------------------------------- |
| ![](/embedded/_img/register-simple.png) | ![](/embedded/_img/memory-simple.png) |
