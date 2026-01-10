## [SMM 1](../../formats.md#smm1) > Save Data (save.dat)

Every user in SMM1 has their progress stored in only one file which is `save.dat`. This file has a size of 40,960 bytes and you can write data from offset `0x0` to offset `0x9FFF`

## `save.dat`
| Offset | Description |
| --- | --- |
| 0x4230 to ? | Represents all your unlocked items in your editor mode |
| 0x4332 | Control settings (VALUES: `00` Dash/Jump `01` Jump/Dash) |
| 0x4337 | GamePad 3D Audio (VALUES: `00` False `01` True) |
| 0x4338 | Notify to other creators (VALUES: `00` False `01` True) |
| 0x4339 | Notify about my courses (VALUES: `00` False `01` True) |
| 0x4340 to 0x43B7 | Represents all 120 levels inside your coursebot |

If you want to know more about how the game process your coursebot data you should read [this](https://pastebin.com/y3Xnsm6S)
