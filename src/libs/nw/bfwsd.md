## [NW](../../formats.md#nw) > [Sound](./sound.md) > Wave Sound (FWSD)

| Block id | Description |
| --- | --- |
| `0x6800` | [Info block](#info-block) |

## Info Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | 8 | [Reference] to [wave id table](./sound.md#wave-id-table) (0x0100) |
| 0x10 | 8 | [Reference] to [wave sound data reference table](#wave-sound-data-reference-table) (0x0101) |

### Wave Sound Data Reference Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] to [wave sound data](#wave-sound-data) (0x4900) |

### Wave Sound Data
| Offset | Size | Description |
| --- | --- |---|
| 0x0 | 8 | [Reference] to [wave sound info](#wave-sound-info) (0x4901) |
| 0x8 | 8 | [Reference] to [track info reference table] (0x0101) |
| 0x10 | 8 | [Reference] to [note info reference table](#note-info-reference-table) (0x0101) |"

### Wave Sound Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | 0x0000XXYY: XX = Surround pan, YY = Pan |
| 0x2 | Pitch (float) |
| 0x4 | 0x00XXYYZZ: XX = Biquad value, YY = Biquad type, ZZ = Low pass filter frequency |
| 0x100 | Send value (4x1 byte) offset |
| 0x200 | Offset to [reference] to [adshr curve](./sound.md#adshr-curve) (0x0000) |

### Track Info Reference Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] to [track info](#track-info) (0x4903) |

#### Track Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] to [note event reference table](#note-event-reference-table) (0x0000) |

##### Note Event Reference Table
| Offset | Size | Description |
| --- | --- |---|
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] to [note event](#note-event) (0x4904) |

###### Note Event
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Position (Float) |
| 0x4 | 4 | Length (Float) |
| 0x8 | 4 | [Note info](#note-info) index |

### Note Info Reference Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of entries |
| 0x4 | | [References] to [note info](#note-info) (0x4902) |

#### Note Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Index into wave id table |
| 0x4 | 4 | Flags. This field specifies which of the following fields is present. |

Every optional field takes up exactly 4 bytes (if present).

| Flag | Description |
| --- | --- |
| 0x1 | Original key |
| 0x2 | Volume |
| 0x4 | 0x0000XXYY: XX = Surround pan, YY = Pan |
| 0x8 | Pitch (float) |
| 0x200 | Offset to [reference] to [adshr curve](./sound.md#adshr-curve) (0x0000) |

[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id
