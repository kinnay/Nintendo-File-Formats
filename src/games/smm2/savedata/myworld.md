## [SMM 2](../../formats.md#smm2) > [Save Data](../savedata.md) > My World

The page describes the content of the `myworld.dat` save data file in Super Mario Maker 2. The filesize is always `0x50000` bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0x4FFC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0x4FFD0 | 0x30 | [Crypto footer](#encryption) |

## Encryption
Details about the encryption algorithm are [described here](../encryption.md).

The following integer table is passed to the key generation algorithm:

```python
table = [
    0xDFF6C33E, 0xB486C7E3, 0x1646D368, 0x567B75E6,
    0xC6D84AE7, 0xCA064CA8, 0x5B254E07, 0x81B3FE37,
    0x08ACAF1B, 0x14CD60EB, 0x5DC5946F, 0xEB8FBB88,
    0xD364B538, 0xA949551D, 0xDA4D7166, 0xEA0E87A7,
    0x89D053E1, 0x009D4895, 0xF86B9856, 0x2FE0C220,
    0x3C402325, 0x8659E43D, 0x87C3ED1A, 0xCBD7030C,
    0xCF396F99, 0x0DFD94DC, 0x84DDD433, 0xCF177DBF,
    0x88F6881C, 0x88DD889F, 0xF1206287, 0xE7DC7805,
    0xF50A2BC6, 0x6236A8BB, 0xDF39F5C5, 0xB57322CB,
    0xFAFD57F6, 0x289DFACC, 0x27FB583A, 0x0B8614EF,
    0xB4F88E08, 0x142D69DC, 0x226B96CF, 0x7C8A3FB5,
    0x8C0C9454, 0x3C64DE8A, 0x0C2E6E3F, 0xB295219F,
    0xE36F5007, 0x6D7E31B7, 0xAC1C2A3A, 0x5F97BED7,
    0x4E5E3DA0, 0x708CB046, 0x81FDC22E, 0x2D2BDEE6,
    0xE7165C54, 0x0C872B94, 0x7995D31C, 0x90FC391D,
    0x8F4096FA, 0x33D111B9, 0x5723F56C, 0x46AF2E44
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 0 |
| 0x4 | 4 | Always 0 |
| 0x8 | 4 | Always 5 |
| 0xC | 4 | CRC-32 of decrypted [file body](#file-body) |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x4FFC0 | Unknown |
