## [XB 2](../../formats.md#xb2) > Audio Files

Each offset is 4 hexa bytes

| Offset | Size | Description                 |
| ---  | ---  | ---                           |
| 0x0  | 0x60 | [File Header](#file-header)   |
| 0x60 | 0x20 | Padding                       |
| 0x80 | 0x?  | [Seek Table](#seek-table)     |
| 0x?  | 0x?  | [Audio Stream](#audio-stream) |

A frame is the work unit for the file format. 1 frame is 20ms (0,02s / 20ms) and 960 samples

The audio duration **(in ms)** can be guessed by these formulas :
* *number of **samples** / sample **rate** = x / 48 000*
* *number of **frames** / sample **duracy** = x / 0,02*

## File Header
| Offset | Value | Description |
| --- | ---         | --- |
|0x00  | 73 61 64 66	| sadf |
|0x04  | ?? ?? ?? ??	| file size / total number of bytes |
|0x08  | 6F 70 75 73	| opus |
|0x0c  | 01 00 00 00	| ??? |
||||
| 0x10 | 68 65 61 64 | head |
| 0x14 | 80 00 00 00 | seek table position |
| 0x18 | 0? 00 00 00 | 1 or 2 = channel count |
| 0x1c | ?? ?? ?? ?? | raw opus start position |
||||
| 0x20 | ?? ?? ?? ?? | raw opus length (without padding) |
| 0x24 | 80 BB 00 00 | 48 000 Hz sample rate |
| 0x28 | ?? ?? ?? ?? | number of samples |
| 0x2c | 00 00 00 00 | loop start |
||||
| 0x30 | ?? ?? ?? ?? | number of samples (bis) / loop end  |
| 0x34 | ?? ?? ?? ?? | raw opus length (without padding) (bis) |
| 0x38 | 00 00 00 00 | 0 |
| 0x3c | 00 00 00 00 | 0 |
||||
| 0x40 | ...         |  |
| 0x44 | 20 4E 00 00 | 20 000 = ??? |
| 0x48 | 00 00 00 00 | 0 |
| 0x4c | ?? ?? ?? ?? | number of frames (without the first and last word of seek table so it’s X-2) |
||||
| 0x50 | ?? ?? ?? ?? | number of frames (bis) |
| 0x54 | 80 00 00 00 | seek table position (bis) |
| 0x58 | ?? ?? ?? ?? | total lenght of the seek table |
| 0x5c | 00 00 00 00 | 0 |

32 bytes empty from 0x60 to 0x7F

## Seek Table

Frame size N = frame N+1 offset - frame N offset

The difference between 2 offsets consecutives give the byte lenght of an audio packet.

| Offset | Value     | Description |
| ---    | ---          | --- |
| 0x80   | 28 00 00 00 | payload’s header lenght / seek table start
| 0x??   | ?? ?? ?? ?? | the last “hexa word” give the payload length without the payload’s padding (the empties bytes at the end of the file) |
| 0x??   | E8 E8 E8 E8 | seek table’s padding |

## Opus Header
###### (first frame, offset is reset for simplicity)
| Offset | Value       | Description | 
| ---    | ---         | --- |
| 0x00   | 01 00 00 80 | magic |
| 0x04   | 18 00 00 00 | ??? |
| 0x08   | 00 01 00 00 | mono |
| 0x08 *(bis)* | 00 02 00 00 | stéréo|
| 0x0c   | 80 BB 00 00 | 48 000 sample rate |
| 0x10   | 20 00 00 00 | ??? |
| 0x14   | 00 00 00 00 | 0 |
| 0x18   | 00 00 00 00 | 0 |
| 0x1c   | 78 00 00 00 | 120 = ? |
| 0x20   | 04 00 00 80 | ? |
| 0x24   | ?? ?? ?? ?? | length of the file’s rest (without the padding) |

## raw “payload”

00 00 00 03 01 00 00 00 FC FF FE = 1 frame of silence, can vary a little

00 00 ?? ?? = frame length (Big Endian)

?? ?? ?? ?? = metadata ?

?? = config byte

To find a frame, search 00 00 after the first frame, then note the two following values, skip 4 bytes. Now, select the bytes until you see another 00 00. If the length corresponds to the value : it's a frame !