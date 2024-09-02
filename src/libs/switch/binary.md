The Nintendo Switch SDK provides basic binary file parsing functions under the `nn::util` namespace. This is used by various Switch libraries, such as the [Bezel engine](../../formats.md#nw).

In general, the files have the following structure:

* [File header](#file-header)
* [File blocks](#block-header)
* [Relocation table](#relocation-table)

## File Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Magic number |
| 0x8 | 1 | Micro version |
| 0x9 | 1 | Minor version |
| 0xA | 2 | Major version |
| 0xC | 2 | Endianness (0xFEFF=Big, 0xFFFE=Little) |
| 0xE | 1 | Alignment |
| 0xF | 1 | Address size |
| 0x10 | 4 | Filename offset |
| 0x14 | 2 | Flags:<br>1 - Is relocated |
| 0x16 | 2 | [First block](#first-block) offset |
| 0x18 | 4 | [Relocation table](#relocation-table) offset |
| 0x1C | 4 | Filesize |
| 0x20 | | Depends on file format |

## Block Header
The block size is usually the same as the offset to the next block, but in the last block the offset is set to 0.

Most blocks depend on the file format, but there is one block that is always present: the [string pool](#string-pool). This block is stored behind the format-specific blocks.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Signature |
| 0x4 | 4 | Offset to next block |
| 0x8 | 4 | Block size, including header |
| 0xC | 4 | Padding |
| 0x10 | | Block body |

## String Pool
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [Block header](#block-header) (`_STR`) |
| 0x10 | 4 | String count |
| 0x14 | | Strings |

### String
Every string is null-terminated. If the string contains an odd number of bytes, an additional null byte is added such that the size field of the next string is aligned.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Size without null terminator |
| 0x2 | | Null-terminated string |

## Relocation Table
When the file is loaded into memory, it is relocated by converting offsets to memory addresses. Which offsets need to be converted is defined by the relocation table.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Signature (`_RLT`) |
| 0x4 | 4 | Offset of relocation table (see [file header](#file-header)) |
| 0x8 | 4 | Number of sections |
| 0xC | 4 | Padding |
| 0x10 | | [Sections](#relocation-section) |
| | | [Relocations](#relocation-entry) |

### Relocation Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Memory address |
| 0x8 | 4 | File offset |
| 0xC | 4 | File size |
| 0x10 | 4 | Index of first relocation |
| 0x14 | 4 | Number of relocations |

### Relocation Entry
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File offset |
| 0x4 | 2 | Number of chunks |
| 0x6 | 1 | Relocated words per chunk |
| 0x7 | 1 | Non-relocated words per chunk |