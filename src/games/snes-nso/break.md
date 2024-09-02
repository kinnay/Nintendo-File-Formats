[SNES Online](../../formats.md#snes-nso) > Break Files
---

A break file contains the emulator state from which a game can be resumed. Everything is encoded in little-endian byte order.

Break files are XZ-compressed. After decompression, a break file starts with a [header](#header) which is followed by the [emulator state](#emulator-state).

## Header

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`0xE40D99F3`) |
| 0x4 | 4 | File format version (max 13) |

Version 0 - 6:

| Offset | Size | Description |
| --- | --- | --- |
| 0x8 | 20 | Unknown SHA-1 |
| 0x1C | 20 | Emulator version string |
| 0x30 | 10 | Emulator host (always `NX.64`) |

Version 7 - 12:

| Offset | Size | Description |
| --- | --- | --- |
| 0x8 | 20 | Unknown SHA-1 |
| 0x1C | 20 | Emulator version string |
| 0x30 | 32 | Game name (for example `SuperMarioKart_e`) |
| 0x50 | 10 | Emulator host (always `NX.64`) |

Version 13:

| Offset | Size | Description |
| --- | --- | --- |
| 0x1C | 20 | Emulator version string |
| 0x30 | 32 | Game name (for example `SuperMarioKart_e`) |
| 0x50 | 10 | Emulator host (always `NX.64`) |

## Emulator State
Unknown