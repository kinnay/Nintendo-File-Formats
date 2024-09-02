## [NW](/formats.md#nw) > [Sound Files](./sound.md) > Stream File (FSTM)

This file contains stream sound data. Instead of embedding them in the [BFSAR file](./bfsar.md), many games store streams sounds in a separate file. This page describes file format version `0x30000`.

| Block id | Description |
| --- | --- |
| `0x4000` | [Info block](#info-block) |
| `0x4001` | Seek block |
| `0x4002` | [Data block](#data-block) |
| `0x4003` | Region block |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`INFO`) |
| 0x4 | 4 | Block size |
| 0x8 | 8 | [Reference] to [stream sound info](#stream-sound-info) (`0x4100`) |
| 0x10 | 8 | [Reference] to track info table (`0x0101`) |
| 0x18 | 8 | [Reference] to channel info table (`0x0101`) |

### Stream Sound Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Sample format](#sample-format) |
| 0x1 | 1 | Unknown |
| 0x2 | 2 | Unknown |
| 0x4 | 4 | Sample rate |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | Unknown |
| 0x18 | 4 | Unknown |
| 0x1C | 4 | Unknown |
| 0x20 | 4 | Unknown |
| 0x24 | 4 | Unknown |
| 0x28 | 12 | Unknown |
| 0x34 | 4 | Offset into [data block](#data-block) |
| 0x38 | 2 | Unknown |
| 0x3A | 6 | Unknown |
| 0x40 | 4 | Offset into [region block](#region-block) |

#### Sample Format
| Value | Description |
| --- | --- |
| 0 | 8-bit |
| 1 | 16-bit |
| 2 | ADPCM |

## Data Block
This block contains raw stream sound data.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`DATA`) |
| 0x4 | 4 | Block size |
| 0x8 | | Sound data |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id