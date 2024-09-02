## [AAL](../../formats.md#aal) > Audio Attenuator (BAATN)

This is an audio attenuator file.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("AATN") |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number (1) |
| 0x8 | 4 | Offset to string table |
| 0xC | 5 * 8 | [Curve description](#curve-description) for each [DistanceParamTarget](#distanceparamtarget) |
| 0x34 | 4 | Directivity name (offset into string table) |
| 0x38 | 4 | Culling name (offset into string table) |
| 0x3C | 4 | Is listener enabled |
| 0x40 | 4 | Is occlusion enabled |
| 0x44 | | String table (null-terminated strings) |

## DistanceParamTarget
| Index | Name |
| --- | --- |
| 0 | Volume |
| 1 | EnvFx |
| 2 | Filter |
| 3 | Spread |
| 4 | Priority |

## Curve Description
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (offset into string table). This is the filename without extension. |
| 0x4 | 4 | [Type](#curve-type) |

### Curve Type
| Value | Name | Extension |
| --- | --- | --- |
| 0 | RollOff | [.baroc](./baroc.md) |
| 1 | Custom | [.bactc](./bactc.md) |
| 2 | UnitDistance | [.baudc](./baudc.md) |