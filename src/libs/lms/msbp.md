## [LMS](../../formats.md#lms) > [Overview](overview.md) > Project File (MSBP)

This file is identified by the magic number `MsgPrjBn`. This file defines various metadata for [MSBT files](msbt.md).

This page describes file format version 3 and 4.

| Type | Description |
| --- | --- |
| `CLR1` | [Colors](#clr1-block) |
| `CLB1` | [Color labels](#clb1-block) |
| `ATI2` | [Attributes](#ati2-block) |
| `ALB1` | [Attribute labels](#alb1-block) |
| `ALI2` | [Attribute string lists](#ali2-block) |
| `TGG2` | [Tag groups](#tgg2-block) |
| `TAG2` | [Tags](#tag2-block) |
| `TGP2` | [Tag parameters](#tgp2-block) |
| `TGL2` | [Tag string list](#tgl2-block) |
| `SYL3` | [Styles](#syl3-block) |
| `SLB1` | [Style labels](#slb1-block) |
| `CTI1` | [Project contents](#cti1-block) |

All blocks are optional.

## CLR1 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of colors |
| 0x4 | 4 per color | RGBA colors |

## CLB1 Block
This block contains [labels](overview.md#hash-tables) for the CLR1 block.

## ATI2 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of attributes |
| 0x4 | 8 per attribute | [Attributes](#attribute) |

### Attribute
The list index refers to the ALI2 block and is only valid if the type is 9.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Type |
| 0x1 | 1 | Padding |
| 0x2 | 2 | List index |
| 0x4 | 4 | Offset |

## ALB1 Block
This block contains [labels](overview.md#hash-tables) for the ATI2 block.

## ALI2 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of lists |
| 0x4 | 4 per list | Offsets to [attribute lists](#attribute-list) |
| | Attribute lists |

The block is padded until it has a multiple of 4 bytes.

### Attribute List
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of list items |
| 0x4 | 4 per list item | Offsets to list item names |
| | | Null-terminated list item names |

## TGG2 Block
This block defines control tag groups for [MSBT files](msbt.md). 

Control tags allow developers to apply modifiers (such as bold or cursive) and insert placeholders for other text. Tags are organized into groups.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of tag groups |
| 0x2 | 2 | Padding |
| 0x4 | 4 per group | Offsets to [tag groups](#tag-group) |
| | | Tag groups |

### Tag Group
Every tag group is identified by an id. In version 3, the id is simply the index of the group. In version 4, it is explicitly stored in the file.

Version 3:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of tags |
| 0x2 | 2 per tag | Tag indices (in TAG2 block) |
| | | Null-terminated tag group name |

Version 4:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Tag group id |
| 0x2 | 2 | Number of tags |
| 0x4 | 2 per tag | Tag indices (in TAG2 block) |
| | | Null-terminated tag group name |

Every tag group is padded so that its size is a multiple of 4.

## TAG2 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of tags |
| 0x2 | 2 | Padding |
| 0x4 | 4 per tag | Offsets to [tags](#tag) |

### Tag
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of tag parameters |
| 0x2 | 2 per parameter | Tag parameter indices (in TGP2 block) |
| | | Null-terminated tag name |

Every tag is padded so that its size is a multiple of 4.

## TGP2 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of parameters |
| 0x2 | 2 | Padding |
| 0x4 | 4 per parameter | Offsets to [parameters](#tag-parameter) |

### Tag Parameter
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Parameter type |

If type is not 9:

| Offset | Size | Description |
| --- | --- | --- |
| 0x1 | | Null terminated parameter name |

If type is 9:

| Offset | Size | Description |
| --- | --- | --- |
| 0x1 | 1 | Padding |
| 0x2 | 2 | Number of strings |
| 0x4 | 2 per list item | String indices (in TGL2 block) |
| | | Null terminated parameter name |

Every tag parameter is padded so that its size is a multiple of 4.

## TGL2 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of strings |
| 0x2 | 2 | Padding |
| 0x4 | 4 per list item | Offsets to strings |
| | | Null-terminated strings |

## SYL3 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of styles |
| 0x4 | 16 per style | [Styles](#style) |

### Style
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Region width |
| 0x4 | 4 | Line num |
| 0x8 | 4 | Font index |
| 0xC | 4 | Base color index |

## SLB1 Block
This block contains [labels](overview.md#hash-tables) for the SYL3 block.

## CTI1 Block
This block contains the names of the source files that the [MSBT files](msbt.md) were generated from. The source files have the `.mstxt` extension.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of filenames |
| 0x4 | 4 per filename | Offsets to filename strings | 
| | | Null-terminated filename strings |
