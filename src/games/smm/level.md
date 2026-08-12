## [SMM](../../formats.md#smm) > Level Files

A Super Mario Maker level consists of the following files:

* [`course_data.cdt`](#course-data) (Main area)
* [`course_data_sub.cdt`](#course-data) (Sub area)
* [`sound.bwv`](#sound) (Unknown functionality)
* [`thumbnail0.tnl`](#thumbnails) (Entire thumbnail)
* [`thumbnail1.tnl`](#thumbnails) (One screen thumbnail)
Both `course_data.cdt` and `course_data_sub.cdt` contain exactly `0x15000` bytes and use the same format.

## Course Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Assumed to be a version number or a way to the game to valitate the file. Always 0xB right now |
| 0x8 | 4 | CRC32 of file from offset 0x10 until the end |
| 0xC | 4 | Padding |
| 0x10 | 2 | Last modification year |
| 0x12 | 1 | Last modification month |
| 0x13 | 1 | Last modification day |
| 0x14 | 1 | Last modification hour |
| 0x15 | 1 | Last modification minute |
| 0x16 | 1 | Unknown |
| 0x17 | 1 | [Official course](#official-course) (for levels with downloaded status true) |
| 0x18 | 2 | Unknown |
| 0x1A | 6 | Last 12 digits of [level ID](https://github.com/kinnay/NintendoClients/wiki/Data-Store-Codes#super-mario-maker) (if it's filled with zeros, other values like Official course or Mii data won't show in game) |
| 0x20 | 1 | Is downloaded level (0 or 1) |
| 0x21 | 1 | Previously removed level from servers (0 or 1) |
| 0x22 | 5 | Unknown |
| 0x27 | 1 | [Game version](#game-version) (physics) |
| 0x28 | 64 | Level name (UTF-16) |
| 0x68 | 2 | Unknown |
| 0x6A | 2 | Game style (`M1`, `M3`, `MW` or `WU`) |
| 0x6C | 1 | Unknown |
| 0x6D | 1 | [Level theme](#level-theme) |
| 0x6E | 1 | Uploaded level to servers (0 or 1) |
| 0x6F | 1 | Clear check level status (0 or 1) |
| 0x70 | 2 | Level timer |
| 0x72 | 1 | Level scroll (0 = None, 1 = Slow, 2 = Medium, 3 = Fast) |
| 0x73 | 1 | Unknown |
| 0x74 | 4 | Level length (minimum: 0x00000180, maximum: 0x00000F00 and increases/decreases by 0x10) |
| 0x78 | 96 | Space reserved for [Mii data](https://github.com/kinnay/NintendoClients/wiki/Mii-Data-(Wii-U)) (for levels with downloaded status true) |
| 0xD8 | 4 | Signed integer value for Mii country flag (for levels with downloaded status true, see table [here](https://github.com/NobleD4/MARIO-MAKER-D4TA-EDITOR/blob/master/README.md)) |
| 0xDC | 4 | Unknown |
| 0xE0 | 12 | Padding |
| 0xEC | 4 | Objects/items/enemies count |
| 0x108 | 83176 | Space reserved for objects/items/enemies |
| 0x145F0 | 2400 | Space reserved for sound effects |
| 0x14F50 | 176 | Padding |

The following repositories provide more information about placing objects:
* [MarioUnmaker](https://github.com/Treeki/MarioUnmaker/blob/master/FormatNotes.md)
* [PointlessMaker](https://github.com/aboood40091/PointlessMaker)
* [MetaMaker](https://github.com/RoadrunnerWMC/Metamaker)

### Official Course
| Value | Maker |
| --- | --- |
| 0x0 | None |
| 0x1 | Mary O. |
| 0x2 | Yamamura |
| 0x3 | Mr. Eraser |
| 0x4 | Undodog |
| 0x5 | Bowser |
| 0x6 | Coursebot |
| 0x7 | Parakeet |
| 0x8 | Soundfrog |
| 0x1D | Event Course |

### Game Version
This field specifies the game version of the physics engine. The older the version, the less patches have been applied.

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

## Sound
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Assumed to be a  way to the game to valitate the file. Always `0x76`, `0x24`, `0x6A`, `0xAE` |
| 0x4 | 55,300 | Unknown, but always filled with zeros |

## Thumbnails
Level thumbnails are saved with a `.tnl` extension. A `.tnl` file always has a size of `0xC800` bytes. It is a wrapper around the JPEG format. More details about the format can be found [here](https://gist.github.com/RoadrunnerWMC/33c28d6d13b411f1e55471936d36c990).

* `thumbnail0.tnl` contains an overview of the whole level. Its maximum resolution is 720 x 80 pixels (the width can be smaller).
* `thumbnail1.tnl` contains a picture of the initial screen. Its resolution is 320 x 240 pixels.
