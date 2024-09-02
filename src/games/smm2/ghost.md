## [SMM 2](../../formats.md#smm2) > Ninji Ghosts

Ninji ghosts are downloaded from the [server](https://github.com/Kinnay/NintendoClients/wiki) with the [GetEventCourseGhost](https://github.com/Kinnay/NintendoClients/wiki/Data-Store-Protocol-(SMM-2)) method. Ninji ghosts are zlib compressed and may use up to 0x8000 bytes.

A decompressed ghost always uses exactly 0x24A36 bytes:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x3C | [File header](#file-header) |
| 0x3C | 0x249FA | [Replay frames](#replay-frame) |

## File Header
The header is stored in big endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Version number (always 2) |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Time in milliseconds |
| 0x10 | 4 | Unknown |
| 0x14 | 1 | Unknown |
| 0x15 | 1 | Unknown |
| 0x16 | 2 | Unknown |
| 0x18 | 4 | Unknown |
| 0x1C | 4 | Unknown |
| 0x20 | 4 | Unknown |
| 0x24 | 4 | Unknown |
| 0x28 | 4 | Unknown |
| 0x2C | 4 | Unknown |
| 0x30 | 4 | Unknown |
| 0x34 | 4 | Unknown |
| 0x38 | 4 | Magic number (always `SPGD`) |

## Replay Frame
Replay data is stored in little endian byte order. The replay frames are stored directly after each other, with no padding.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | `0xAB`<br>`A`: Flags<br>`B`: [Player state](#player-state) |
| 0x1 | 2 | X position |
| 0x3 | 2 | Y position |

If `flags & 4`:

| Offset | Size | Description |
| --- | --- | --- |
| 0x5 | 1 | Unknown |

If `flags & 2` but not `flags & 4`:

| Offset | Size | Description |
| --- | --- | --- |
| 0x5 | 1 | Unknown (`X`) |

If `X & 7 != 1`:

| Offset | Size | Description |
| --- | --- | --- |
| 0x6 | 2 | Unknown |

### Player State
| Value | Description |
| --- | --- |
| 0 | Waiting / walking / running |
| 1 | Jumping |
| 2 | Swimming |
| 3 | Climbing |
| 4 | "hipat" |
| 5 | Slipping |
| 6 | "wsld" |
| 7 | Moving through clear pipe (SM3DW) or riding dry bones shell |
| 8 | Cat attack (SM3DW) or riding clown car |
| 9 | Waiting on tree top (SM3DW) or riding lakitu cloud |
| 10 | Riding goomba shoe (SMB1/SMB3), Koopa Troopa car (SM3DW) or Yoshi |
| 11 | Walking cat |