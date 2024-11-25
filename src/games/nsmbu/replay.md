## [NSMBU](../../formats.md#nsmbu) > Replay

A replay file contains recorded button presses. It is used for titles screen replays, super guides and challenge records. This page describes version `1.0.1.64` of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`RPRH`) |
| 0x4 | 4 | Version number |
| 0x8 | 4 | Unknown |
| 0xC | 16 | RNG state |
| 0x1C | 1 | World number |
| 0x1D | 1 | Level number |
| 0x1E | 1 | Area number |
| 0x1F | 1 | Entrance id |
| 0x20 | 1 | Unknown |
| 0x21 | 1 | Unknown |
| 0x22 | 1 | Challenge  id (or -1) |
| 0x23 | 1 | Unknown |
| 0x24 | 2 | Unknown |
| 0x26 | 2 | Unknown |
| 0x28 | 1 | Unknown |
| 0x29 | 1 | Unknown |
| 0x2A | 1 | Unknown |
| 0x2B | 1 | Unknown |
| 0x2C | 16 * 4 | [Initial player states](#player-state) |
| 0x6C | 1 * 3 | Star coins collected |
| 0x6F | 1 | Unknown |
| 0x70 | 1 | Unknown |
| 0x71 | 1 | Unknown |
| 0x72 | 1 | Unknown |
| 0x73 | 1 | Flags:<br>1 = is nabbit chase |
| 0x74 | 1 | Game type (0=normal, 1=boost rush, 2=coin battle, 3=coin edit, 4=challenge) |
| 0x75 | 1 | Coins |
| 0x76 | 2 | Flags:<br>1 = is title screen<br>4 = is boost rush<br>16 = is nslu<br>32 = is edited coin course |
| 0x78 | 4 | Score |
| 0x7C | 1 | Number of deaths (decides if super guide block should appear) |
| 0x7D | 1 | Baby yoshi type (10=bubble, 11=balloon, 14=none) |
| 0x7E | 1 | Unknown |
| 0x7F | 1 | Unknown |
| 0x80 | 4 | Boost rush speed (float) |
| 0x84 | 1 | Unknown |
| 0x85 | 1 | Unknown |
| 0x86 | 1 | Unknown |
| 0x87 | 1 | Unknown |
| 0x88 | | [Replay data](#replay-data) |
| | | CRC32 of replay file |

## Player State
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Is active |
| 0x1 | 1 | Number of lives |
| 0x2 | 1 | Unknown |
| 0x3 | 1 | [Character](#character) |
| 0x4 | 1 | [Powerup](#powerup) |
| 0x5 | 1 | Has star power |
| 0x6 | 1 | Unknown |
| 0x7 | 1 | Unknown |
| 0x8 | 4 | Number of coins |
| 0xC | 1 | Unknown |
| 0xD | 1 | Unknown |
| 0xE | 1 | Unknown |
| 0xF | 1 | Unknown |

## Character
| ID | Character |
| --- | --- |
| 0 | Mario |
| 1 | Luigi |
| 2 | Yellow Toad |
| 3 | Blue Toad |
| 4 | Mii |

## Powerup
| ID | Powerup |
| --- | --- |
| 0 | Small |
| 1 | Big |
| 2 | Fire |
| 3 | Mini |
| 4 | Propeller |
| 5 | Penguin |
| 6 | Ice |
| 7 | Acorn |
| 8 | P-Acorn |
