## [SMM 2](../../formats.md#smm2) > [Save Data](../savedata.md) > Network

The page describes the content of the `network.dat` save data file in Super Mario Maker 2. The filesize is always `0x48000` bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0x47FC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0x47FD0 | 0x30 | [Crypto footer](#encryption) |

## Encryption
Details about the encryption algorithm are [described here](../encryption.md).

The following integer table is passed to the key generation algorithm:

```python
table = [
    0x0EE7AC92, 0xF29F5875, 0xCBB2572B, 0x06DC86B3,
    0x553B9F0B, 0x5DFD99C5, 0x0ED6FFBB, 0x37D69AC2,
    0x30A16D25, 0xA22D3C0D, 0xA6D5C8C1, 0xB18F8E99,
    0x02865CF2, 0xE4A7A62E, 0x37DD1F79, 0xD2A6A211,
    0x85A60435, 0x01628233, 0x2CFD6417, 0xFFC307E9,
    0x4442D40B, 0x8A11105A, 0x108FB62C, 0xC1B9F529,
    0x60468D41, 0x6F7DB950, 0x51A8DB7C, 0xDF1FA64C,
    0xEA508456, 0x6EFA4C34, 0x90AF1DFD, 0x42276A9E,
    0xB7C94364, 0x6BA070D0, 0xD4C21979, 0x8511B7A3,
    0x47D42CC0, 0x5DC58EAE, 0xFBFB56F0, 0xAEC981EA,
    0x45355D36, 0xA862859F, 0x272AD5ED, 0x696CCA17,
    0x24483704, 0x1E7C03F2, 0xAACB9CEE, 0xB0C75827,
    0x28D0FDE2, 0x1B382F8E, 0x8E738624, 0x2E6A356D,
    0xF00D88EF, 0xD22A903E, 0x34339DBC, 0xCB1116F1,
    0xE9AD1838, 0xA37E340C, 0xE1D64C9E, 0xB8EAAF32,
    0x9D81506D, 0xB79AA1B3, 0x39BD904E, 0x65CEA34D
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 4 | Always 8 |
| 0x8 | 4 | CRC-32 of decrypted [file body](#file-body) |
| 0xC | 4 | Always 0 |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x47FC0 | Unknown |
