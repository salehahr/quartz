---
title: integer-overflow
date: 2021-12-30
tags:
  - embedded
  - math/numbers
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

![](/embedded/_img/twos-complement.png)

## 8-bit representation
|    Hex |  Dec | Bin         |    Hex | Dec |         Bin |
| ------:| ----:| ----------- | ------:| ---:| -----------:|
| `0xFF` |   -1 | `1111 1111` | `0x01` |   1 | `0000 0001` |
| `0xFE` |   -2 | `1111 1110` | `0x02` |   2 | `0000 0010` |
| `0xFD` |   -3 | `1111 1101` | `0x03` |   3 | `0000 0011` |
|        |      |             |    ... |     |             |
| `0x81` | -127 | `1000 0001` | `0x7F` | 127 | `0111 1111` |
| `0x80` | -128 | `1000 0000` |        |     |             |

Getting the negative hex representation:
* For all bits except the least significant bit: subtract the bit from `F`
* For the least significant (rightmost) bit: subtract the bit from `F + 1`