The Nintendo Switch SDK provides basic binary file parsing functions under the `nn::util` namespace. This is used by various Switch libraries, especially by [NintendoWare](../../formats.md#nw).

## File Header
The alignment value specifies the number of bits. For example, if the alignment has the value 12, then the file must be aligned to `1 << 12 = 4096` bytes.

The address size field specifies the number of bits in a pointer. This is usually 64.

The relocation flag indicates whether the [relocation table](#relocation-table) has been applied at runtime. The relocation flag is set to 1 at runtime after relocations are applied.

If there is no relocation table, the relocation table offset is 0.

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
| 0x16 | 2 | Offset to first block or section |
| 0x18 | 4 | [Relocation table](#relocation-table) offset |
| 0x1C | 4 | Filesize |

## Block Header
The block size is usually the same as the offset to the next block, but in the last block the offset is set to 0.

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
| 0x10 | 4 | String count, excluding empty string |
| 0x14 | 4 | Empty string |
| 0x18 | | [Strings](#string) |

### String
Every string is null-terminated. If the string contains an odd number of bytes, an additional null byte is added such that the size field of the next string is aligned.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Size without null terminator |
| 0x2 | | Null-terminated string |

## Dictionary
The dictionary contains a binary search tree that allows programs to efficiently find the index of a given string.

> **Note:** not all strings are included in the dictionary. Which strings are included the dictionary depends on the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always `_DIC` |
| 0x4 | 4 | Number of nodes, excluding root node (N) |
| 0x8 | 16 | Root node |
| 0x18 | 16 * N | Other nodes |

Every node is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Bit index |
| 0x4 | 2 | Left child index (when bit is 0) |
| 0x6 | 2 | Right child index (when bit is 1) |
| 0x8 | 8 | Offset to string in [string pool](#string-pool), relative to start of file |

In the root node, the bit index is -1, the left index points to the actual root node, the right index is 0, and the offset points to the empty string of the [string pool](#string-pool).

In other nodes, the offset refers to a string in the [string pool](#string-pool). If this string does not equal the search string, the search continues at one of its children. Which child is chosen depends on whether a specific bit in the search string is 0 or 1.

Bit index 0 refers to the least significant (right-most) bit of the string.

Node index 0 refers to the root node. Node index 1 refers to the first node after the root node. If there are no further children, the node index refers to the node itself or one of its parents.

## Relocation Table
When the file is loaded into memory, it is relocated by converting offsets to memory addresses. Which offsets need to be converted is defined by the relocation table.

The relocation table offset is repeated here, so that the beginning of the file can be found from a pointer to the relocation table.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Signature (`_RLT`) |
| 0x4 | 4 | Offset of relocation table (see [file header](#file-header)) |
| 0x8 | 4 | Number of sections |
| 0xC | 4 | Padding |
| 0x10 | | [Sections](#relocation-section) |
| | | [Relocations](#relocation-entry) |

### Relocation Section
The address field is a placeholder that is filled in at runtime. It is always 0 in the file.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Memory address |
| 0x8 | 4 | File offset |
| 0xC | 4 | File size |
| 0x10 | 4 | Index of first relocation |
| 0x14 | 4 | Number of relocations |

### Relocation Entry
The word size is specified in the [header](#file-header) in the address size field. In most Switch games, a word consists of 8 bytes.

Every chunk consists of a number of relocated words, followed by a number of non-relocated words. Relocated words contains an offset in the file and are replaced by a pointer at runtime. Non-relocated words are left unchanged.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to chunks, relative to start of file |
| 0x4 | 2 | Number of chunks |
| 0x6 | 1 | Number of relocated words per chunk |
| 0x7 | 1 | Number of non-relocated words per chunk |
