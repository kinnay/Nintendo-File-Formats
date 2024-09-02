## [NW](/formats.md#nw) > Bezel Archive (BEA)

This is an archive format used by the Bezel engine. The file format is based on the Nintendo Switch [binary file format](../switch/binary.md).

The compressed subfiles are stored behind the relocation table. The filesize in the file header also does not include the compressed subfiles.

## File Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Binary file header](../switch/binary.md#file-header) (`SCNE`) |
| 0x20 | 2 | Number of subfiles |
| 0x22 | 2 | Unknown |
| 0x24 | 4 | Unknown |
| 0x28 | 8 | Address of file info pointers |
| 0x30 | 8 | Address of dictionary section |
| 0x38 | 8 | Unknown |
| 0x40 | 8 | Address of archive name |
| 0x48 | | File info pointers |
| | | 40 unknown bytes per subfile (all 0?) |
| | | [Dictionary section](#dictionary-section) |

### File Info Pointer
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Address of [file info block](#file-info-block) |

## File Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [Block header](../switch/binary.md#block-header) (`ASST`) |
| 0x10 | 1 | Compression algorithm |
| 0x11 | 1 | Padding |
| 0x12 | 2 | Alignment bits |
| 0x14 | 4 | Compressed size |
| 0x18 | 4 | Decompressed size |
| 0x1C | 4 | Padding |
| 0x20 | 8 | Address of compressed file |
| 0x28 | 8 | Address of filename |

| ID | Algorithm |
| --- | --- |
| 0 | None |
| 1 | Zlib |
| 2 | Zstandard |

## Dictionary Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Signature (`_DIC`) |
| 0x4 | | Unknown |