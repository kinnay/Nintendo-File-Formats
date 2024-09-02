## [NW](/formats.md#nw) > Sound File Overview

This page describes some general data structures seen in a [BFSAR file](./bfsar.md) and its subfiles. Each sound file is divided into one or more blocks, which are all aligned to 32 bytes.

## File Header
The header is padded with null bytes until it contains a multiple of 32 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number |
| 0x4 | 2 | Endianness (0xFEFF=Big, 0xFFFE=Little) |
| 0x6 | 2 | Header size, including block references |
| 0x8 | 4 | Version number |
| 0xC | 4 | Filesize |
| 0x10 | 2 | Number of blocks |
| 0x12 | 2 | Padding |
| 0x14 | | [Block references](#block-reference) |

## Block Reference
Blocks are looked up by id, so their order doesn't matter.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Type id |
| 0x2 | 2 | Padding |
| 0x4 | 4 | Offset, relative to start of file |
| 0x8 | 4 | Size |

## Section Reference
If a section is not present, the type id is set to 0 and the offset is set to -1.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Type id |
| 0x2 | 2 | Padding |
| 0x4 | 4 | Offset, relative to start of section or block |

## Item ID
Files are often referenced by 'item id'. An item id consists of both file type and file index. The file index is an index into the reference table of the corresponding file type in the [INFO block](./bfsar.md#info-block) of the [BFSAR file](./bfsar.md).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | File type |
| 0x1 | 3 | File index |

<br>

| File type | Description |
| --- | --- |
| 1 | Sound (SE/WSD/STRM) |
| 2 | Sound group (WSDSET/SEQSET) |
| 3 | Bank (BANK) |
| 4 | Player (PLAYER) |
| 5 | Wave archive (WAR) |
| 6 | Group (GROUP) |

## Wave ID Table
This table contains references to individual wave files.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [Wave file ids](#wave-file-id) |

### Wave File ID
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Item id](#item-id) of [wave archive](./bfwar.md) |
| 0x4 | 4 | Wave file index |

## ADSHR Curve
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Attack |
| 0x1 | 1 | Decay |
| 0x2 | 1 | Sustain |
| 0x3 | 1 | Hold |
| 0x4 | 1 | Release |