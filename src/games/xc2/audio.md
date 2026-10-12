## [XC 2](../../formats.md#xc2) > Audio Files

This page describes the `.nop` (Nintendo OPus) file format, which is based on the opus format but with a custom header.

The audio stream uses VBR (Variable Bit Rate) encoding.

A frame is the work unit of this file format. Each frame is 20 ms long and contains 960 samples.

To play these files, you can use [Foobar2000](https://www.foobar2000.org/) with the [VGMstream plugin](https://vgmstream.org/) or the [VGMstream website](https://katiefrogs.github.io/vgmstream-web/) directly.

| Offset | Size | Description                  |
| ---    | ---  | ---                          |
| 0x0    | 0x60 | [File Header](#file-header)  |
| 0x60   | 0x20 | Padding                      |
| 0x80   | ?    | [Index Table](#index-table)  |
| ?	     | 0x28 | [Opus Header](#opus-header)  |
| ?      | ?    | [Opus Stream](#opus-stream)  |

## File Header

| Offset | Size | Description |
| ---    | ---  | --- |
| 0x0    | 4    | Always `"sadf"` |
| 0x4    | 4    | File size |
| 0x8    | 4    | Always `"opus"` |
| 0xC    | 4    | Always 1 |
| 0x10   | 4    | Always `"head"` |
| 0x14   | 4    | Index table offset (`0x80`) |
| 0x18   | 4    | Channel count (1 or 2) |
| 0x1C   | 4    | Opus stream offset |
| 0x20   | 4    | Opus stream length (excluding padding) |
| 0x24   | 4    | Sample rate (48,000 Hz) |
| 0x28   | 4    | Number of samples (960)|
| 0x2C   | 4    | Unknown (always 0?) |
| 0x30   | 4    | Number of samples (bis) |
| 0x34   | 4    | Opus stream length (excluding padding, bis) |
| 0x38   | 4    | Unknown (always 0?) |
| 0x3C   | 4    | Unknown (always 0?) |
| 0x40   | 4    | Unknown (64,000 or 96,000) |
| 0x44   | 4    | Unknown (20,000) |
| 0x48   | 4    | Unknown (always 0?) |
| 0x4C   | 4    | Number of frames |
| 0x50   | 4    | Number of frames (bis) |
| 0x54   | 4    | Index table offset (bis, `0x80`) |
| 0x58   | 4    | Total length of the index table |
| 0x5C   | 4    | Unknown (always 0?) |
| 0x60   | 32   | Padding |

## Index Table

The size of a frame can be determined by calculating the difference between two consecutive offsets.

| Offset | Size | Description |
| ---    | ---  | ---         |
| 0x80   | 4    | `28 00 00 00` Start of the index table / Opus header length
| 0x??   | 4    | The last 4 bytes give the opus length, excluding opus padding |
| 0x??   | 4 / 8 / 12 | Padding (`E8 E8 E8 E8` ...) |

The index table is padded with `0xE8` until its size is a multiple of 16 bytes

## Opus Header
The offsets below are relative to the start of the Opus header for simplicity.

| Offset | Size | Description | 
| ---    | ---  | ---         |
| 0x0    | 4    | `01 00 00 80` Unknown |
| 0x4    | 4    | `18 00 00 00` Unknown |
| 0x8    | 1    | Unknown |
| 0x9    | 1    | 1 = Mono, 2 = Stereo |
| 0xA    | 2    | Unknown |
| 0xC    | 4    | Sample rate (48,000 Hz) |
| 0x10   | 4    | `20 00 00 00` Unknown |
| 0x14   | 4    | `00 00 00 00` 0 |
| 0x18   | 4    | `00 00 00 00` 0 |
| 0x1C   | 4    | `78 00 00 00` Unknown |
| 0x20   | 4    | `04 00 00 80` Unknown |
| 0x24   | 4    | Length of the file's rest (excluding padding) |

The index table is padded with `0xE8` until its size is a multiple of 16 bytes
	
## Opus Stream

This is the structure of a single frame.

| Offset | Size | Description |
| ---    | ---  | --- |
| 0x0    | 4    | Frame data size |
| 0x4    | 4    | Frame checksum |
| 0x8    | 1    | Frame data |

Frame data starts with the byte `FC`.

`00 00 00 03 01 00 00 00 FC FF FE` = 1 frame of silence, may vary slightly.

To find a frame, locate the end of the index table and skip the opus header. Take note of the four following bytes, then skip the frame checksum. Read the subsequent bytes until the number of bytes matches the recorded frame length.

All `.nop` files are padded with null bytes (`0x00`) until its size is a multiple of 16 bytes (This padding is included in the .nop file size but is not part of the Opus stream).