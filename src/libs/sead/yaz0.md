## [SEAD](../../formats.md#sead) > Yaz0 Compression (SZS)

This file always uses big endian byte order, even on little endian platforms.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`Yaz0`) |
| 0x4 | 4 | Decompressed size |
| 0x8 | 4 | Required memory alignment (either 0 or a power of 2) |
| 0xC | 4 | Reserved (always 0) |
| 0x10 | | Yaz0 compressed data |

A good explanation of Yaz0 compression can be found here: http://www.amnoid.de/gc/yaz0.txt