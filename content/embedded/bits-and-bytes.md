---
title: bits-and-bytes
date: 2021-12-30
tags:
  - math/numbers
---

**See also:** [bin-hex-dec-table](embedded/bin-hex-dec-table.md)

|         Example (bin) | Bit | Byte | Hex | Example (hex) | Note               |
| ---------------------:| ---:| ----:| ---:| -------------:| ------------------ |
|                   `0` |   1 |      |     |           0x0 |                    |
|                  `01` |   2 |      |     |           0x1 |                    |
|                `0101` |   4 |      |     |           0x5 | Nibble (half byte) |
|                `1111` |     |      |     |           0xF |                    |
|           `0101 0101` |   8 |    1 |     |          0x55 | Half word          |
|           `1111 1111` |     |      |     |          0xFF |                    |
| `0011 0101 0011 0101` |  16 |    2 |   1 |        0x3535 | Word               |
|                       |  32 |    4 |   2 |   0xDEAD'BEEF |                    |

**Note**
* KB (kilobyte binary), also known as KiB (kibibyte), is different from kB (kilobyte metric)
* A metric kilobyte is a thousand bytes  
	$$
	1 \text{~kB} = 1000 \text{~B}
	$$
* A binary kilobyte is a $2^{10}$ bytes  
	$$
	1 \text{~KB} = 1 \text{~KiB} = 1024 \text{~B}
	$$