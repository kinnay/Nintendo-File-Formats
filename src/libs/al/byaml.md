## [AL / LP](../../formats.md#al--lp) > Binary YAML

These files are similar to regular YAML files, but are encoded in binary form. They usually have the file extension `.byml` or `.byaml`.

Dictionary nodes may contain cycles, i.e. they are not necessarily a tree.

## Header
Offsets in the header are 0 if the table that they refer to is empty.

The binary data table is only seen in Mario Kart 8. In other games, binary data is stored as a string.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Magic number / BOM (`BY`: big endian, `YB`: little endian)
| 0x2 | 2 | [Version number](#changelog) |

Old version:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 4 | Offset to [dictionary key table](#string-table) |
| 0x8 | 4 | Offset to [string table](#string-table) |
| 0xC | 4 | Offset to [binary data table](#binary-table) |
| 0x10 | 4 | Offset to root node ([array](#array) or [dictionary](#dictionary)) |

New version:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 4 | Offset to [dictionary key table](#string-table) |
| 0x8 | 4 | Offset to [string table](#string-table) |
| 0xC | 4 | Offset to root node ([array](#array) or [dictionary](#dictionary)) |

## Changelog
| Version | Changes |
| --- | --- |
| v1 | Initial file format. |
| v2 | Unsigned integers were added (**0xD3**). |
| v3 | 64-bit values were added (**0xD4 - 0xD6**). |
| v4 | Binary data was added again (**0xA1**), but without binary data table (**0xC3**). |
| v5 | Type **0xA2** was added. |
| v6 | Unknown |
| v7 | Unknown |

## Node Types
| ID | Type | Version |
| --- | --- | --- |
| 0xA0 | String | Any |
| 0xA1 | Binary data | (1) and 4+ |
| 0xA2 | Binary data with param | 5 |
| 0xC0 | [Array](#array) | Any |
| 0xC1 | [Dictionary](#dictionary) | Any |
| 0xD0 | Bool | Any |
| 0xD1 | Integer | Any |
| 0xD2 | Float | Any |
| 0xD3 | Unsigned integer | 2+ |
| 0xD4 | Integer (64 bits) | 3+ |
| 0xD5 | Unsigned integer (64 bits) | 3+ |
| 0xD6 | Double | 3+ |
| 0xFF | Null | Any |

The following node types may not be used in an array or dictionary. They are only used by the [header](#header).

| ID | Type | Version |
| --- | --- | --- |
| 0xC2 | [String table](#string-table) | Any |
| 0xC3 | [Binary table](#binary-table) | (1) |

Arrays and dictionaries reserve 32 bits per element. Because not all node types fit into 32 bits, they are stored as follows:

| Type | Value |
| --- | --- |
| 0xA0 | An index into the string table (see [header](#header)). |
| 0xA1 | (v1): An index into the binary data table (see [header](#header)).<br>v4: An absolute offset to a binary blob. The blob is prefixed by a 32-bit integer that holds its size. |
| 0xA2 | An absolute offset to a binary blob. The blob is prefixed by a 32-bit integer that holds its size and another 32-bit integer with unknown purpose. |
| 0xC0 and 0xC1 | An absolute offset to the node. |
| 0xD0 - 0xD3 | Simply the value. |
| 0xD4 - 0xD6 | An absolute offset to the value. |
| 0xFF | Doesn't matter, always 0 |

## Array
If the number of elements is not a multiple of 4, additional null bytes are inserted between the type table and the data table such that the data table is aligned to 4 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Node type](#node-types) (0xC0) |
| 0x1 | 3 | Number of elements (N) |
| 0x4 | N | Type table |
| | 4 x N | Data table |

The type table contains one byte per element that indicates its [node type](#node-types).

The data table contains either an absolute offset to the node (for container nodes), or simply the value of the array element (for primitive nodes).

## Dictionary
A dictionary contains key / value pairs. The pairs must be sorted by their keys, because a binary search algorithm is used to look them up.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Node type](#node-types) (0xC1) |
| 0x1 | 3 | Number of pairs (N) |
| 0x4 | 8 x N | Pair table |

Every pair is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 3 | Index into dictionary key table (see [header](#header)) |
| 0x3 | 1 | [Node type](#node-types) |
| 0x4 | 4 | Value |

Just like [array elements](#array-elements), the value is either a primitive or an absolute offset to a container node.

## String Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Node type](#node-types) (0xC2) |
| 0x1 | 3 | Number of strings (N) |
| 0x4 | 4 x (N + 1) | Address table |
| | | Null-terminated strings |

The address table contains offsets to the strings, relative to the start of the string table node. It also contains an offset that points to the end of the string table (right behind the last string).

The address table and strings must both be sorted, because a binary search algorithm is used to find them.

## Binary Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Node type](#node-types) (0xC3) |
| 0x1 | 3 | Number of binary blobs (N) |
| 0x4 | 4 x (N + 1) | Address table |
| | | Binary data |

The address table contains offsets to the binary data, relative to the start of the binary table node. It also contains an offset that points to the end of the binary table (right behind the last binary blob).

The address table must be sorted, because the size of a binary blob is calculated from the difference between two offsets.