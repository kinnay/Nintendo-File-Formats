## [XC 2](../../formats.md#xc2) > Audio Files

This page describes the `.nop` (Nintendo OPus) file format, which is based on the opus format but with a custom header.

The file is encoded with little endian byte order.

To listen to these files, you can use [Foobar2000](https://www.foobar2000.org/) with the [VGMstream plugin](https://vgmstream.org/) or the [VGMstream website](https://katiefrogs.github.io/vgmstream-web/) directly.

| Offset | Size | Description                  |
| ---    | ---  | ---                          |
| 0x0    | 0x60 | [File Header](#file-header)  |
| 0x60   | 0x20 | Padding                      |
| 0x80   | ?    | [Seek Table](#seek-table)    |
| ?	     | 0x28 | [Opus Header](#opus-stream)  |
| ?      | ?    | [Opus Stream](#audio-stream) |

A frame is the work unit for the file format. One frame is 20 ms and approximately 960 samples

## File Header

| Offset | Size | Description |
| ---    | ---  | --- |
| 0x0    | 4    | Always `"sadf"` |
| 0x4    | 4    | File size |
| 0x8    | 4    | Always `"opus"` |
| 0xC    | 4    | Always 1 |
| 0x10   | 4    | Always `"head"` |
| 0x14   | 4    | Seek table position (`0x80`) |
| 0x18   | 4    | Channel count (1 or 2) |
| 0x1C   | 4    | Raw opus start position |
| 0x20   | 4    | Raw opus length (without padding) |
| 0x24   | 4    | Sample rate (e.g. 48 000 Hz) |
| 0x28   | 4    | Number of samples |
| 0x2C   | 4    | Loop start |
| 0x30   | 4    | Number of samples (bis) / loop end  |
| 0x34   | 4    | Raw opus length (without padding) (bis) |
| 0x38   | 4    | Unknown (always 0?) |
| 0x3C   | 4    | Unknown (always 0?) |
| 0x40   | 4    | Unknown (64,000 or 96,000) |
| 0x44   | 4    | Unknown (20,000) |
| 0x48   | 4    | Unknown (always 0?) |
| 0x4C   | 4    | Number of frames (without the first and last 4 bytes of seek table so it's X-2) |
| 0x50   | 4    | Number of frames (bis) |
| 0x54   | 4    | Seek table position (bis) (`0x80`) |
| 0x58   | 4    | Total length of the seek table |
| 0x5C   | 4    | Always 0? |
| 0x60   | 32   | Padding  |

## Seek Table

The size of a frame can be determined by calculating the difference between two consecutive offsets.

| Offset | Size | Description |
| ---    | ---  | ---         |
| 0x80   | 4    | `28 00 00 00` Payload's header length / seek table start
| 0x??   | 4    | The last 4 bytes give the payload length without the payload's padding |
| 0x??   |  | Padding (`E8 E8 E8 E8` ...) |

The seek table is padded with `0xE8` until its size is a multiple of 16 bytes

## Opus Header
(first frame, offset is reset for simplicity)

| Offset | Size | Description | 
| ---    | ---  | ---         |
| 0x0    | 4    | `01 00 00 80` magic |
| 0x4    | 4    | `18 00 00 00` = ? |
| 0x8    | 1    | Unknown |
| 0x9    | 1    | 1 = Mono, 2 = Stereo |
| 0xA    | 2    | Unknown |
| 0xC    | 4    | Sample rate (e.g. 48,000) |
| 0x10   | 4    | `20 00 00 00` = ? |
| 0x14   | 4    | `00 00 00 00` 0 |
| 0x18   | 4    | `00 00 00 00` 0 |
| 0x1C   | 4    | `78 00 00 00` = 120 : ? |
| 0x20   | 4    | `04 00 00 80` ? |
| 0x24   | 4    | Length of the file's rest (without the padding) |

## Opus Stream

| Offset | Size | Description |
| --- | ---  | --- |
| 0x0 | 4    | Frame length (big endian) |
| 0x4 | 4    | Metadata ? |
| 0x8 | 2    | Config byte |

`00 00 00 03 01 00 00 00 FC FF FE` = 1 frame of silence, can vary a little

To find a frame, search for `00 00` after the first frame, take note of the two following values, skip 4 bytes. Now, select the bytes until you see another 00 00. If the length corresponds to the value, it's a frame!

Every opus stream is padded will null bytes until its size is a multiple of 16 bytes