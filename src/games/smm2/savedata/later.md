
## [SMM 2](../../formats.md#smm2) > [Save Data](../savedata.md) > Later

The page describes the content of the `later.dat` save data file in Super Mario Maker 2. The filesize is always `0xC000` bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0xBFC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0xBFD0 | 0x30 | [Crypto footer](#encryption) |

## Encryption
Details about the encryption algorithm are [described here](../encryption.md).

The following integer table is passed to the key generation algorithm:

```python
table = [
    0x1CBC16C1, 0xF468AFCF, 0x6F56A9CD, 0xFF234473,
    0x79D75E19, 0xCE13762E, 0xA7C3B9EC, 0x2DBD57D2,
    0x52B04A8B, 0x91BA89AB, 0x02AA963A, 0x372F4D1C,
    0x0B0DFE6F, 0x10791D7B, 0x48E6ADB2, 0x446B8979,
    0xF6C22D64, 0xA1A850C9, 0x1E0873A7, 0xDF669A3A,
    0xF2444EE4, 0x26B7F6FF, 0x23085C49, 0x724379C3,
    0xB869BE34, 0x235E09DB, 0xAA73EE66, 0x2CC099EE,
    0x5119DD31, 0x2CD16119, 0x3601C35D, 0x48A9B1F9,
    0xFA096C03, 0xD0F8B7F1, 0x8B3DFFEB, 0xBF91B778,
    0x6B6F8E77, 0x51F6D398, 0x2D3FD2EA, 0x553D9AF7,
    0x0C716204, 0x3B2FFD8E, 0x7B185872, 0xBDDA19A5,
    0xC9CED66B, 0xA935CEB5, 0xCA3EBC89, 0xC0EE4C4D,
    0xFFDDA782, 0xCC0C1069, 0x91F3FAC0, 0x5FAFBDF4,
    0xA42FBF7D, 0xAA88D236, 0xE7606B88, 0x71D7FF31,
    0x1022D446, 0xDA78A3DF, 0x596E8949, 0xA1FC82EB,
    0x665D7428, 0x5E9161D3, 0x1C1BDCC7, 0xEEE25BD0
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 4 | Always 10 |
| 0x8 | 4 | CRC-32 of decrypted [file body](#file-body) |
| 0xC | 4 | Always 0 |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0xBFC0 | Unknown |
