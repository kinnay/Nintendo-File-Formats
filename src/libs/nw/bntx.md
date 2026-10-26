## [NW](../../formats.md#nw) > Textures (BNTX)

This is the texture format that is used on the Nintendo Switch and Switch 2. This page describes version 4.0.0 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Binary file header](../switch/binary.md#file-header) (`BNTX\0\0\0\0`) |
| 0x20 | 4 | Platform (`NX  ` or `OUNC`) |
| 0x24 | | Unknown |
| 0x1A8 | [String pool](#string-pool) |
| | | [Relocation table](../switch/binary.md#relocation-table) |

### String Pool
This is a standard [string pool section](../switch/binary.md#string-pool), except there is a [dictionary](../switch/binary.md#dictionary) embedded in the string pool section behind the string.
