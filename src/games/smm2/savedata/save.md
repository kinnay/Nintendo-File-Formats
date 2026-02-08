## [SMM 2](../../formats.md#smm2) > [Save Data](../savedata.md) > Main

The page describes the content of the `save.dat` save data file in Super Mario Maker 2. The filesize is always `0xC000` bytes.

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
    0x5C736064, 0x3F9178C3, 0x9D11DBD3, 0xD8B11DE9,
    0xBCAFD10B, 0x85E013EB, 0xAB4CB7A5, 0x12DF234A,
    0x69BD8F28, 0x9718796A, 0x467E510E, 0xC9002264,
    0xF5EF9EF5, 0xFE19683B, 0x9E739A59, 0x8330F69F,
    0x158E467C, 0xDCC25B0B, 0xCC96E901, 0x5AFF8BE1,
    0xBB08745E, 0xF9C232E5, 0xDB7E0641, 0x9B5E1AD7,
    0x25B8D979, 0xE35251D3, 0x9C1E9ADB, 0x256902E2,
    0xCA67B195, 0x16CDB407, 0xFD95C734, 0xD019C133,
    0x5F39E755, 0x118168FC, 0xAA796804, 0xC9AC1148,
    0x2EC0C6B4, 0xDE6E18F6, 0x5F7FAA46, 0x09FAE6A3,
    0x6BF9D926, 0xD41D2628, 0xC91BD99B, 0xB4F43F73,
    0x37B8C265, 0xA8AD2CDB, 0xF2F7A186, 0x4842B092,
    0xC6C69499, 0x5171F6D5, 0xB21A4FA7, 0x7E97D996,
    0x6FD8C33C, 0x5C9A8698, 0x7BB249D5, 0x0D43D9B4,
    0xAAAC5F3D, 0x264A8038, 0x8DF13471, 0x1C912EC2,
    0xB5D226E7, 0x807803C2, 0xD07EC9D7, 0x8ED952BB
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 4 | Always 11 |
| 0x8 | 4 | CRC32 of decrypted [file body](#file-body) |
| 0xC | 4 | Always 0 |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 20 | Nickname (UTF-16) |
| 0x14 | 2 | Maker outfit (top) |
| 0x16 | 2 | Maker outfit (bottom) |
| 0x18 | 2 | Maker outfit (headwear) |
| 0x1A | 2 | Maker emotion |
| 0x1C | 52 | Unknown |
| 0x50 | 88 | Mii data |
| 0xA8 | 16 | UUIDv4, generated once during save data creation |
| 0xB8 | 360 | Unknown |
| 0x220 | 8 | Save data creation timestamp |
| 0x228 | 0xBD98 | Unknown |
| 0xBFC0 | --- | End |