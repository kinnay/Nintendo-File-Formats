## [XB 2](../../formats.md#xb2) > Audio Files

Each offset is 4 hexa bytes

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x60 | [File Header](#file-header) |
| 0x60 | 0x20 | Padding |
| 0x80 | 0x? | [Seek Table](#seek-table) |
| 0x5BFD0 | 0x? | [Audio Stream](#audio-stream) |


## File Header
| Offset | Value | Description |
| --- | --- | --- |
|0x00 | 73 61 64 66	| sadf |
|0x04 | ?? ?? ?? ??	| file size / total number of bytes |
|0x08 | 6F 70 75 73	| opus |
|0x0c | 01 00 00 00	| ??? |

| 0x10 | 68 65 61 64 | head |
| 0x14 | 80 00 00 00 | seek table position |
| 0x18 | 0? 00 00 00 | 1 or 2 = channel count |
| 0x1c | ?? ?? ?? ?? | raw opus start position |

| 0x20 | ?? ?? ?? ?? | raw opus length (without padding) |
| 0x24 | 80 BB 00 00 | 48 000 Hz sample rate |
| 0x28 | ?? ?? ?? ?? | number of samples |
| 0x2c | 00 00 00 00 | loop start |

| 0x30 | ?? ?? ?? ?? | number of samples (bis) / loop end  |
| 0x34 | ?? ?? ?? ?? | raw opus length (without padding) (bis) |
| 0x38 | 00 00 00 00 | 0 |
| 0x3c | 00 00 00 00 | 0 |

| 0x40 | ... |  |
| 0x44 | 20 4E 00 00 | 20 000 = ??? |
| 0x48 | 00 00 00 00 | 0 |
| 0x4c | ?? ?? ?? ?? | number of frames (without the first and last word of seek table so it’s X-2) |

| 0x50 | ?? ?? ?? ?? | number of frames (bis) |
| 0x54 | 80 00 00 00 | seek table position (bis) |
| 0x58 | ?? ?? ?? ?? | total lenght of the seek table |
| 0x5c | 00 00 00 00 | 0 |

32 bytes empty from 0x60 to 0x7F