## [NW](../../formats.md#nw) > [Sound](./sound.md) > Wave File (FWAV)

This file contains wave sound data. It is usually stored in a [wave archive](./bfwar.md).

This page describes version 0x10100 and 0x10200 of the file format.

| Block id | Description |
| --- | --- |
| `0x7000` | [Info block](#info-block) |
| `0x7001` | [Data block](#data-block) |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 1 | [Sample format](#sample-format) |
| 0x9 | 1 | Is looped |
| 0xA | 2 | Padding |
| 0xC | 4 | Sample rate |
| 0x10 | 4 | Loop start sample |
| 0x14 | 4 | Number of samples |
| 0x18 | 4 | Version 0x10100: Reserved (always 0)<br>Version 0x10200: Adjusted loop start sample (see below) |
| 0x1C | 4 | Number of channels (up to 2) |
| 0x20 | | [References] to [channel info](#channel-info) (0x7100), relative to 'number of channels' field. |

The adjusted loop start sample is always less than the real loop start sample. If the adjusted loop start sample is X less than the real loop start sample, the last X samples of the wave file are skipped when the wave file is looped.

### Sample Format
| Value | Description |
| --- | --- |
| 0 | 8-bit |
| 1 | 16-bit |
| 2 | ADPCM |

### Channel Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] into [data block](#data-block) (0x1F00) |
| 0x8 | 8 | [Reference] to [DSP ADPCM info](#dsp-adpcm-info) (0x0300) |
| 0x10 | 4 | Unused (always 0) |

#### DSP ADPCM Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 * 2 | ADPCM coefficients |
| 0x20 | 6 | [ADPCM context](#adpcm-context) (main) |
| 0x26 | 6 | [ADPCM context](#adpcm-context) (loop) |
| 0x28 | 2 | Unused (always 0) |

#### ADPCM Context
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Initial header byte |
| 0x2 | 2 | Initial hist 1 |
| 0x4 | 2 | Initial hist 2 |

## Data Block
This block contains the actual sound data.

In version 0x10100, the sound data is aligned to 32 bytes. In version 0x10200, it is aligned to 64 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("DATA") |
| 0x4 | 4 | Block size |
| 0x8 | | Sound data |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id