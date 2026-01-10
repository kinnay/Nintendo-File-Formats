## [SMM](../../formats.md#smm) > Level Files

A Super Mario Maker level consists of the following files:

* [`course_data.cdt`](#course-data) (Main area)
* [`course_data_sub.cdt`](#course-data) (Sub area)
* `sound.bwv` (Unknown)
* [`thumbnail0.tnl`](#thumbnails) (Long thumbnail)
* [`thumbnail1.tnl`](#thumbnails) (Small thumbnail)

Both `course_data.cdt` and `course_data_sub.cdt` contain exactly `0x15000` bytes and use the same format.

## Course Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Unknown |
| 0x8 | 4 | CRC32 of file from offset 0x10 until the end |
| 0xC | 4 | Unknown |
| 0x10 | 2 | Last modification year |
| 0x12 | 1 | Last modification month |
| 0x13 | 1 | Last modification day |
| 0x14 | 1 | Last modification hour |
| 0x15 | 1 | Last modification minute |
| 0x16 | 4 | Unknown |
| 0x1A | 6 | Last 12 digits of [level id](https://github.com/kinnay/NintendoClients/wiki/Data-Store-Codes#super-mario-maker) |
| 0x20 | 1 | Is downloaded level (0 or 1) |
| 0x21 | 1 | Previously removed level from servers (0 or 1) |
| 0x22 | 5 | Unknown |
| 0x27 | 1 | [Physics version](#physics-version) |
| 0x28 | 64 | Level name (UTF-16) |
| 0x68 | 2 | Unknown |
| 0x6A | 2 | Level style (`M1`, `M3`, `MW` or `WU`) |
| 0x6C | 1 | Unknown |
| 0x6D | 1 | [Level theme](#level-theme) |
| 0x6E | 1 | Uploaded level to servers (0 or 1) |
| 0x6F | 1 | Clear check level status (0 or 1) |
| 0x70 | 2 | Level timer |
| 0x72 | 1 | Level scroll (0 = None, 1 = Slow, 2 = Normal, 3 = Fast) |
| 0x73 | 5 | Unknown |
| 0x78 | 96 | [Mii data](https://github.com/kinnay/NintendoClients/wiki/Mii-Data-(Wii-U)) |
| 0xD8 | 3 | Unknown |
| 0xDB | 1 | Mii country flag (for downloaded levels, see table [here](https://github.com/NobleD4/MARIO-MAKER-D4TA-EDITOR/blob/master/README.md)) |
| 0xDC | 44 | Unknown |
| 0x108 | 83176 | Space reserved for object/items/enemies |
| 0x145F0 | 2400 | Space reserved for sound effects |
| 0x14F50 | 176 | Unknown |

The following repositories provide more information about placing objects:
* [MarioUnmaker](https://github.com/Treeki/MarioUnmaker/blob/master/FormatNotes.md)
* [PointlessMaker](https://github.com/aboood40091/PointlessMaker)

### Physics Version
This field specifies the version of the physics engine. The older the version, the less patches have been applied.

| Value | Version |
| --- | --- |
| 0 | 1.00 |
| 1 | 1.20 |
| 2 | 1.30 |
| 3 | 1.43 |
| 4 | 1.44 |
| 5 | 1.45 |
| 6 | 1.46 |
| 7 | 1.47 |

### Level Theme
| Value | Theme |
| --- | --- |
| 0 | Ground |
| 1 | Underground |
| 2 | Castle |
| 3 | Airship |
| 4 | Underwater |
| 5 | Ghost house |

## Thumbnails
Level thumbnails are saved with a `.tnl` extension. A `.tnl` file always has a size of `0xC800` bytes. It is a wrapper around the JPEG format. More details about the format can be found [here](https://gist.github.com/RoadrunnerWMC/33c28d6d13b411f1e55471936d36c990).

* `thumbnail0.tnl` contains an overview of the whole level. Its maximum resolution is 720 x 80 pixels (the width can be smaller).
* `thumbnail1.tnl` contains a picture of the initial screen. Its resolution is 320 x 240 pixels.