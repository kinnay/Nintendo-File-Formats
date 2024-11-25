## [NW](../../formats.md#nw) > Model Archive (FRES)

A BFRES archive contains various resources for 3D objects, such as models, textures and animations. This page describes version `3.0.0.1` of the file format.

The general file structure is as follows:
* [Header](#header)
* [Metadata](#metadata)
* [Additional file info](#additional-file-info)
* [Dictionaries](#dictionary)
* Resources and [string table](#string-table)

All offsets are relative to themselves.

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
| 0x20 | 4 | Offset to model dictionary |
| 0x24 | 4 | Offset to texture dictionary |
| 0x28 | 4 | Offset to skeletal animation dictionary |
| 0x2C | 4 | Offset to shader param animation dictionary |
| 0x30 | 4 | Offset to color animation dictionary |
| 0x34 | 4 | Offset to texture SRT animation dictionary |
| 0x38 | 4 | Offset to shader param animation dictionary |
| 0x3C | 4 | Offset to bone visibility animation dictionary |
| 0x40 | 4 | Offset to material visibility animation dictionary |
| 0x44 | 4 | Offset to shape animation dictionary |
| 0x48 | 4 | Offset to scene animation dictionary |
| 0x4C | 4 | Offset to additional file dictionary |
| 0x50 | 4 | Number of model objects |
| 0x52 | 4 | Number of texture objects |
| 0x54 | 4 | Number of skeletal animation objects |
| 0x56 | 4 | Number of shader param animation objects |
| 0x58 | 4 | Number of color animation objects |
| 0x5A | 4 | Number of texture SRT animation objects |
| 0x5C | 4 | Number of shader param animation objects |
| 0x5E | 4 | Number of bone visibility animation objects |
| 0x60 | 4 | Number of material visibility animation objects |
| 0x62 | 4 | Number of shape animation objects |
| 0x64 | 4 | Number of scene animation objects |
| 0x66 | 4 | Number of additional files |
| 0x68 | 4 | Padding |

## Additional File Info
This section contains the following for every additional file:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to additional file |
| 0x4 | 4 | Size of additional file |

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

## String Table
Most text strings, such as object names, are stored in the string table. Every string is null-terminated and padded so that its size is a multiple of 4 bytes. Every string is also prefixed by a 4-byte integer that specifies its size without the null terminator and padding.

When an offset refers to a string, it always points to the string itself, not the length prefix.

In official files, the string table seems to be sorted. The last string is always an empty string.
