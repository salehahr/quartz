---
title: Arrays in C
date: 2022-01-01
tags:
  - programming/c
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

* Group of variables of the same type.
* The variables occupy consecutive memory locations.
* An array is treated as a [pointer](embedded/pointers.md) (to the beginning of the array). Likewise, every pointer can also be viewed as an array.

```
int counter[2] = {0, 0};

counter[0] = 1;
counter[1] = 2;
```

* Indexing the array is equivalent to adding the index to the array pointer and getting the value at that address.
* The value `counter[1]` is equivalent to `*(counter + 1)` (pointer arithmetic)

## Address arithmetic vs. pointer arithmetic
From the [LED example](embedded/led-example.md):
```
unsigned int LED_RED = (1U << 1);

// address arithmetic
*((unsigned int *)(BASE_ADDRESS + LED_RED_OFFSET)) = LED_RED;

// pointer arithmetic
*(DATA_BITS_R + LED_RED) = LED_RED;
DATA_BITS_R[LED_RED] = LED_RED;
```

In address arithmetic:
* address is calculated
* then cast to a pointer type
* the pointer value is set via the dereferenced pointer