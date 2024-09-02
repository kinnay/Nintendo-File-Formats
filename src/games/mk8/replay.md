[MK8](/formats.md#mk8) > Replay Files
---

Everything is encoded with big-endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | File header size (0x400) |
| 0x4 | 4 | Version number: `(major << 21) \| (minor << 11) \| patch` |
| 0x8 | 4 | Total file size |
| 0xC | 28 | [Creation date](#creation-date) |
| 0x28 | 4 | CRC32 hash of whole file |
| 0x2C | 488 | [Race info](#race-info)
| 0x214 | 28 | [Race kart info](#race-kart-info) |
| 0x230 | 256 | Unknown |
| 0x330 | 5 * 12 | Unknown |
| 0x36C | 2 | Unknown |
| 0x36E | 1 | Unknown |
| 0x36F | 1 | Padding |
| 0x370 | 2 | Unknown |
| 0x372 | 6 | Padding |
| 0x378 | 8 | [Race kart result](#race-kart-result) |
| 0x380 | 1 | Unknown |
| 0x381 | 127 | Unknown |
| 0x400 | | [Replay data](#replay-data) |

## Creation Date
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Year |
| 0x4 | 4 | Month |
| 0x8 | 4 | Day |
| 0xC | 4 | Weekday |
| 0x10 | 4 | Hour |
| 0x14 | 4 | Minute |
| 0x18 | 4 | Second |

## Race Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 12 * 28 | [Race kart info](#race-kart-info) (x12) |
| 0x150 | 4 | [Track id](#track-ids) |
| 0x154 | 148 | Unknown |

## Race Kart Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 1 | Unknown |
| 0x11 | 1 | Unknown |
| 0x12 | 2 | Padding |
| 0x14 | 4 | Unknown |
| 0x18 | 4 | Unknown |

## Race Kart Result
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |

## Replay Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | CRC32 hash of replay header |
| 0x4 | 4 | Replay header size |
| 0x54 | 4 | Replay data size |
| | | Yaz0 compressed replay frames |

## Track IDs
| Cup | Track | ID |
| --- | --- | --- |
| Mushroom | Mario Kart Stadium | 27 |
| Mushroom | Water Park | 28 |
| Mushroom | Sweet Sweet Canyon | 19 |
| Mushroom | Thwomp Ruins | 17 |
||
| Flower | Mario Circuit | 16 |
| Flower | Toad Harbor | 18 |
| Flower | Twisted Mansion | 20 |
| Flower | Shy Guy Falls | 21 |
||
| Star | Sunshine Airport | 26 |
| Star | Dolphin Shoals | 29 |
| Star | Electrodrome | 25 |
| Star | Mount Wario | 24 |
||
| Special | Cloudtop Cruise | 23 |
| Special | Bone-Dry Dunes | 22 |
| Special | Bowser's Castle | 30 |
| Special | Rainbow Road | 31 |
||
| Shell | Wii Moo Moo Meadows | 33 |
| Shell | GBA Mario Circuit | 38 |
| Shell | DS Cheep Cheep Beach | 36 |
| Shell | N64 Toad's Turnpike | 35 |
||
| Banana | GCN Dry Dry Desert | 42 |
| Banana | SNES Donut Plains 3 | 41 |
| Banana | N64 Royal Raceway | 34 |
| Banana | 3DS DK Jungle | 32 |
||
| Leaf | DS Wario Stadium | 46 |
| Leaf | GCN Sherbet Land | 37 |
| Leaf | 3DS Music Park | 39 |
| Leaf | N64 Yoshi Valley | 45 |
||
| Lightning | DS Tick-Tock Clock | 44 |
| Lightning | 3DS Piranha Plant Slide | 43 |
| Lightning | Wii Grumble Volcano | 40 |
| Lightning | N64 Rainbow Road | 47 |
||
| Egg | GCN Yoshi Circuit | 56 |
| Egg | Excitebike Arena | 53 |
| Egg | Dragon Driftway | 50 |
| Egg | Mute City | 49 |
||
| Triforce | Wii Wario's Gold Mine | 57 |
| Triforce | SNES Rainbow Road | 58 |
| Triforce | Ice Ice Outpost | 55 |
| Triforce | Hyrule Circuit | 51 |
||
| Crossing | GCN Baby Park | 61 |
| Crossing | GBA Cheese Land | 62 |
| Crossing | Wild Woods | 54 |
| Crossing | Animal Crossing (Summer) | 52 |
| Crossing | Animal Crossing (Spring) | 64 |
| Crossing | Animal Crossing (Autumn) | 65 |
| Crossing | Animal Crossing (Winter) | 66 |
||
| Bell | 3DS Neo Bowser City | 60 |
| Bell | GBA Ribbon Road | 59 |
| Bell | Super Bell Subway | 48 |
| Bell | Big Blue | 63 |