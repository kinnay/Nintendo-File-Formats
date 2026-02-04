## [AC:NH](../../formats.md#acnh) > Save Data

This page is based on Animal Crossing: New Horizons version 3.0.0.

AC:NH uses a system wide save data archive, instead of one save data archive per user. The following files can be found in the save data archive:

* [`landname.dat`](#landnamedat)
* [`main.dat`](#maindat)
* [`mainHeader.dat`](#header-files)

In addition, up to 8 folders named `Villager0` up to `Villager7` may be present. These contain the following files:

* `personal.dat`
* [`personalHeader.dat`](#header-files)
* `photo_studio_island.dat`
* [`photo_studio_islandHeader.dat`](#header-files)
* `postbox.dat`
* [`postboxHeader.dat`](#header-files)
* `profile.dat`
* [`profileHeader.dat`](#header-files)

Everything is stored in little-endian byte order.

## Header Files
All files, except for `landname.dat`, are encrypted with AES-CTR. The header file, that is stored along with each file, contains information that is used to generate the key and IV:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 256 | Unknown |
| 0x100 | 4 * 128 | Encryption key table (128 random integers) |

The key and IV are generated using the [SEAD RNG](https://github.com/kinnay/NintendoClients/wiki/SEAD-RNG), as follows:

```python
def generate_data(seed: int, skips: int) -> bytes:
    rng = Random(seed)
    for i in range(skips):
        rng.u64()
    
    data = []
    for i in range(16):
        data.append(rng.u32() >> 24)
    return bytes(data)

def generate_key(table: list[int]) -> bytes:
    seed = table[table[0] & 0x7F]
    skips = (table[table[1] & 0x7F] & 0xF) + 1
    return generate_data(seed, skips)

def generate_iv(table: list[int]) -> bytes:
    seed = table[table[2] & 0x7F]
    skips = (table[table[3] & 0x7F] & 0xF) + 1
    return generate_data(seed, skips)
```

The rest of this page describes the format of decrypted save data files.

## landname.dat
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 20 | Island name (UTF-16) |
| 0x14 | 2 | Unknown |

## main.dat
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 10161808 | Unknown |
| 0x9B0E90 | --- | --- |

## Sources
Besides reverse engineering, the following sources were used for this page:
* [https://gist.github.com/Treeki/d46ac2f8cd9111f60f48b6707207fa4a](https://gist.github.com/Treeki/d46ac2f8cd9111f60f48b6707207fa4a)
