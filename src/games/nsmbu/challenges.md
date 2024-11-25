## [NSMBU](../../formats.md#nsmbu) > Challenge Info

This page describes the `HIOSubjectData_CAFE.exbin` file found in NSMBU. It defines the 80 challenges that can be played in the game.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 3000 |
| 0x4 | 4 | Always 1000 |
| 0x8 | 4 | Always 0 |
| 0xC | 4 | Always 0 |
| 0x10 | 96 * 80 | [Challenges](#challenge) |

## Challenge
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Baby yoshi (0=none, 1=bubble, 2=balloon) |
| 0x4 | 4 | Level number minus 1 |
| 0x8 | 4 | [Initial powerup](#powerup) |
| 0xC | 4 | Unknown |
| 0x10 | 4 | [Challenge end](#challenge-end) |
| 0x14 | 4 | [Challenge type](#challenge-type) |
| 0x18 | 4 | [Challenge category](#challenge-category) |
| 0x1C | 4 | Unknown |
| 0x20 | 4 | World number minus 1 |
| 0x24 | 4 | Unknown |
| 0x28 | 4 | Unknown |
| 0x2C | 4 | Challenge id that must be completed before this challenge is unlocked |
| 0x30 | 4 | Number of challenges that must be completed in this category before this challenge is unlocked |
| 0x34 | 4 | Unknown |
| 0x38 | 4 | Time limit |
| 0x3C | 4 | Difficulty rating (stars) |
| 0x40 | 4 | Area number minus 1 |
| 0x44 | 4 | Entrance id |
| 0x48 | 4 | Challenge id |
| 0x4C | 4 | Unknown |
| 0x50 | 4 | Unknown |
| 0x54 | 4 | Bronze medal cut-off |
| 0x58 | 4 | Silver medal cut-off |
| 0x5C | 4 | Gold medal cut-off |

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

## Challenge End
| ID | Condition |
| --- | --- |
| 0 | None |
| 1 | A crab leaves the screen alive |
| 2 | All coins are collected |
| 3 | A coin is collected |
| 4 | The player walks after gliding |
| 5 | The ground is touched after an enemy has been killed |
| 6 | The ground is touched |
| 7 | A snake block is touched |
| 8 | A rising tilt-controlled girder is touched |
| 9 | A powerup is collected or damage is taken |
| 10 | Your powerup is lost |
| 11 | Monty mole is killed |
| 12 | Unknown |
| 13 | The ground is touched |
| 14 | Unknown |
| 15 | Baby yoshi dies |
| 16 | An enemy is touched or a coin is collected |
| 17 | The player runs |
| 18 | A star coin is collected |

## Challenge Type
| ID | Type |
| --- | --- |
| 0 | Time trial |
| 1 | Gather as many coins as possible |
| 2 | Gather as few coins as possible |
| 3 | Get as many lives as possible |
| 4 | Hit as few enemies as possible |
| 5 | Reach the goal |
| 6 | Unknown |
| 7 | Unknown |
| 8 | Unknown |
| 9 | Unknown |
| 10 | Survive for a certain amount of time |

## Challenge Category
| ID | Category |
| --- | --- |
| 0 | Time attack |
| 1 | Coin collection |
| 2 | 1-up rally |
| 3 | Special |
| 4 | Boost mode |
