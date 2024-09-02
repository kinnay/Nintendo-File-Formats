## [AAL](../../formats.md#aal) > Loop Asset List (BLAL)

This file contains a loop asset list.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("BLAL") |
| 0x4 | 2 | Endianness (0xFFFE for little endian) |
| 0x6 | 2 | Version number (1) |
| 0x8 | 4 | Number of entries |
| 0xC | | CRC32 hashes. These must be sorted, because a binary search algorithm is used to check if a hash is in the list. |