---
title: preprocessor-macros
date: 2021-12-31
tags:
  - embedded
  - programming/c
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)


## Manual definition of macros
```
#define RCGCGPIO *((unsigned int *)0x400FE608U)

#define GPIOF_BASE 0x40025000u
#define GPIOF_DIR (*((unsigned int *)( GPIOF_BASE + 0x400U)))
#define GPIOF_DEN (*((unsigned int *)( GPIOF_BASE + 0x51CU)))

int main() {
	RCGCGPIO |= 0x20U;
	GPIODIR |= 0xEU;
	GPIOF_DEN |= 0xEU;
	...
}
```

**Notes**:
* Macros can also be partial statements
* Calculations within the macros don't lead to runtime overheads

## Header files
```
#include <stdint.h>
#include "lm4f120h5qr.h"

int main() {
	...
}
```