## [NW](/formats.md#nw) > [Sound Files](./sound.md) > Group File (FGRP)

This file contains a group of subfiles in a [BFSAR archive](./bfsar.md). When a file isn't stored in the [file block](./bfsar.md#file-block) of the [BFSAR file](./bfsar.md) or externally, the group files are scanned until it is found (or not found anywhere).

| Block id | Description |
| --- | --- |
| `0x7800` | [Info block](#info-block) |
| `0x7801` | [File block](#file-block) |
| `0x7802` | [InfoEx block](#infoex-block) |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 4 | Number of entries |
| 0xC | | [References] to [location info](#location-info) (0x7900) |

### Location Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File index |
| 0x4 | 8 | [Reference] into [file block](#file-block) body (0x1F00) |
| 0xC | 4 | Filesize |

## File Block
This block contains the actual subfiles. All files are aligned to 32 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("FILE") |
| 0x4 | 4 | Block size |
| 0x8 | | Files |

## InfoEx Block
This block specifies which files this group depends on.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFX") |
| 0x4 | 4 | Block size |
| 0x8 | | [References] to [dependency info](#dependency-info) (0x7901) |

### Dependency Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Item id] |
| 0x4 | 4 | Flags |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id