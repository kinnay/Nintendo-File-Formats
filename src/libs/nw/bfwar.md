## [NW](/formats.md#nw) > [Sound](./sound.md) > Wave Archive (FWAR)

This file contains a bunch of [wave files](./bfwav.md) that can be used by [wave sounds](./bfwsd.md) and [banks](./bfbnk.md).

| Block id | Description |
| --- | --- |
| `0x6800` | [Info block](#info-block) |
| `0x6801` | [File block](#file-block) |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 4 | Number of entries |
| 0xC | | [File references](#file-reference) |

### File Reference
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] into [file block](#file-block) body (0x1F00) |
| 0x8 | 4 | Filesize |

## File Block
This block contains the actual subfiles. All files are aligned to 32 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("FILE") |
| 0x4 | 4 | Block size |
| 0x8 | | Files |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id