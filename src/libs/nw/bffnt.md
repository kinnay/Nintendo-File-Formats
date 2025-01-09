## [NW](../../formats.md#nw) > Font File (FFNT)

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("FFNT") |
| 0x4 | 2 | Endianness (0xFEFF) |
| 0x6 | 2 | Header size (0x14) |
| 0x8 | 4 | Version number |
| 0xC | 4 | Filesize |
| 0x10 | 2 | Number of sections |
| 0x12 | 2 | Padding |
| 0x14 | | Sections. All sections are aligned to 4 bytes. |

## Info Section
Contains general information about the font.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("FINF") |
| 0x4 | 4 | Section size |
| 0x8 | 1 | Font type |
| 0x9 | 1 | Width |
| 0xA | 1 | Height |
| 0xB | 1 | Ascent |
| 0xC | 2 | Line feed |
| 0xE | 2 | Invalid char symbol index |
| 0x10 | 1 | Unknown |
| 0x11 | 1 | Unknown |
| 0x12 | 1 | Unknown |
| 0x13 | 1 | Character code |
| 0x14 | 4 | Offset to texture section |
| 0x18 | 4 | Offset to width section |
| 0x1C | 4 | Offset to code map section |

## Texture Section
A font may consist of multiple texture sheets. The texture data of each sheet is stored directly after each other. Every cell contains a single glyph texture.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("TGLP") |
| 0x4 | 4 | Section size |
| 0x8 | 1 | Cell width |
| 0x9 | 1 | Cell height |
| 0xA | 1 | Number of sheets |
| 0xB | 1 | Unknown |
| 0xC | 4 | Sheet size |
| 0x10 | 2 | Baseline position |
| 0x12 | 2 | Texture format |
| 0x14 | 2 | Cells per row |
| 0x16 | 2 | Cells per column |
| 0x18 | 2 | Texture width |
| 0x1A | 2 | Texture height |
| 0x1C | 4 | Texture data offset |

| Texture Format | GX2SurfaceFormat |
| --- | --- |
| 0 | GX2_SURFACE_FORMAT_UNORM_R8_G8_B8_A8 |
| 12 | GX2_SURFACE_FORMAT_UNORM_BC4 |

## Width Section
Contains width information for a range of glyphs.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("CWDH") |
| 0x4 | 4 | Section size |
| 0x8 | 2 | First glyph index |
| 0xA | 2 | Last glyph index |
| 0xC | 4 | Size of width data |
| 0x10 | | Width data |

### Width Entry
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Distance from left cell border to character |
| 0x1 | 1 | Cell width |
| 0x2 | 1 | Character width |

## Code Map Section
Assigns glyphs to a range of character codes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("CMAP") |
| 0x4 | 4 | Section size |
| 0x8 | 2 | First character code |
| 0xA | 2 | Last character code |
| 0xC | 2 | Mapping type |
| 0xE | 2 | Padding |
| 0x10 | 4 | Size of mapping data |
| 0x14 | | Mapping data |

### Code Map Type 0
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | `base_index`. The first character code is mapped to `base_index`. The second is mapped to `base_index + 1`, and so on. |

### Code Map Type 1
If a glyph index is 0xFFFF it indicates an invalid character.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Glyph index of first character code |
| 0x2 | 2 | Glyph index of second character code |
| ... | ... | ... |
| ... | 2 | Glyph index of last character code |

### Code Map Type 2
The first and last character code in the section header are ignored.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Number of entries |
| 0x2 | 2 | Character code 1 |
| 0x4 | 2 | Glyph index 1 |
| 0x6 | 2 | Character code 2 |
| 0x8 | 2 | Glyph index 2 |
| ... | ... | ... |

## Kerning Section
Offsets the horizontal position of glyphs. Positive is right, negative is left. (Pixel Based)
Kerning for Glyphs not listed default to 0.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("KRNG") |
| 0x4 | 4 | Section size |
| 0x8 | | Kerning Data |

### Kerning Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x2 | 2 | Character Code 1 |
| 0x4 | 2 | Horizontal Offset for Glyph 1 |
| 0x6 | 2 | Character Code 2 |
| 0x8 | 2 | Horizontal Offset for Glyph 2 |
| ... | ... | ... |
