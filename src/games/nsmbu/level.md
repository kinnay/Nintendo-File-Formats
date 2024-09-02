## [NSMBU](/formats.md#nsmbu) > Level Files

NSMBU levels are Yaz0 compressed SARC archives. They contain another SARC archive with the same name as the outer archive, and optionally some actor and tileset files. If an actor file isn't found in the level archive it is loaded from the 'actor' folder. Tileset files are loaded from the 'unit' folder if they aren't found in the level archive.

The internal SARC archive contains a 'course' folder with a `course[X].bin` file for each area and a `course[X]_bgdatL[Y].bin` file for each tile layer.

| Table of Contents |
| --- |
| [Area File](#area-file) |
| [Layer File](#layer-file) |

## Area File
This file contains 15 block headers followed by the blocks themselves:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset (relative to start of file) |
| 0x4 | 4 | Size |

### Block 1: Tileset names
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | Pa0 tileset |
| 0x20 | 32 | Pa1 tileset |
| 0x40 | 32 | Pa2 tileset |
| 0x60 | 32 | Pa3 tileset |

### Block 2: Area settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Events activated when area is entered (0-31) |
| 0x4 | 4 | Events activated when zone is entered (32-63) |
| 0x8 | 2 | Flags<br>`0x1`: Wrap across edges |
| 0xA | 2 | Time limit |
| 0xC | 1 | Unknown |
| 0xD | 1 | Unknown |
| 0xE | 1 | Unknown |
| 0xF | 1 | Unknown |
| 0x10 | 1 | Start entrance |
| 0x11 | 1 | Unknown |
| 0x12 | 1 | Unknown |
| 0x13 | 1 | Start entrance for coin battle and boost rush mode |
| 0x14 | 2 | Checkpoint time 1 |
| 0x16 | 2 | Checkpoint time 2 |

### Block 3: Zone boundaries
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Y upper bound |
| 0x4 | 4 | Y lower bound |
| 0x8 | 4 | Y upper bound 2 |
| 0xC | 4 | Y lower bound 2 |
| 0x10 | 2 | Zone bound id |
| 0x12 | 2 | Unknown |
| 0x14 | 8 | Unknown |

### Block 4: Unknown

### Block 5: Background settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Background id |
| 0x2 | 2 | X offset |
| 0x4 | 2 | Y offset |
| 0x6 | 2 | Unknown |
| 0x8 | 16 | Background name |
| 0x18 | 1 | Unknown |
| 0x19 | 1 | Unknown |
| 0x1A | 1 | Unknown |
| 0x1B | 1 | Unknown |

### Block 6: Unknown

### Block 7: Entrances
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | X position |
| 0x2 | 2 | Y position |
| 0x4 | 2 | Camera offset x |
| 0x6 | 2 | Camera offset y |
| 0x8 | 1 | Entrance id |
| 0x9 | 1 | Destination area |
| 0xA | 1 | Destination entrance |
| 0xB | 1 | Type |
| 0xC | 1 | Players that spawn at this entrance (one bit for each player) |
| 0xD | 1 | Zone id |
| 0xE | 1 | Padding |
| 0xF | 1 | Distance between players (0, 1 or 2) |
| 0x10 | 2 | Flags<br>`0x1`: Face left<br>`0x8`: Non-enterable |
| 0x12 | 1 | Baby yoshi entrance |
| 0x13 | 1 | Coin edit entrance order |
| 0x14 | 1 | Path id |
| 0x15 | 1 | Path node index |
| 0x16 | 1 | Transition type |
| 0x17 | 1 | Padding |

#### Transition Type
The screen fades out with the transition mode of the source entrance, and fades in with the transition mode of the destination entrance.

| Transition Mode | Description |
| --- | --- |
| 0 | Default |
| 1 | Fade |
| 2 | Mario face |
| 3 | Circle towards center |
| 4 | Bowser face |
| 5 | Circle towards entrance |
| 6 | Waves (always down) |
| 7 | Waves (down on fadeout, up on fadein) |
| 8 | Waves (up on fadeout, down on fadein) |
| 9 | Mushroom |
| 11 | No transition |

### Block 8: Sprites
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Sprite id |
| 0x2 | 2 | X position |
| 0x4 | 2 | Y position |
| 0x6 | 2 | Event ids |
| 0x8 | 4 | Actor settings |
| 0xC | 4 | Actor settings |
| 0x10 | 1 | Zone id |
| 0x11 | 1 | Layer id |
| 0x12 | 1 | Link id (sometimes used to link sprites with other sprites) |
| 0x13 | 1 | Movement id |
| 0x14 | 1 | Specifies the initial state of some sprites (swoopers and podoboos use this field for example) |
| 0x15 | 3 | Padding |

### Block 9: Loaded sprites
This block contains one entry for each kind of sprite in the area. This allows the game to preload their actor files.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Sprite id |
| 0x2 | 2 | Padding |

### Block 10: Zone settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | X position |
| 0x2 | 2 | Y position |
| 0x4 | 2 | Width |
| 0x6 | 2 | Height |
| 0x8 | 2 | Theme |
| 0xA | 2 | Unknown |
| 0xC | 1 | Zone id |
| 0xD | 1 | Zone bound id |
| 0xE | 1 | Unknown |
| 0xF | 1 | Zoom |
| 0x10 | 1 | Unknown |
| 0x11 | 1 | Visibility |
| 0x12 | 1 | Background id |
| 0x13 | 1 | Unknown |
| 0x14 | 1 | Unknown |
| 0x15 | 1 | Unknown |
| 0x16 | 1 | Music id |
| 0x17 | 1 | Unknown |
| 0x18 | 1 | Unknown |
| 0x19 | 1 | Unknown |
| 0x1A | 2 | Unknown |

### Block 11: Locations
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | X position |
| 0x2 | 2 | Y position |
| 0x4 | 2 | Width |
| 0x6 | 2 | Height |
| 0x8 | 1 | Location id |
| 0x9 | 3 | Padding |

### Block 12: Unknown

### Block 13: Unknown

### Block 14: Paths
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Path id |
| 0x1 | 1 | Unknown |
| 0x2 | 2 | Start node index |
| 0x4 | 2 | Number of nodes |
| 0x6 | 2 | Unknown |
| 0x8 | 4 | Unknown |

### Block 15: Path nodes
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | X position |
| 0x2 | 2 | Y position |
| 0x4 | 4 | Speed (float) |
| 0x8 | 4 | Acceleration (float) |
| 0xC | 2 | Delay |
| 0xE | 2 | Unknown |
| 0x10 | 1 | Unknown |
| 0x11 | 1 | Unknown |
| 0x12 | 1 | Unknown |
| 0x13 | 1 | Unknown |

## Layer File
This file contains an instance of the following struct for each block of tiles:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Type: 0xXYYY. X is the tileset id, Y is the [tile object index](tileset.md#tile-object-file). 0x7FFF is ignored, 0xFFFF marks the end of the file |
| 0x2 | 2 | X position |
| 0x4 | 2 | Y position |
| 0x6 | 2 | Width |
| 0x8 | 2 | Height |
| 0xA | 1 | Type override |
| 0xB | 1 | Padding |
| 0xC | 4 | Padding |

### Type override
When this value is non-zero, the tile is transformed to one of the following tiles, regardless of its real type.

| Value | Tile type |
| --- | --- |
| 0 | 0x430 |
| 1 | 0x830 |
| 2 | 0xC30 |
| 3 | 0x1030 |
| 4 | 0x1430 |
| 5 | 0x1830 |
| 6 | 0x1C30 |
| 7 | 0x2030 |
| 8 | 0x2430 |
| 9 | 0x2830 |
| 10 | 0x2C30 |
| 11 | 0x3430 |
| 12 | 0x31 |
| 13 | 0x431 |
| 14 | 0x831 |
| 15 | 0xC31 |
| 16 | 0x1031 |
| 17 | 0x1431 |
| 18 | 0x1831 |
| 19 | 0x1C31 |
| 20 | 0x2031 |
| 21 | 0x2431 |
| 22 | 0x2831 |
| 23 | 0x2C31 |