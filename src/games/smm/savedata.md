## [SMM](../../formats.md#smm) > Save Data (save.dat)

Every user in Super Mario Maker has their progress stored in one file, which is `save.dat`. This file has a size of `0xA000` bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16944 | Unknown |
| 0x4230 | ? | Represents all your unlocked items in your editor mode |
| | ? | Unknown |
| 0x4332 | 1 | Control settings (0 = Dash/Jump, 1 = Jump/Dash) |
| 0x4333 | 4 | Unknown |
| 0x4337 | 1 | GamePad 3D Audio (0 or 1) |
| 0x4338 | 1 | Notify to other creators (0 or 1) |
| 0x4339 | 1 | Notify about my courses (0 or 1) |
| 0x433A | 6 | Unknown |
| 0x4340 | 120 | Represents all 120 levels inside your coursebot |
| 0x43B8 | 23624 | Unknown |

[This page](https://pastebin.com/y3Xnsm6S) contains more information about how the game processes your coursebot data.
