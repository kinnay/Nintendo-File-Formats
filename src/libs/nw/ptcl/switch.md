## [NW](../../formats.md#nw) > [Particle File](../ptcl.md) > Switch

A `.ptcl` file contains graphical effects. This page describes the `.ptcl` file format as seen in Nintendo Switch games. This page describes version 22.4.0 of the file format.

This file format does not use relocation tables.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Binary file header](../../switch/binary.md#file-header) (`VFXB    `) |
| 0x20 | 32 | Filename ("Particle") |
| 0x40 | | Top-level sections |

Every section starts with a [section header](#section-header) that indicates its type. The following top-level sections may be present in a particle file:

| Type | Description |
| --- | --- |
| `ESTA` | [Emitter set array](#emitter-set-array) |
| `GRTF` | [Graphics resource texture files](#graphics-resource-texture-files) |
| `PRMA` | Primitive array |
| `G3PR` | 3D models |
| `GRSN` | Shader binary array |

## Section Header
Offsets in the section header are relative to the start of the section header.

If a section has no children, the offset to the first child section is set to -1. If there are no further siblings, the offset to the next sibling section is set to -1.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number |
| 0x4 | 4 | Total size of section header and children |
| 0x8 | 4 | Offset to first child section |
| 0xC | 4 | Offset to next sibling section |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | Offset to section payload |
| 0x18 | 4 | Unknown |
| 0x1C | 4 | Unknown |

Whether the section data starts with a child section or other data depends on the section type.

## Emitter Set Array
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Section header](#section-header) (`ESTA`) |
| 0x20 | | [Emitter sets](#emitter-set)

### Emitter Set
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Section header](#section-header) (`ESET`) |
| 0x20 | 104 | [Emitter set payload](#emitter-set-payload) |
| 0x88 | | [Emitter](#emitter) sections |

#### Emitter Set Payload
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | Unknown |
| 0x10 | 64 | Emitter set name |
| 0x50 | 4 | Number of emitters |
| 0x54 | 20 | Unknown |

### Emitter
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Section header](#section-header) (`EMTR`) |
| 0x20 | | Unknown |

## Graphics Resource Texture Files
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Section header](#section-header) (`GRTF`) |
| 0x20 | | Unknown |
