## [ELINK](/formats.md#xlink) > Effect Links

This file format was reverse engineered by [KillzXGaming](https://github.com/kinnay/Nintendo-File-Formats/issues/5).

## Header

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Signature (eflk) |
| 0x4 | 4 | Version |
| 0x8 | 4 | User data count|
| 0xC | 4 | String table offset|

After the header is a list of user data entry pointers.

## User Data Pointer

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Data offset (from start of file) |
| 0x4 | 4 | Name offset (from string table) |

Each data points to a user data section

## User Data

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown (usually 9) |
| 0x4 | 4 | Num emitter set param/index tables. |
| 0x8 | 4 | Num emitter resources. |
| 0xC | 4 | Num emitter action param table. |
| 0x10 | 4 | Num actions. |
| 0x14 | 4 | String table offset (relative from start of this header). |
| 0x18 | 4 | Unkown (4). |

Then each section is in order.

## Emitter Set Param Table

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index |
| 0x4 | 28 | Unknown |
| 0x20 | 28 | Name offset (relative from string table) |
| 0x24 | 24 | Unknown |
| 0x3C | 4 | Scale (float) |
| 0x48 | 12 | Position (float[3]) |
| 0x54 | 12 | Rotate (float[3]) |
| 0x60 | 16 | Color (float[4]) |


## Emitter Set Index Table

Emitter Set Index Table (possibly emitter set custom callback indices?)

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index 1 |
| 0x4 | 4 | Value 1 |
| 0x8 | 4 | Index 2 |
| 0xC | 4 | Value 2 |

## Emitter Resource Table

Emitter Resource (section that stores emitter sets)

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name offset (relative to string table) |
| 0x4 | 12 | Padding |
| 0x10 | 4 | Start emitter set index (from the emitter set param list) |
| 0x14 | 4 |  End emitter set index (from the emitter set param list) |

## Emitter Action Param Table

Parameters for emitter action parameters to be used with the action section.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index |
| 0x4 | 4 | Name (same as emitter resource to use on) (relative to string table) |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Frame to emit at |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | Unknown |
| 0x18 | 4 | Bone name to attach to (relative to string table) |
| 0x1C | 28 | Unknown |

## Emitter Action Table

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (relative to string table)|
| 0x4 | 4 | Padding|
| 0x8 | 4 | Action parameter table Index Start|
| 0xC | 4 | Action  parameter table Index End|

