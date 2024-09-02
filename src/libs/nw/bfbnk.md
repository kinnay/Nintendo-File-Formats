## [NW](/formats.md#nw) > [Sound Files](./sound.md) > Bank File (FBNK)

This file contains instrument definitions. Every instrument references a [wave file](./bfwav.md) in a [wave archive](./bfwar.md). Bank files are used by [sequence sounds](./bfseq.md).

| Block id | Description |
| --- | --- |
| `0x5800` | [Info block](#info-block) |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 8 | [Reference] to [wave id table](./sound.md#wave-id-table) (0x0100) |
| 0x10 | 8 | [Reference] to [instrument reference table](#instrument-reference-table) (0x0101) |

### Instrument Reference Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] to [instruments](#instrument) (0x5900) |

#### Instrument
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference table](#region-reference-table) for [key regions](#key-region) (0x5901) |

#### Key Region
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference table](#region-reference-table) for [velocity regions](#velocity-region) (0x5902) |

#### Velocity Region
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | Original key |
| 0x2 | Volume |
| 0x4 | Pan |
| 0x8 | Pitch |
| 0x10 | 0x00XXYYZZ: XX = Interpolation type, YY = Key group, ZZ = Ignore note off |
| 0x200 | Offset to [reference] to [adshr curve](./sound.md#adshr-curve) (0x0000) |

### Region Reference Table
Every instrument has a bunch of key regions which are further divided into velocity regions. All note commands in a sequence sound specify a 'key' and 'velocity' value, which ultimately decide which key region and velocity region are chosen.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to region info (0x6000, 0x6001 or 0x6002) |

Type 0x6000 is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to region |

Type 0x6001 is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Region number 1 |
| 0x1 | 1 | Region number 2 |
| | | ... |
| | | Padding to align to 8 bytes |
| | 8 | [Reference] to region 1 |
| | 8 | [Reference] to region 2 |
| | | ... |

Type 0x6002 is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | First region number |
| 0x1 | 1 | Last region number |
| 0x2 | 6 | Padding |
| 0x8 | | [References] to regions |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id