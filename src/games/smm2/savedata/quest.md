## [SMM 2](../../formats.md#smm2) > [Save Data](../savedata.md) > Quest

The page describes the content of the `quest.dat` save data file in Super Mario Maker 2. The filesize is always `0xC000` bytes.

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
    0x45161724, 0x1D628088, 0xEF1E1690, 0xD706180D,
    0x002CD75E, 0xE8C54C2B, 0xE37E094F, 0xFBE29E78,
    0xA55D19AA, 0xF3E9EE1F, 0x99336DD8, 0xC633334A,
    0xCB0FB5AB, 0x79527874, 0x583E363A, 0xA67FA640,
    0xAEDD8316, 0xBAFFF13E, 0x043BC03B, 0xF6C744CE,
    0x7E3D100A, 0x65E5199C, 0x760F0BE7, 0x33CA6B78,
    0x281F702E, 0xF131398F, 0xC0737FF2, 0x3A608374,
    0xBC5865F1, 0xCA43A35B, 0x6D766010, 0x770BE2C2,
    0xA77D3D9E, 0xE93F1DB3, 0xCE5E26EC, 0xAA9DC229,
    0xDD79665E, 0x5A412697, 0x45870A1C, 0x3ADF5F4C,
    0x8830A112, 0x8E27D707, 0x1B1CEFC2, 0x3B6FA2A5,
    0xB852CFAE, 0x242ADD3F, 0x4C7DFEC6, 0x57D72147,
    0x5B5612DD, 0x603951BF, 0x600A4D77, 0x08404482,
    0xD3617496, 0xF4401AC6, 0x82C7DCD6, 0xD4916D8A,
    0x60028D8F, 0xC54C79F0, 0x599C898F, 0xB6387382,
    0x6A7ED543, 0x8D0A0C82, 0x83C0C4B5, 0x04B17698
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 4 | Always 1 |
| 0x8 | 4 | CRC32 of decrypted [file body](#file-body) |
| 0xC | 4 | Always 0 |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0xBFC0 | Unknown |
