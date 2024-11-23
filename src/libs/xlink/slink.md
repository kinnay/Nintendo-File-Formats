## [ELINK](../../formats.md#xlink) > Sound Links

This page describes version 0x45 of the file format. Everything is encoded in big-endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`SLNK`) |
| 0x4 | 4 | File size |
| 0x8 | 4 | Version number |
| 0xC | 4 | Number of resources (N) |
| 0x10 | 4 * N | Offsets to resources |
| | | String table |
| | | Resources |

When a field is marked as 'reserved', its value does not matter. These fields are overwritten at runtime. Unless indicated otherwise, reserved fields are set to 0 in official files.

## Resource
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 4 | Resource size |
| 0x8 | 4 | Name (offset into string table) |
| 0xC | 4 | Number of sound call tables (P) |
| 0x10 | 4 | Number of action call tables (Q) |
| 0x14 | 4 | Number of sounds (R) |
| 0x18 | 4 | Number of actions (S) |
| 0x1C | 4 | Reserved for string table pointer<br>Set to `resource size - 4` in official files |
| 0x20 | 4 | Unknown (float) |
| 0x24 | 4 | Unknown (float) |
| 0x28 | 4 | Unknown (float) |
| 0x2C | 4 | Unknown (float) |
| 0x30 | 20 * P | Sound call tables |
| | 20 * Q | Action call tables |
| | 92 * R | Sounds |
| | 76 * S | Actions |
| | 4 | Always 0 |

### Call Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (offset into string table) |
| 0x4 | 4 | Reserved for name pointer |
| 0x8 | 4 | Reserved for name hash |
| 0xC | 1 | Unknown |
| 0xD | 1 | Select by properties |
| 0xE | 1 | Select randomly |
| 0xF | 1 | Unknown |
| 0x10 | 2 | First index |
| 0x12 | 2 | Last index |

### Sound
Every sound is referenced by exactly one [call table](#call-table).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index |
| 0x4 | 4 | Reserved for call table pointer |
| 0x8 | 4 | Property name 1 (offset into string table) |
| 0xC | 4 | Property id 1 |
| 0x10 | 4 | Property name 2 (offset into string table) |
| 0x14 | 4 | Property id 2 |
| 0x18 | 4 | Sound name in [BFSAR](../nw/bfsar.md) (offset into string table) |
| 0x1C | 4 | Reserved for [item id](../nw/sound.md#item-id) |
| 0x20 | 4 | Filename (offset into string table) |
| 0x24 | 4 | Reserved for filename pointer |
| 0x28 | 4 | Minimum volume (float) |
| 0x2C | 4 | Maximum volume (float) |
| 0x30 | 4 | Minimum pitch (float) |
| 0x34 | 4 | Maximum pitch (float) |
| 0x38 | 4 | Minimum lpf (float) |
| 0x3C | 4 | Maximum lpf (float) |
| 0x40 | 4 | Minimum pan (float) |
| 0x44 | 4 | Maximum pan (float) |
| 0x48 | 4 | Minimum surround pan (float) |
| 0x4C | 4 | Maximum surround pan (float) |
| 0x50 | 2 | Minimum delay |
| 0x52 | 2 | Maximum delay |
| 0x54 | 4 | Name of bone to follow (offset into string table) |
| 0x58 | 1 | Is hold |
| 0x59 | 1 | Is follow |
| 0x5A | 1 | Use property id instead of name |
| 0x5B | 1 | Unknown |

### Action
Every action is referenced by exactly one [call table](#call-table).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index |
| 0x4 | 4 | Reserved for action call table pointer |
| 0x8 | 4 | Sound call table index |
| 0xC | 4 | Reserved for sound call table pointer |
| 0x10 | 8 | Unknown |
| 0x18 | 2 | Flags:<br>4 = is follow<br>8 = is hold |
| 0x1A | 2 | Unknown |
| 0x1C | 4 | Minimum volume (float) |
| 0x20 | 4 | Maximum volume (float) |
| 0x24 | 4 | Minimum pitch (float) |
| 0x28 | 4 | Maximum pitch (float) |
| 0x2C | 4 | Minimum lpf (float) |
| 0x30 | 4 | Maximum lpf (float) |
| 0x34 | 4 | Minimum pan (float) |
| 0x38 | 4 | Maximum pan (float) |
| 0x3C | 4 | Minimum surround pan (float) |
| 0x40 | 4 | Maximum surround pan (float) |
| 0x44 | 2 | Minimum delay |
| 0x46 | 2 | Maximum delay |
| 0x48 | 4 | Unknown |
