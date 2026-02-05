## [XB 2](../../formats.md#xb2) > Audio Files

.nop (Nintendo OPus) is based on the opus format with a custom header made by Nintendo.

| Offset | Size | Description                  |
| ---    | ---  | ---                          |
| 0x0    | 0x60 | [File Header](#file-header)  |
| 0x60   | 0x20 | Padding                      |
| 0x80   | 0x?  | [Seek Table](#seek-table)    |
| 0x?	 | 0x?  | [Opus Header](#opus-stream)  |
| 0x?    | 0x?  | [Opus Stream](#audio-stream) |

A frame is the work unit for the file format. 1 frame is 20ms (0,02s / 20ms) and approximatively 960 samples

The audio duration **(in ms)** can be guessed by these formulas :
* *number of **samples** / sample **rate** = x / 48 000*
* *number of **frames** / sample **duration** = x / 0,02*

## File Header
| Offset | Size | Value       | Description |
| ---    | ---  | ---         | ---   |
|0x00    | 4    | 73 61 64 66 | Sadf |
|0x04    | 4    | ?? ?? ?? ?? | File size / total number of bytes |
|0x08    | 4    | 6F 70 75 73 | Opus |
|0x0c    | 4    | 01 00 00 00 | ??? |
|||||
| 0x10   | 4    | 68 65 61 64 | Head |
| 0x14   | 4    | 80 00 00 00 | Seek table position |
| 0x18   | 4    | 0? 00 00 00 | 1 or 2 = channel count |
| 0x1c   | 4    | ?? ?? ?? ?? | Raw opus start position |
||||
| 0x20   | 4    | ?? ?? ?? ?? | Raw opus length (without padding) |
| 0x24   | 4    | 80 BB 00 00 | 48 000 Hz sample rate |
| 0x28   | 4    | ?? ?? ?? ?? | Number of samples |
| 0x2c   | 4    | 00 00 00 00 | Loop start |
||||
| 0x30   | 4    | ?? ?? ?? ?? | Number of samples (bis) / loop end  |
| 0x34   | 4    | ?? ?? ?? ?? | Raw opus length (without padding) (bis) |
| 0x38   | 4    | 00 00 00 00 | 0 |
| 0x3c   | 4    | 00 00 00 00 | 0 |
||||
| 0x40   | 4    | 00 FA 00 00 or 00 77 01 00 | 64 000 or 96 000 |
| 0x44   | 4    | 20 4E 00 00 | 20 000 = ??? |
| 0x48   | 4    | 00 00 00 00 | 0 |
| 0x4c   | 4    | ?? ?? ?? ?? | Number of frames (without the first and last 4 bytes of seek table so it's X-2) |
||||
| 0x50   | 4    | ?? ?? ?? ?? | Number of frames (bis) |
| 0x54   | 4    | 80 00 00 00 | Seek table position (bis) |
| 0x58   | 4    | ?? ?? ?? ?? | Total length of the seek table |
| 0x5c   | 4    | 00 00 00 00 | 0 |

32 bytes empty from 0x60 to 0x7F

## Seek Table

Frame size N = frame N+1 offset - frame N offset

The difference between 2 offsets consecutives give the byte length of an audio packet.

| Offset | Size | Value       | Description |
| ---    | ---  | ---         | --- |
| 0x80   | 4    | 28 00 00 00 | Payload's header length / seek table start
| 0x??   | 4    | ?? ?? ?? ?? | The last 4 bytes give the payload length without the payload's padding (the empties bytes at the end of the file) |
| 0x??   | 4    | E8 E8 E8 E8 | Seek table's padding |

## Opus Header
###### (first frame, offset is reset for simplicity)
| Offset | Size |Value        | Description | 
| ---    | ---  | ---         | --- |
| 0x00   | 4    | 01 00 00 80 | magic |
| 0x04   | 4    | 18 00 00 00 | ??? |
| 0x08   | 4    | 00 01 00 00 or 00 02 00 00 | Mono / Stereo |
| 0x0c   | 4    | 80 BB 00 00 | 48 000 sample rate |
| 0x10   | 4    | 20 00 00 00 | ??? |
| 0x14   | 4    | 00 00 00 00 | 0 |
| 0x18   | 4    | 00 00 00 00 | 0 |
| 0x1c   | 4    | 78 00 00 00 | 120 = ? |
| 0x20   | 4    | 04 00 00 80 | ? |
| 0x24   | 4    | ?? ?? ?? ?? | Length of the file's rest (without the padding) |

## Opus Stream

00 00 00 03 01 00 00 00 FC FF FE = 1 frame of silence, can vary a little

00 00 ?? ?? = frame length (Big Endian)

?? ?? ?? ?? = metadata ?

?? = config byte

To find a frame, search 00 00 after the first frame, then note the two following values, skip 4 bytes. Now, select the bytes until you see another 00 00. If the length corresponds to the value : it's a frame !