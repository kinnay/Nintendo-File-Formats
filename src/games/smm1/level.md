## [SMM 1](../../formats.md#smm1) > Level Files

Every single SMM1 level contains the next following files:
* `course_data.cdt` (Main area)
* `course_data_sub.cdt` (Sub area)
* `sound.bwv` (Unknown)
* `thumbnail0.tnl` (Long thumbnail)
* `thumbnail1.tnl` (Thumbnail)

Both of `course_data.cdt` and `course_data_sub.cdt` are files with a size of exactly 86,016 bytes, in which you can write data from offset `0x0` to offset `0x14FFF` and both uses the same format

## `course_data.cdt` & `course_data_sub.cdt`
| Offset | Description |
| --- | --- |
| 0x0 to 0x7 | Unknown |
| 0x8 to 0xB | CRC32 applied starting from offset 0x10 to the end of the file |
| 0x10 to 0x11 | Last modification Year |
| 0x12 | Last modification Month |
| 0x13 | Last modification Day |
| 0x14 | Last modification Hour |
| 0x15 | Last modification Minute |
| 0x16 to 0x19 | Unknown |
| 0x1A to 0x1F | Last 12 ID characters (NOTE: Only applies for downloaded levels) |
| 0x20 | Downloaded level (VALUES: `00` False `01` True) |
| 0x21 | Previously removed level from servers (VALUES: `00` False `01` True) |
| 0x22 to 0x26 | Unknown |
| 0x27 | Physics version, allows you to downgrade a level and do partially patched techs (VALUES: `00` Version 1.00, `01` Version 1.20, `02` Version 1.30, `03` Version 1.43, `04` Version 1.44, `05` Version 1.45, `06` Version 1.46, `07` Version 1.47) |
| 0x28 to 0x67 | Level name (utf16) |
| 0x68 to 0x69 | Unknown |
| 0x6A to 0x6B | Level style (VALUES: [`4D` `31` = `M1`] [`4D` `33` = `M3`] [`4D` `57` = `MW`] [`57` `55` = `WU`]) |
| 0x6C | Unknown |
| 0x6D | Level theme (VALUES: `00` Ground, `01` Underground, `02` Castle, `03` Airship, `04` Underwater, `05` Ghost house) |
| 0x6E | Uploaded level to servers (VALUES: `00` False `01` True) |
| 0x6F | Clear check level status (VALUES: `00` False `01` True) |
| 0x70 to 0x71 | Level timer |
| 0x72 | Level scroll (VALUES: `00` None, `01` Slow, `02` Normal, `03` Fast, `Out of range` Scroll lock) |
| 0x73 to 0x77 | Unknown |
| 0x78 to 0xDA | Mii data (NOTE: Only applies for downloaded levels and right now is unknown how it works) |
| 0xDB | Mii country flag (NOTE: Only applies for downloaded levels. SMM1 country values table [here](https://github.com/NobleD4/MARIO-MAKER-D4TA-EDITOR/blob/master/README.md)) |
| 0xDC to 0x107 | Unknown |
| 0x108 to 0x145EF | Space reserved for object/items/enemies |
| 0x145F0 to 0x14F4F | Space reserved for sound effects |
| 0x14F50 to 0x14FFF | Unknown |

I would like to add something more about IDs format inside `.cdt` files:
* Level ID only displays in coursebot if "Downloaded level" value is True
* First 4 characters (ID prefix) are calculated from next 12 characters (ID subfix) using an MD5 hash algorithm and a key access string
* If every character in subfix is `00` the level won't display an ID in coursebot, even if "Downloaded level" is True
* Everything about SMM1 IDs format [here](https://github.com/kinnay/NintendoClients/wiki/Data-Store-Codes#super-mario-maker)

If you want to know more about placing objects you should check this repos:
* [MarioUnmaker](https://github.com/Treeki/MarioUnmaker/blob/master/FormatNotes.md)
* [PointlessMaker](https://github.com/aboood40091/PointlessMaker)

## `thumbnail0.tnl` & `thumbnail1.tnl`
In SMM1, level thumbnails are saved as `.tnl` file which is just a JPEG wrapper format. A `.tnl` file always has a size of 51,200 bytes, so you can write data from offset 0x0 to offset 0xC7FF.

* `thumbnail0.tnl` resolution: 720px width & 80px height (width could be any number but 720px is the maximum)
* `thumbnail1.tnl` resolution: 320px width & 240px height
* Reference for this format [here](https://gist.github.com/RoadrunnerWMC/33c28d6d13b411f1e55471936d36c990)
