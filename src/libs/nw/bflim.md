## [NW](../../formats.md#nw) > Layout Image (FLIM)

BFLIM files start with the image data. A footer is stored behind the image data. This probably makes it easier to align the image data in memory. The footer is found by examining the last 4 bytes of the file, which contain the size of the image data.

## Footer
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FLIM`) |
| 0x4 | 2 | Endianness (0xFEFF=Big, 0xFFFE=Little) |
| 0x6 | 2 | Footer size (0x14) |
| 0x8 | 4 | [Version number](#known-versions) |
| 0xC | 4 | Filesize |
| 0x10 | 2 | Number of sections |
| 0x12 | 2 | Padding |
| 0x14 | | Sections. All sections are aligned to 4 bytes. |
| | 4 | Size of image data |

### Known Versions
| Version | Description |
| --- | --- |
| `2.2.0.0` | Oldest known version. |
| `3.3.0.0` | Some image formats were added. |

## Image Section
Contains information about the image.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`imag`) |
| 0x4 | 4 | Section size (0x10) |
| 0x8 | 2 | Width |
| 0xA | 2 | Height |
| 0xC | 2 | Alignment |
| 0xE | 1 | [Format](#image-formats) |
| 0xF | 1 | `value & 31`: Tile mode<br>`value >> 5`: Swizzle |

### Image Formats
| ID  | Format | Compmap | Description |
| ---  | --- | --- | --- |
| 0 | `UNORM` `R8` | `RRR1` | Grayscale |
| 1 | `UNORM` `R8` | `111R` | Transparency |
| 2 | `UNORM` `R4` `G4` | `RRRG` | Grayscale with transparency |
| 3 | `UNORM` `R8` `G8` | `RRRG` | Grayscale with transparency |
| 4 | `UNORM` `R8` `G8` | `RG01` | Red and green |
| 5 | `UNORM` `R5` `G6` `B5` | `BGR1` | Blue, green, red |
| 6 | Invalid | `RGB1` | |
| 7 | `UNORM` `R5` `G5` `B5` `A1` | `RGBA` | RGBA |
| 8 | `UNORM` `R4` `G4` `B4` `A4` | `ABGR` | RGBA |
| 9 | `UNORM` `R8` `G8` `B8` `A8` | `RGBA` | RGBA |
| 10 | Invalid | `RGB1` | |
| 11 | Invalid | `RGBA` | |
| 12 | `UNORM` `BC1` | `RGBA` | RGBA |
| 13 | `UNORM` `BC2` | `RGBA` | RGBA |
| 14 | `UNORM` `BC3` | `RGBA` | RGBA |
| 15 | `UNORM` `BC4` | `RRR1` | Grayscale |
| 16 | `UNORM` `BC4` | `111R` | Transparency |
| 17 | `UNORM` `BC5` | `RRRG` | Grayscale with transparency |
| 18 | Invalid | `RRR1` |
| 19 | Invalid | `000R` |

Version 3.3.0.0:

| ID  | Format | Compmap | Description |
| ---  | --- | --- | --- |
| 20 | `SRGB` `R8` `G8` `B8` `A8` | `RGBA` | RGBA |
| 21 | `SRGB` `BC1` | `RGBA` | RGBA |
| 22 | `SRGB` `BC2` | `RGBA` | RGBA |
| 23 | `SRGB` `BC3` | `RGBA` | RGBA |
| 24 | `UNORM` `R10` `G10` `B10` `A2` | `RGBA` | RGBA |