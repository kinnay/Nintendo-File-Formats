## [CAS](../../formats.md#cas) > Binary Animation Event

This page describes version 2.1.0 of the file format.

All offsets are absolute and the file is encoded in little-endian byte order.

Fields that are marked as pointer are absolute offsets in the file. These may be replaced by a memory address at runtime, and hence occupy 8 bytes.

General file layout:
* [File header](#file-header)
* [Section headers](#section-header)
* [Data section](#data-section)

Note: the naming of the tables on this page is somewhat arbitrary. When `.baev` files are better understood they might be changed.

## File Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`BFFH`) |
| 0x4 | 4 | Unknown (always 0?) |
| 0x8 | 4 | Filesize |
| 0xC | 4 | Alignment (always 8) |
| 0x10 | 8 | Pointer to [section header](#section-header) array |
| 0x18 | 4 | Number of [section header](#section-header) |
| 0x1C | 4 | Size of each [section header](#section-header) |
| 0x20 | 8 | Pointer to [data section](#data-section) |
| 0x28 | 128 | Class name |

The class name is always: `Nintendo.AnimationEvent.ResourceConverter.Resource.AnimationEventArchiveResData`.

## Section Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`BFSI`) |
| 0x4 | 4 | Data offset |
| 0x8 | 4 | Data size |
| 0xC | 4 | Data alignment |
| 0x10 | 8 | Data pointer |
| 0x18 | 16 | Section name |

## Data Section
This section contains raw data that is referenced by the [section headers](#section-header). There are always two sections in the file: `Default` and `StringPool`. The string pool section simply contains null terminated strings. The default section has the following format:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Reserved (a pointer to the file header is placed here at runtime) |
| 0x8 | 1 | Micro version (0) |
| 0x9 | 1 | Minor version (1) |
| 0xA | 2 | Major version (2) |
| 0xC | 4 | Padding |
| 0x10 | 8 | Pointer to string pool |
| 0x18 | 8 | Pointer to [event table](#event-table) (may be 0) |
| 0x20 | 4 | Number of [event table](#event-table) entries |
| 0x24 | 4 | Size of each [event table](#event-table) entry (should be 24) |
| 0x28 | 8 | Pointer to [action table](#action-table) (may be 0) |
| 0x30 | 4 | Number of [action table](#action-table) entries |
| 0x34 | 4 | Size of each [action table](#action-table) entry (should be 24) |

### Event Table
The event table is sorted by the name hash. All entries have the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Name hash](#hash-algorithm) |
| 0x4 | 4 | Padding |
| 0x8 | 8 | Pointer to action indices for this group |
| 0x10 | 4 | Number of action indices in this group |
| 0x14 | 4 | Size of each action index (always 4) |

The event table is followed by a list of action indices (4 bytes each).

The names can be found in `.asb` files.

Example names from the Tomodachi Life Demo:
* `SneakingUpH127W0`
* `JumpUpDiagonallyVertical`
* `SneakingPose`

### Action Table
All entries in the action table have the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Pointer to [animation entries](#animation-table) |
| 0x8 | 4 | Number of [animation entries](#animation-table) |
| 0xC | 4 | Size of each [animation entry](#animation-table) (should be 48) |
| 0x10 | 4 | [Name hash](#hash-algorithm) |
| 0x14 | 4 | Unknown |

### Animation Table
All entries in the animation table have the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Pointer to name |
| 0x8 | 8 | Pointer to [trigger entries](#trigger-table) |
| 0x10 | 4 | Number of [trigger entries](#trigger-table) |
| 0x14 | 4 | Size of each [trigger entry](#trigger-table) (should be 24) |
| 0x18 | 8 | Pointer to [hold entries](#trigger-table) |
| 0x20 | 4 | Number of [hold entries](#trigger-table) |
| 0x24 | 4 | Size of each [hold entry](#trigger-table) (should be 24) |
| 0x28 | 4 | Unknown |
| 0x2C | 4 | Unknown |

### Trigger Table
All entries in the trigger and hold table have the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Pointer to [parameter](#parameter) pointers |
| 0x8 | 4 | Number of [parameter](#parameter) pointers |
| 0xC | 4 | Size of each [parameter](#parameter) pointer (should be 8) |
| 0x10 | 4 | Start frame (float) |
| 0x14 | 4 | End frame (float) |

The table is followed by a list of pointers to [parameters](#parameter) (8 bytes each).

### Parameter
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Parameter type](#parameter-types) |
| 0x4 | 4 | Padding |
| 0x8 | | Parameter value |

The value is padded so that its size is a multiple of 8 bytes.

#### Parameter Types
| ID | Size | Type |
| --- | --- | --- |
| 0 | 4 | Integer |
| 1 | 4 | Float |
| 2 | | Unknown |
| 3 | 12 | Vector (3 floats) |
| 4 | | Unknown |
| 5 | 8 | String pointer |
| 6 | | Unknown |
| 7 | | Unknown |
| 8 | | Unknown |

### Hash Algorithm
The hash algorithm is as follows:

```python
def calc_hash(name):
    hash = 0x811c9dc5
    const = 0x1000193
    for char in name:
        hash = (hash ^ ord(char)) * const
        hash &= 0xFFFFFFFF
    return hash
```

## External links
* [https://github.com/dt-12345/asb](https://github.com/dt-12345/asb)
