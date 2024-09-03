## [AAL](../../formats.md#aal) > Wave Sound (BWAV)

This file contains a wave sound. It is a replacement for the [BFWAV](../nw/bfwav.md) file format in games that use [AAL](../../formats.md#aal).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("BWAV") |
| 0x4 | 2 | Endianness (0xFFFE for little endian) |
| 0x6 | 2 | Version number (1) |
| 0x8 | 4 | Unknown |
| 0xA | 2 | Unknown |
| 0xC | 2 | Number of tracks (N) |
| 0x10 | 0x4C * N | Track info |
| | | Unknown |

Every track info is encoded as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Sample rate |
| 0x8 | 4 | Number of samples (1) |
| 0xC | 4 | Number of samples (2) |
| 0x10 | 40 | Unknown |
| 0x38 | 2 | Unknown |
| 0x3A | 2 | Unknown |
| 0x3C | 16 | Unknown |
