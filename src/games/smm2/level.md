## [SMM 2](../../formats.md#smm2) > Level Files

A Super Mario Maker level consists of the following files:

* [`course_data_XXX.bcd`](#file-body)
* `course_thumb_XXX.btl` (One screen thumbnail)
* `course_replay_XXX.dat`

All .bcd files have the same size in Super Mario Maker 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0x5BFC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0x5BFD0 | 0x30 | [Crypto footer](#encryption) |

## Encryption
Details about the encryption algorithm are [described here](encryption.md).

The following integer table is passed to the key generation algorithm:

```python
table = [
	0x7AB1C9D2, 0xCA750936, 0x3003E59C, 0xF261014B,
	0x2E25160A, 0xED614811, 0xF1AC6240, 0xD59272CD,
	0xF38549BF, 0x6CF5B327, 0xDA4DB82A, 0x820C435A,
	0xC95609BA, 0x19BE08B0, 0x738E2B81, 0xED3C349A,
	0x045275D1, 0xE0A73635, 0x1DEBF4DA, 0x9924B0DE,
	0x6A1FC367, 0x71970467, 0xFC55ABEB, 0x368D7489,
	0x0CC97D1D, 0x17CC441E, 0x3528D152, 0xD0129B53,
	0xE12A69E9, 0x13D1BDB7, 0x32EAA9ED, 0x42F41D1B,
	0xAEA5F51F, 0x42C5D23C, 0x7CC742ED, 0x723BA5F9,
	0xDE5B99E3, 0x2C0055A4, 0xC38807B4, 0x4C099B61,
	0xC4E4568E, 0x8C29C901, 0xE13B34AC, 0xE7C3F212,
	0xB67EF941, 0x08038965, 0x8AFD1E6A, 0x8E5341A3,
	0xA4C61107, 0xFBAF1418, 0x9B05EF64, 0x3C91734E,
	0x82EC6646, 0xFB19F33E, 0x3BDE6FE2, 0x17A84CCA,
	0xCCDF0CE9, 0x50E4135C, 0xFF2658B2, 0x3780F156,
	0x7D8F5D68, 0x517CBED1, 0x1FCDDF0D, 0x77A58C94
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 2 | Always 16 |
| 0x6 | 2 | Always 1 |
| 0x8 | 4 | CRC-32 of decrypted [file body](#file-body) |
| 0xC | 4 | Magic number (always `SCDL`) |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x200 | [Course metadata](#course-metadata) |
| 0x200 | 0x2DEE0 | [Course Area](#course-area) Main area |
| 0x2E0E0 | 0x2DEE0 | [Course Area](#course-area) Sub area |

### Course Metadata
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Start Y position |
| 0x1 | 1 | Goal Y position |
| 0x2 | 2 | Goal X position |
| 0x4 | 2 | Level timer |
| 0x6 | 2 | Clear Condition Amount |
| 0x8 | 2 | Last modification year |
| 0xA | 1 | Last modification month |
| 0xB | 1 | Last modification day |
| 0xC | 1 | Last modification hour |
| 0xD | 1 | Last modification minute |
| 0xE | 1 | Custom scroll speed (0 = Slow, 1 = Medium, 2 = Fast) |
| 0xF | 1 | Clear Condition Category (0 = None, 1 = Parts, 2 = Status, 3 = Actions) |
| 0x10 | 4 | Clear Condition CRC32 |
| 0x14 | 4 | [Game version](#game-version) (physics and it's represented on bits in this offset) |
| 0x18 | 4 | [Management flags](#management-flags) |
| 0x1C | 4 | Clear check attempts |
| 0x20 | 4 | Clear check time |
| 0x24 | 4 | Random number seed |
| 0x28 | 8 | Level ID |
| 0x30 | 4 | Clear check [game version](#game-version) (this value is represented in byte) |
| 0x34 | 0xBC | Reserved |
| 0xF0 | 1 | Unknown (usually `0xFF`) |
| 0xF1 | 2 | GameStyle (`M1`, `M3`, `MW`, `WU`, or `3W`) |
| 0xF3 | 1 | Unknown |
| 0xF4 | 0x42 | Level name 32 characters null-terminated (UTF-16) |
| 0x136 | 0xCA | Level description 75 characters with space for 100 null-terminated (UTF-16) |

### Game Version
This field specifies the game version of the physics engine. The older the version, the less patches have been applied.

| Bit/Value | Version |
| --- | --- |
| 0 | 1.0.0 |
| 1 | 1.0.1 |
| 2 | 1.1.0 |
| 3 | 2.0.0 |
| 4 | 3.0.0 |
| 5 | 3.0.1 |

### Management flags
| Bit | Description |
| --- | --- |
| 0 | Needs to be set, but isn't for quest_105 and quest_115 |
| 1 | Has passed clear check |
| 2 | Unknown |
| 3 | Used only for Lesson and Quest courses |
| 4 | Can't upload course |
| 5 | Has clear condition amount |
| 6 | Has chosen sub area orientation |
| 7+ | Unknown |

### Course Area
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x48 | Course Area Header |
| 0x48 | 0x14500 (0x20 * 2600) | Object |
| 0x14584 | 0x4B0 (0x4 * 300) | Sound Effect |
| 0x149F8 | 0x12D4 (0x3C4 * 5) | Snake Block |
| 0x15CCC | 0xE420 (0x124 * 200) | Clear Pipe |
| 0x240EC | 0x348 (0x54 * 10) | Piranha Creeper |
| 0x24434 | 0x1B8 (0x2C * 10) | ! Block |
| 0x245EC | 0x1B8 (0x2C * 10) | Track Block |
| 0x247A4 | 0x3E80 (0x4 * 4000) | Ground |
| 0x28624 | 0x4650 (0xC * 1500) | Track |
| 0x2CC74 | 0x4B0 (0x4 * 300) | Icicle |
| 0x2D124 | 0xDBC | Reserved |

### Course Area Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Theme |
| 0x1 | 1 | Level scroll (0 = None, 1 = Slow, 2 = Medium, 3 = Fast, 4 = Custom) |
| 0x2 | 1 | Boundary Flags (0 = Built Above Line, 1 = Built Under Line) |
| 0x3 | 1 | Orientation (0 = Horizontal, 1 = Vertical) |
| 0x4 | 1 | End Liquid Height |
| 0x5 | 1 | Liquid Mode (0 = Static, 1 = Rising or Falling, 2 = Rising and Falling) |
| 0x6 | 1 | Liquid Speed (0 = None, 1 = Slow, 2 = Medium, 3 = Fast) |
| 0x7 | 1 | Start Liquid Height |
| 0x8 | 4 | Right Boundary |
| 0xC | 4 | Top Boundary |
| 0x10 | 4 | Left Boundary |
| 0x14 | 4 | Bottom Boundary |
| 0x18 | 4 | Is night time (0 or 1) |
| 0x1C | 4 | Object Count |
| 0x20 | 4 | Sound Effect Count |
| 0x24 | 4 | Snake Block Count |
| 0x28 | 4 | Clear Pipe Count |
| 0x2C | 4 | Piranha Creeper Count |
| 0x30 | 4 | ! Block Count |
| 0x34 | 4 | Track Block Count |
| 0x38 | 4 | Reserved |
| 0x3C | 4 | Ground Count |
| 0x40 | 4 | Track Count |
| 0x44 | 4 | Icicle Count |

### Level Theme
| Value | Theme |
| --- | --- |
| 0 | Ground |
| 1 | Underground |
| 2 | Castle |
| 3 | Airship |
| 4 | Underwater |
| 5 | Ghost house |
| 6 | Snow |
| 7 | Desert |
| 8 | Sky |
| 9 | Forest |

The following repositories provide more information about placing objects:
* [SMM2-documentation](https://github.com/liamadvance/smm2-documentation/blob/master/Course%20Format.md)
* [SMM2LevelViewer](https://github.com/JiXiaomai/SMM2LevelViewer)
