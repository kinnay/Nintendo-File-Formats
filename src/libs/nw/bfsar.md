## [NW](../../formats.md#nw) > [Sound](./sound.md) > Sound Archive (FSAR)

A BFSAR file is an archive with all kinds of sound-related files. This page describes file format version `0x20400`.

| Block id | Description |
| --- | --- |
| `0x2000` | [String block](#string-block) |
| `0x2001` | [Info block](#info-block) |
| `0x2002` | [File block](#file-block) |

## String Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("STRG") |
| 0x4 | 4 | Block size |
| 0x8 | 8 | [String table](#string-table) [reference] (0x2400) |
| 0x10 | 8 | [Search tree](#string-search-tree) [reference] (0x2401) |

### String Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of strings |
| 0x4 | | [String table entries](#string-table-entry) |

#### String Table Entry
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | String [reference] (0x1F01) |
| 0x8 | 4 | String size, including null terminator |

### String Search Tree
This is a binary search tree to efficiently find strings in the table.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Root node index |
| 0x4 | 4 | Number of nodes |
| 0x8 | | Tree nodes |

#### Search Tree Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | 1 if this is a leaf, 0 otherwise |
| 0x2 | 2 | String bit index |
| 0x4 | 4 | Left child index, go here when the bit is 0 |
| 0x8 | 4 | Right child index, go here when the bit is 1 |
| 0xC | 4 | String table index |
| 0x10 | 4 | [Item id] |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 8 | [Reference] to [sound info](#sound-info) [reference table](#info-reference-table) (0x2100) |
| 0x10 | 8 | [Reference] to [sound group info](#sound-group-info) [reference table](#info-reference-table) (0x2104) |
| 0x18 | 8 | [Reference] to [bank info](#bank-info) [reference table](#info-reference-table) (0x2101) |
| 0x20 | 8 | [Reference] to [wave archive info](#wave-archive-info) [reference table](#info-reference-table) (0x2103) |
| 0x28 | 8 | [Reference] to [group info](#group-info) [reference table](#info-reference-table) (0x2105) |
| 0x30 | 8 | [Reference] to [player info](#player-info) [reference table](#info-reference-table) (0x2102) |
| 0x38 | 8 | [Reference] to [file info](#file-info) [reference table](#info-reference-table) (0x2106) |
| 0x40 | 8 | [Reference] to [sound archive player info](#sound-archive-player-info) (0x220B) |

### Info Reference Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] |

| Info type | Reference id |
| --- | --- |
| [Sound info](#sound-info) | 0x2200 |
| [Sound group info](#sound-group-info) | 0x2204 |
| [Bank info](#bank-info) | 0x2206 |
| [Wave archive info](#wave-archive-info) | 0x2207 |
| [Group info](#group-info) | 0x2208 |
| [Player info](#player-info) | 0x2209 |
| [File info](#file-info) | 0x220A |

### Sound Info
This structure describes a sound file (STRM/WSD/SE).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File index |
| 0x4 | 4 | Player [item id] |
| 0x8 | 1 | Initial volume |
| 0x9 | 1 | Remote filter |
| 0xA | 2 | Padding |
| 0xC | 8 | [Reference] to [stream](#stream-sound-info) (0x2201), [wave](#wave-sound-info) (0x2202) or [sequence](#sequence-sound-info) (0x2203) info |
| 0x14 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present). The user param fields can be used to store additional information that can be read by the game.

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |
| 0x2 | 0x0000XXYY: XX = pan curve, YY = pan mode |
| 0x4 | 0x0000XXYY: XX = actor player id, YY = player priority |
| 0x100 | Offset to [3D info](#sound-3d-info) |
| 0x20000 | Is front bypass |
| 0x10000000 | User param 1 |
| 0x20000000 | User param 2 |
| 0x40000000 | User param 3 |
| 0x80000000 | User param 4 |

#### Sound 3D Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Flags |
| 0x4 | 4 | Unknown float |
| 0x8 | 1 | Unknown |
| 0x9 | 1 | Unknown |
| 0xA | 2    | Padding  |

#### Stream Sound Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Bitmask defining which tracks are valid |
| 0x2 | 2 | Number of channels (up to 16) |
| 0x4 | 8 | [Reference] to [track info table](#track-info-table) (0x0101) |
| 0x8 | 4 | Unknown float |
| 0x10 | 8 | [Reference] to send value (0xAABBBBCC) (0x220F) |
| 0x18 | 8 | [Reference] to stream sound extension (0x2210) |
| 0x20 | 4 | File index of this stream's prefetch file |

#### Track Info Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [Track info](#track-info) [references] (0x220E) |

#### Track Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Unknown |
| 0x1 | 1 | Unknown |
| 0x2 | 1 | Unknown |
| 0x3 | 1 | Unknown |
| 0x4 | 8 | [Reference] to [track channel info](#track-channel-info) (0x0100) |
| 0xC | 8 | [Reference] to send value (0x220F) |
| 0x14 | 1 | Unknown |
| 0x15 | 1 | Unknown |
| 0x16 | 2 | Padding |

#### Track Channel Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries (up to 2) |
| 0x4 | | Channel indexes (one byte per entry) |

#### Wave Sound Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Wave index in wave archive |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | 0x0000XXYY: XX = Release priority fix, YY = Channel priority |

#### Sequence Sound Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to [bank id table](#bank-id-table) (0x0100) |
| 0x8 | 4 | Bitmask defining which tracks are valid |
| 0xC | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | Start offset |
| 0x2 | 0x0000XXYY: XX = Release priority fix, YY = Channel priority |

#### Bank ID Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | Bank [item ids] |

### Sound Group Info
This structure describes a set of sound files.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Item id] of first sound |
| 0x4 | 4 | [Item id] of last sound |
| 0x8 | 8 | [Reference] to [file table](#file-table) (0x0100) |
| 0x10 | 8 | [Reference] to [wave archive table reference](#wave-archive-table-reference) (0x2205) |
| 0x18 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |

#### File Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | File indices |

#### Wave Archive Table Reference
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to [wave archive table](#wave-archive-table) (0x0100) |

### Bank Info
This structure describes a [bank file](./bfbnk.md).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File index |
| 0x4 | 8 | [Reference] to [wave archive table](#wave-archive-table) (0x0100) |
| 0xC | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |

#### Wave Archive Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | Wave archive [item ids] |

### Wave Archive Info
This structure describes a [wave archive file](./bfwar.md).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File index |
| 0x4 | 1 | Unknown |
| 0x5 | 3 | Padding |
| 0x8 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |
| 0x2 | Number of wave files |

### Group Info
This structure describes a [group file](./bfgrp.md).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File index |
| 0x4 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |

### Player Info
This structure describes a sound player.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Playable sound limit |
| 0x4 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | [String table](#string-block) index (name) |
| 0x2 | Player heap size |

### File Info
This structure describes a single file. A file can be stored either internally or in an external file.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to [internal file info](#internal-file-info) (0x220C), or [external file info](#external-file-info) (0x220D) |

#### Internal File Info
If this file is stored in a [group file](./bfgrp.md) instead of the [file block](#file-block), offset and filesize are set to -1.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] into [file block](#file-block) body (0x1F00) |
| 0x8 | 4 | File size |
| 0xC | 8 | [Reference] to [group table](#group-table) body (0x0100) |

##### Group Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of Entries |
| 0x4 |   | Item Ids of group files |

#### External File Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | | Null-terminated filename string |

### Sound Archive Player Info
This structure defines limits that are used to determine how much memory should be allocated.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of sequence sounds |
| 0x2 | 2 | Number of sequence tracks |
| 0x4 | 2 | Number of stream sounds |
| 0x6 | 2 | Unknown |
| 0x8 | 2 | Number of stream channels |
| 0xA | 2 | Number of wave sounds |
| 0xC | 2 | Unknown |
| 0xE | 1 | Stream Buffer Times |
| 0xF | 1 | Boolean to specify if the waves are "advanced" |

## File Block
This block contains the actual subfiles of the BFSAR file. All files are aligned to 32 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("FILE") |
| 0x4 | 4 | Block size |
| 0x8 | | Files |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id
