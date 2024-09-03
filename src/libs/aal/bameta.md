## [AAL](../../formats.md#aal) > Audio Metadata (BAMETA)

This file is part of a [BARS](./bars.md) file and contains metadata about an audio resource.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("AMTA") |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number (0x0100, 0x0300 or 0x0400) |
| 0x8 | 4 | Filesize |
| 0xC | 4 | Offset to [data section](#data-section) |
| 0x10 | 4 | Offset to [marker section](#marker-section) |
| 0x14 | 4 | Offset to [ext section](#ext-section). *Only present in version 3.0 and 4.0* |
| 0x14 or 0x18 | 4 | Offset to [string table section](#string-table-section) |

The file is padded with null bytes at the end such that its size is a multiple of 4.

## Data Section
Header:
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("DATA") |
| 0x4 | 4 | Body size |

Body:
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Asset name (offset into string table) |
| 0x4 | 4 | Number of output samples at 48000 Hz |
| 0x8 | 1 | Type (0=Wave, 1=Stream) |
| 0x9 | 1 | Total number of channels |
| 0xA | 1 | Number of stream tracks (up to 8) |
| 0xB | 1 | Flags:<br>1 = unknown<br>2 = unknown<br>4 = is looped<br>8 = unknown<br>16 = unknown |
| 0xC | 4 | Unknown (float) |
| 0x10 | 4 | Sample rate |
| 0x14 | 4 | Loop start sample |
| 0x18 | 4 | Number of samples |
| 0x1C | 4 | Volume in decibel (float). This is always negative. Calculate the real volume as follows: `10 ** (value / 20)`. |
| 0x20 | 8 * 8 | [Stream tracks](#stream-track) |
| 0x60 | 4 | Amplitude peak value (float). *Only present in version 4.0* |

### Stream Track
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of channels |
| 0x4 | 4 | Volume (float) |

## Marker Section
Header:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("MARK") |
| 0x4 | 4 | Body size |

Body:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [Marker infos](#marker-info) |

### Marker Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Id |
| 0x4 | 4 | Name (offset into string table) |
| 0x8 | 4 | Start pos |
| 0xC | 4 | Length |

## Ext Section
Header:
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("EXT_") |
| 0x4 | 4 | Body size |

Body:
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [Ext entries](#ext-entry) |

### Ext Entry
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (offset into string table) |
| 0x4 | 4 | Value (float) |

## String Table Section
> <b>Nintendo's tools are broken.</b>
>
> Obviously, an offset into the string table should be measured in bytes. However, Nintendo's tooling counts the number of characters instead. Thus, if a string contains non-ascii characters, all offsets to strings that come after it are wrong.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("STRG") |
| 0x4 | 4 | Body size |
| 0x8 | | Body (null-terminated strings) |

Duplicate strings are stored in the string table only once.