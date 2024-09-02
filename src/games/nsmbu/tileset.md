## [NSMBU](/formats.md#tilesets) > Tilesets

NSMBU tilesets are SARC archives. Self-contained tileset files in the unit folder are Yaz0 compressed. The archive contains the following files (replace '%' by the name of the tileset):

| Filename | Description |
| --- | --- |
| BG_chk/d_bgchk_%.bin | [Collision behavior data](#tile-collision-file) |
| BG_tex/%.gtx | Texture |
| BG_tex/%_nml.gtx | Normal map |
| BG_unt/%.bin | [Tile object layout](#tile-object-layout) |
| BG_unt/%_hd.bin | [Tile objects](#tile-object-file) |

Pa0 tileset files also contain the following animation textures:

| Filename |
| --- |
| belt_conveyor_anime.gtx |
| block_anime.gtx |
| block_anime_L.gtx |
| hatena_anime.gtx |
| hatena_anime_L.gtx |
| tuka_coin_anime.gtx |

## Tile Collision File
This file describes the collision behavior of the tile. It contains one instance of the following struct for every tile:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | `....AA.BCCDDEEEE` |

| Field | Description |
| --- | --- |
| A | Terrain type |
| B | Solidity |
| C | Extra parameters |
| D | [Collision parameters](#collision-parameters-rails) |
| E | [Collision type](#collision-type) |
| `.` | Unknown or unused |

### Collision Type
| Value | Description |
| --- | --- |
| 1 | Rails |
| 2 | Dash coin |
| 3 | Coin |
| 6 | Brick block |
| 14 | Climbable |
| 16 | Pipe |
| 20 | Hanging ledge / climbable wall |

#### Collision Parameters (Rails)
| Value | Description |
| --- | --- |
| 0 | Upslope |
| 1 | Downslope |
| 2 | Top-left corner |
| 3 | Bottom-right corner |
| 4 | Horizontal |
| 5 | Vertical |
| 6 | Blank |
| 7 | Gentle upslope 1 |
| 8 | Gentle upslope 2 |
| 9 | Gentle downslope 1 |
| 10 | Gentle downslope 2 |
| 11 | Steep upslope 1 |
| 12 | Steep upslope 2 |
| 13 | Steep downslope 1 |
| 14 | Steep downslope 2 |
| 15 | 1x1 circle |
| 16 | 2x2 circle 1 |
| 17 | 2x2 circle 2 |
| 18 | 2x2 circle 3 |
| 19 | 2x2 circle 4 |
| 20 | 4x4 circle 1 |
| 21 | 4x4 circle 2 |
| 22 | 4x4 circle 3 |
| 23 | 4x4 circle 4 |
| 24 | 4x4 circle 5 |
| 25 | 4x4 circle 6 |
| 26 | 4x4 circle 7 |
| 27 | 4x4 circle 8 |
| 28 | 4x4 circle 9 |
| 29 | 4x4 circle 10 |
| 30 | 4x4 circle 11 |
| 31 | 4x4 circle 12 |
| 32 | End stop |

## Tile Object Layout File
This file describes which tiles belong to a tile object and its repetition patterns.

## Tile Object File
This file contains an instance of the following struct for each tile object:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Offset into [tile object layout file](#tile-object-layout-file) |
| 0x2 | 1 | Width |
| 0x3 | 1 | Height |
| 0x4 | 2 | Randomization: 0xXY |

### Randomization
| X | Description |
| --- | --- |
| 0 | No restrictions |
| 1 | Tile may not be the same as left or right neighbour |
| 2 | Tile may not be the same as upper or lower neighbour |
| 3 | Tile may not be the same as any neighbour tile |

Y specifies the number of tiles that are chosen from randomly.