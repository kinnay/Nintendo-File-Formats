## [SMM 2](../../formats.md#smm2) > Level Files

All level files have the same size in Super Mario Maker 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0x5BFC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0x5BFD0 | 0x30 | [Crypto parameters](#encryption) |

## Encryption
The [file body](#file-body) is encrypted with AES-CBC. The following structure is stored at the end of the level file:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | Initialization vector |
| 0x10 | 4 x 4 | Random number generator state |
| 0x20 | 16 | AES-CMAC of decrypted data |

The [ENL key generation algorithm](https://github.com/Kinnay/NintendoClients/wiki/ENL-Key-Generation) is used to generate the keys. However, instead of initializing the random number generator by seed, its internal state is initialized directly with the values from the structure above. Two keys are generated (with the same random number generator):
1. A 16-byte key to decrypt the [file body](#file-body)
2. A 16-byte key to calculate or verify the CMAC

The following integer table is passed to the key generation algorithm:

```python
table = [
	0x7AB1C9D2, 0xCA750936, 0x3003E59C, 0xF261014B,
	0x2E25160A, 0xED614811, 0xF1AC6240, 0xD59272CD,
	0xF38549BF, 0x6CF5B327, 0xDA4DB82A, 0x820C435A,
	0xC95609BA, 0x19BE08B0, 0x738E2B81, 0xED3C349A,
	0x045275D1, 0xE0A73635, 0x1DEBF4DA, 0x9924B0DE,
	0x6A1FC367, 0x71970467, 0xFC55ABEB, 0x368D7489,
	0x0CC97D1D, 0x17CC441E, 0x3528D152, 0xD0129B53,
	0xE12A69E9, 0x13D1BDB7, 0x32EAA9ED, 0x42F41D1B,
	0xAEA5F51F, 0x42C5D23C, 0x7CC742ED, 0x723BA5F9,
	0xDE5B99E3, 0x2C0055A4, 0xC38807B4, 0x4C099B61,
	0xC4E4568E, 0x8C29C901, 0xE13B34AC, 0xE7C3F212,
	0xB67EF941, 0x08038965, 0x8AFD1E6A, 0x8E5341A3,
	0xA4C61107, 0xFBAF1418, 0x9B05EF64, 0x3C91734E,
	0x82EC6646, 0xFB19F33E, 0x3BDE6FE2, 0x17A84CCA,
	0xCCDF0CE9, 0x50E4135C, 0xFF2658B2, 0x3780F156,
	0x7D8F5D68, 0x517CBED1, 0x1FCDDF0D, 0x77A58C94
]
```

## File Header
The header is not encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Always 1 |
| 0x4 | 2 | Always 16 |
| 0x6 | 2 | Always 1 |
| 0x8 | 4 | CRC32 of decrypted [file body](#file-body) |
| 0xC | 4 | Magic number (always `SCDL`) |

## File Body
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x200 | [Course metadata](#course-metadata) |
| 0x200 | 0x2DEE0 | Unknown |
| 0x2E0E0 | 0x2DEE0 | Unknown |

### Course Metadata
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 2 | Time limit |
| 0x6 | 2 | Unknown |
| 0x8 | 2 | Creation year |
| 0xA | 1 | Creation month |
| 0xB | 1 | Creation day |
| 0xC | 1 | Creation hour |
| 0xD | 1 | Creation minute |
| 0xE | 2 | Unknown |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | Unknown |
| 0x18 | 8 | Unknown |
| 0x20 | 4 | Unknown |
| 0x24 | 4 | Random number seed |
| 0x28 | 0xC0 | Unknown |
| 0xF0 | 1 | Unknown |
| 0xF1 | 3 | Unknown |
| 0xF4 | 0x20 | Level name (utf16) |
| 0x114 | 0xEC | Unknown |