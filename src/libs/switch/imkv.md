## [Switch](../../formats.md#nintendo-switch) > Key-Value Database (IMKV)

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`IMKV`) |
| 0x4 | 4 | Always 0 |
| 0x8 | 4 | Number of entries |
| 0xC | | [Entries](#entry) |

### Entry
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`IMEN`) |
| 0x4 | 4 | Key size (K) |
| 0x8 | 4 | Value size (V) |
| 0xC | K | Key |
| | V | Value |

### References
* [https://switchbrew.org/wiki/IMKV](https://switchbrew.org/wiki/IMKV)
