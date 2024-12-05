## [NW](../../formats.md#nw) > Model Archive (FRES)

A BFRES archive contains various resources for 3D objects, such as models, textures and animations. This page describes version `3.0.0.1` of the file format.

The general file structure is as follows:
* [Header](#header)
* [Metadata](#metadata)
* [File info](#file-info)
* [Dictionaries](#dictionary)
* Resources
* [String table](#string-table)
* Texture data
* File data

All offsets are relative to themselves and may be negative.

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FRES`) |
| 0x4 | 4 | Version number |
| 0x8 | 2 | BOM (Always 0xFEFF) |
| 0xA | 2 | Header size (always 0x10) |
| 0xC | 4 | Filesize |

## Metadata
The metadata comes right after the [header](#header).

| Offset | Size | Description |
| --- | --- | --- |
| 0x10 | 4 | Alignment |
| 0x14 | 4 | Offset to archive name |
| 0x18 | 4 | Size of [string table](#string-table) |
| 0x1C | 4 | Offset to [string table](#string-table) |
| 0x20 | 4 | Offset to [model](#model) [dictionary](#dictionary) |
| 0x24 | 4 | Offset to [texture](#texture) [dictionary](#dictionary) |
| 0x28 | 4 | Offset to skeletal animation [dictionary](#dictionary) |
| 0x2C | 4 | Offset to shader param animation [dictionary](#dictionary) |
| 0x30 | 4 | Offset to color animation [dictionary](#dictionary) |
| 0x34 | 4 | Offset to texture SRT animation [dictionary](#dictionary) |
| 0x38 | 4 | Offset to shader param animation [dictionary](#dictionary) |
| 0x3C | 4 | Offset to bone visibility animation [dictionary](#dictionary) |
| 0x40 | 4 | Offset to material visibility animation [dictionary](#dictionary) |
| 0x44 | 4 | Offset to shape animation [dictionary](#dictionary) |
| 0x48 | 4 | Offset to scene animation [dictionary](#dictionary) |
| 0x4C | 4 | Offset to [file](#file-info) [dictionary](#dictionary) |
| 0x50 | 2 | Number of model objects |
| 0x52 | 2 | Number of texture objects |
| 0x54 | 2 | Number of skeletal animation objects |
| 0x56 | 2 | Number of shader param animation objects |
| 0x58 | 2 | Number of color animation objects |
| 0x5A | 2 | Number of texture SRT animation objects |
| 0x5C | 2 | Number of shader param animation objects |
| 0x5E | 2 | Number of bone visibility animation objects |
| 0x60 | 2 | Number of material visibility animation objects |
| 0x62 | 2 | Number of shape animation objects |
| 0x64 | 2 | Number of scene animation objects |
| 0x66 | 2 | Number of files |
| 0x68 | 4 | Padding |

## File Info
This section contains information for additional files that may be stored in a BFRES archive:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to file |
| 0x4 | 4 | Size of file |

These entries are referenced by the file [dictionary](#dictionary) (see [metadata](#metadata)).

## Dictionary
A dictionary contains a [patricia trie](https://en.wikipedia.org/wiki/Radix_tree) that makes it possible to find an object in the BFRES archive by name. It is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of dictionary |
| 0x4 | 4 | Number of objects |
| 0x8 | | Dictionary nodes |

Every dictionary node is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Inspected bit position |
| 0x4 | 2 | Left index (followed when bit is 0) |
| 0x6 | 2 | Right index (followed when bit is 1) |
| 0x8 | 4 | Offset to name |
| 0xC | 4 | Offset to data |

The search always starts at the first node. In the first node, the bit position is always -1 and the left index is always followed. Then, whether the left or right index is followed depends on the inspected bit in the object name.

In every node, one of the indices refers to the node itself. When that index is followed, the search is stopped and the object name is compared.

The dictionary must always be arranged so that the bits are inspected from right to left (high to low).

Given a byte string, the correct bit can be extracted as follows:

```python
def get_bit(name, index):
	return (name[index // 8] >> (index % 8)) & 1
```

If the bit index is longer than the given name, then 0 is used.

## User Data
Various objects in a BFRES archive support user data. This can be used to store additional data in the object for any purpose.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to user data name |
| 0x4 | 2 | Number of values (N) |
| 0x6 | 1 | [Value type](#user-data-type) |
| 0x7 | 1 | Padding |
| 0x8 | 4 * N | Values |

### User Data Type
| ID | Type |
| --- | --- |
| 0 | Integer |
| 1 | Float |
| 2 | String |
| 3 | Wide string |
| 4 | Raw data |

## Model
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FMDL`) |
| 0x4 | 4 | Offset to model name |
| 0x8 | 4 | Offset to model path |
| 0xC | 4 | Offset to skeleton |
| 0x10 | 4 | Offset to vertex buffer array |
| 0x14 | 4 | Offset to shape [dictionary](#dictionary) |
| 0x18 | 4 | Offset to material [dictionary](#dictionary) |
| 0x1C | 4 | Offset to user data [dictionary](#dictionary) |
| 0x20 | 2 | Number of vertex buffers |
| 0x22 | 2 | Number of shapes |
| 0x24 | 2 | Number of materials |
| 0x26 | 2 | Number of user data entries |
| 0x28 | 4 | Number of vertices |
| 0x2C | 4 | Reserved (always 0) |

## Texture
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FTEX`) |
| 0x4 | 156 | [Texture](../wiiu/gx2.md#gx2texture) |
| 0xA0 | 4 | Reserved (always 0) |
| 0xA4 | 4 | Unknown |
| 0xA8 | 4 | Offset to texture name |
| 0xAC | 4 | Offset to texture path |
| 0xB0 | 4 | Offset to image data |
| 0xB4 | 4 | Offset to mipmap data |
| 0xB8 | 4 | Offset to [user data](#user-data) [dictionary](#dictionary) |
| 0xBC | 2 | Number of [user data](#user-data) entries |
| 0xBE | 2 | Padding |

## String Table
Most text strings, such as object names, are stored in the string table. Every string is null-terminated and padded so that its size is a multiple of 4 bytes. Every string is also prefixed by a 4-byte integer that specifies its size without the null terminator and padding.

When an offset refers to a string, it always points to the string itself, not the length prefix.

In official files, the string table seems to be sorted. The last string is always an empty string.
