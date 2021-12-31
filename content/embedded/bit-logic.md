---
title: bit-logic
date: 2021-12-30
tags:
  - math/numbers
  - programming/c
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

| Logic                   | Description  | Notes                           |
|:----------------------- | ------------ | ------------------------------- |
| `(num & 1) != 0`        | Odd number   | Tests the least significant bit |
| `(num & 1) == 0`        | Even number  |                                 |
| <code>a &#124; b</code> | Bit-wise OR  |                                 |
| `a & b`                 | Bit-wise AND |                                 |
| `a ^ b`                 | Exclusive OR |                                 |
| `~b`                    | NOT          |                                 |


## Bit shift operations
### Unsigned
Uses logical bit shifting.  

Define an unsigned number:
```
u =  101 = 0x65 = 0b0110'0101
```

#### Right shift (unsigned)
Corresponds to integer division by $2^n$
```
c = u >> 1
c = 0b0011'0010 = 50
```

In assembly: `LSRS` shifts zeroes into the most significant bit positions.

#### Left shift (unsigned)
Corresponds to multiplication by $2^n$, but taking into account the most significant bits that 'fall off the edge'.
```
c = u << 1
c = 0b1100'1010 = 202
```
```
c = u << 3
c = 0b0010'1000 = 40
```

In assembly: `LSLS` shifts zeroes into the least significant bit positions.

### Signed
Define an unsigned and a signed number:
```
u =  101 = 0x65 = 0b0110'0101
s = -101 = 0x9B = 0b1001'1011
```

#### Right shift (signed)
Corresponds to division by $2^n$, rounded up if negative, rounded down in positive.
```
c = u >> 3
c = 0b0000'1100 = 12 = floor(101 / 8)
```

```
c = s >> 3
c = 0b1111'0011 = 243 = -13 = - ceil(101 / 8)
```

In assembly: `ASRS` (arithmetic right shift) shifts zeroes or ones into the most significant bit positions,  depending on most significant bit. This preserves the sign.

## Bit setting and clearing
Change [a] specific bit/s without affecting the other bits.

Bit set `ORR.W`
```
value |= mask_of_bit;
```

Bit clear
```
value &= ~mask_of_bit;
```

