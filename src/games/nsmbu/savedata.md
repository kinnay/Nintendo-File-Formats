## [NSMBU](/formats.md#nsmbu) > Save Data (rp_savedata.dat)

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [Header](#header) |
| 0x10 | 0x204 * 6 | [Main slots](#save-slot) (3 for NSMBU, 3 for NSLU) |
| 0xC28 | 0x204 * 6 | [Quick save slots](#save-slot) (3 for NSMBU, 3 for NSLU) |
| 0x1840 | 0x360C | [Challenge data](#challenge-data) |
| 0x4E4C | 0xA8 | [Boost rush data](#boost-rush-data) |
| 0x4EF4 | 0x5F38 | [Coin edit data](#coin-edit-data) |
| 0xAE2C | 0x94 | [Telemetry stats](#telemetry-stats) |
| 0xAEC0 | 0x274 | [Mii data](#mii-data) |

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("RPSD") |
| 0x4 | 1 | Version (always 1) |
| 0x5 | 1 | Version (always 0) |
| 0x6 | 1 | Version (always 2) |
| 0x7 | 1 | Last used slot index |
| 0x8 | 1 | Bool indicating if the game has notified you about NSLU |
| 0x9 | 1 | Button layout |
| 0xA | 2 | Padding |
| 0xC | 4 | CRC32 |

## Save Slot
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Bool indicating if this is a valid (used) save slot |
| 0x1 | 1 | Last number of players |
| 0x2 | 1 | Number of coins |
| 0x3 | 1 | Rock-candy mine switch state |
| 0x4 | 3 | [World map location](#world-map-location) |
| 0x7 | 3 | [World map location](#world-map-location) |
| 0xA | 1 | Unknown |
| 0xB | 1 | Unknown |
| 0xC | 1 * 4 | Lives of each player |
| 0x10 | 1 * 4 | Character of each player |
| 0x14 | 1 * 4 | Powerup of each player |
| 0x18 | 1 * 4 | Game overs of each player |
| 0x1C | 2 | Finished worlds flags |
| 0x1E | 1 | Game completion flags:<br>0x02: All levels beaten<br>0x08: All star coins collected<br>0x10: All exits reached |
| 0x1F | 1 | Unknown |
| 0x20 | 12 | Unknown (Vector3f) |
| 0x2C | 1 | Unknown |
| 0x2D | 1 | Unknown |
| 0x2E | 1 | Unknown |
| 0x2F | 1 | Unknown |
| 0x30 | 4 | Score |
| 0x34 | 16 | Unknown |
| 0x44 | 2 | Credits highscore (coins) |
| 0x46 | 3 | Airship location ([world map location](#world-map-location))
| 0x49 | 1 | Nabbit world number |
| 0x4A | 1 | Nabbit world number |
| 0x4B | 1 | Unknown |
| 0x4C | 1 | Unknown |
| 0x4D | 1 | Unknown |
| 0x4E | 1 | Unknown |
| 0x4F | 1 | Unknown |
| 0x50 | 1 | Unknown |
| 0x51 | 1 | Unknown |
| 0x52 | 1 | Unknown |
| 0x53 | 1 | Unknown |
| 0x54 | 1 | Unknown |
| 0x55 | 1 | Available baby yoshi flags |
| 0x56 | 1 | Active baby yoshi |
| 0x57 | 1 | Unknown |
| 0x58 | 1 | Unknown |
| 0x59 | 1 | Unknown |
| 0x5A | 1 | Reappear counter for balloon yoshi |
| 0x5B | 1 | Reappear counter for bubble yoshi |
| 0x5C | 1 * 4 | Unknown |
| 0x60 | 1 * 4 | Ambush items |
| 0x64 | 1 * 7 | Nabbit related |
| 0x6B | 1 * 123 | Level completion flags:<br>0x1: Unlocked<br>0x2: Played
| 0xE6 | 1 * 62 | Death counter for each level |
| 0x124 | 1 * 41 | Star coins for each level |
| 0x14D | 1 * 10 | Inventory items |
| 0x157 | 0x6D | [Ambush data](#ambush-data) |
| 0x1C4 | 0x38 | [Secret island statistics](#secret-island-statistics) |
| 0x1FC | 1 | Caught nabbit flags |
| 0x1FD | 3 | Padding |
| 0x200 | 4 | CRC32 |

### World map location
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | World number |
| 0x1 | 1 | Section id |
| 0x2 | 1 | Node id |

### Ambush Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 5 * 2 | [World 1 enemies](#ambush-enemy) |
| 0xA | 5 * 3 | [World 2 enemies](#ambush-enemy) |
| 0x19 | 5 * 2 | [World 3 enemies](#ambush-enemy) |
| 0x23 | 5 * 5 | [World 4 enemies](#ambush-enemy) |
| 0x3C | 5 * 3 | [World 5 enemies](#ambush-enemy) |
| 0x4B | 5 * 3 | [World 7 enemies](#ambush-enemy) |
| 0x5A | 18 | Unknown |
| 0x6C | 1 | Unknown |

### Ambush Enemy
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 3 | [World map location](#world-map-location) |
| 0x3 | 1 | Unknown |
| 0x4 | 1 | Unknown |

### Secret Island Statistics
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Coins collected |
| 0x4 | 4 | Star coins collected |
| 0x8 | 4 | Goals reached |
| 0xC | 4 | Times applauded |
| 0x10 | 4 | Boost block distance |
| 0x14 | 4 | Mini boost block distance |
| 0x18 | 4 | Nabbits caught |
| 0x1C | 4 | Goombas stomped |
| 0x20 | 4 | Items collected |
| 0x24 | 4 | Goals reached with yoshi |
| 0x28 | 4 | Goals reached with baby yoshi |
| 0x2C | 4 | 1-Ups earned at goal |
| 0x30 | 4 | Fireworks at goal |
| 0x34 | 4 | 3-Up moons collected |

## Challenge Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Bool indicating if this struct contains valid values |
| 0x1 | 1 * 5 | Medal for each category |
| 0x6 | 1 | Unknown |
| 0x7 | 1 | Unknown |
| 0x8 | 0x6C * 80 | [Challenges](#challenge-info) |
| 0x21C8 | 0x1440 | Unknown |
| 0x3608 | 4 | CRC32 |

### Challenge Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Completion state |
| 0x1 | 1 | Player this challenge was completed with |
| 0x2 | 2 | Unknown |
| 0x4 | 0x60 | [FFLStoreData](https://github.com/Kinnay/NintendoClients/blob/master/nintendo/miis.py) if this challenge was completed with a mii |
| 0x64 | 4 | Highscore |
| 0x68 | 4 | CRC32 of replay file |

## Boost Rush Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Unknown |
| 0x1 | 1 | Unknown |
| 0x2 | 1 | Unknown |
| 0x3 | 1 | Unknown |
| 0x4 | 4 * 32 | Highscore in 1/100 seconds |
| 0x84 | 1 * 32 | Unknown |
| 0xA4 | 4 | CRC32 |

## Coin Edit Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x984 * 10 | [Coin edit levels](#coin-edit-stage) |
| 0x5F28 | 12 | Unlocked levels |
| 0x5F34 | 4 | CRC32 |

### Coin Edit Stage
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 * 300 | [Coins](#coin-edit-coin) |
| 0x960 | 12 * 3 | [Star coins](#coin-edit-star-coin) |

### Coin Edit Coin
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Area number |
| 0x1 | 1 | Zone number |
| 0x2 | 1 | Bool indicating if this entry is valid |
| 0x3 | 1 | Unknown |
| 0x4 | 2 | X position |
| 0x6 | 2 | Y position |

### Coin Edit Star Coin
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Area number |
| 0x1 | 1 | Zone number |
| 0x2 | 1 | Unknown |
| 0x3 | 1 | Unknown |
| 0x4 | 4 | X position (float) |
| 0x8 | 4 | Y position (float) |

## Telemetry Stats
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Seconds played |
| 0x4 | 4 | Seconds spent in story mode |
| 0x8 | 4 | Levels played |
| 0xC | 4 | Levels played alone |
| 0x10 | 4 | Levels played with two players |
| 0x14 | 4 | Levels played with three players |
| 0x18 | 4 | Levels played with four players |
| 0x1C | 4 | Unknown |
| 0x20 | 4 | Nabbits chased |
| 0x24 | 4 | Super guides seen |
| 0x28 | 4 | Boost rush games played |
| 0x2C | 4 | Boost rush games played alone |
| 0x30 | 4 | Boost rush games played with two players |
| 0x34 | 4 | Boost rush games played with three players |
| 0x38 | 4 | Boost rush games played with four players |
| 0x3C | 4 | Unknown |
| 0x40 | 4 | Unknown |
| 0x44 | 4 | Coin battles played |
| 0x48 | 4 | Coin battles played alone |
| 0x4C | 4 | Coin battles played with two players |
| 0x50 | 4 | Coin battles played with three players |
| 0x54 | 4 | Coin battles played with four players |
| 0x58 | 4 | Unknown |
| 0x5C | 4 | Unknown |
| 0x60 | 4 | Edited coin battle levels played |
| 0x64 | 4 | Challenges played |
| 0x68 | 4 | Unknown |
| 0x6C | 4 | Challenge replays watched |
| 0x70 | 4 | Boost mode challenges played |
| 0x74 | 4 | NSLU levels played |
| 0x78 | 4 | Unknown |
| 0x7C | 4 | Unknown |
| 0x80 | 4 | Powerups used |
| 0x84 | 1 | Unknown |
| 0x85 | 1 | Unknown |
| 0x86 | 1 | Unknown |
| 0x87 | 1 | Unknown |
| 0x88 | 1 | Unknown |
| 0x89 | 1 | Unknown |
| 0x8A | 1 | Gold medals earned |
| 0x8B | 1 | Silver medals earned |
| 0x8C | 1 | Bronze medals earned |
| 0x8D | 1 | Boost mode challenges completed |
| 0x8E | 1 | Unknown |
| 0x8F | 1 | Unknown |
| 0x90 | 4 | CRC32 |

## Mii Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Number of entries |
| 0x1 | 10 * 62 | Up to 62 FFLCreateID entries |
| 0x26D | 3 | Padding |
| 0x270 | 4 | CRC32 |