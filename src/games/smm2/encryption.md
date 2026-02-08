## [SMM 2](../../formats.md#smm2) > Encryption

Many files, such as [level files](level.md) and [save data](savedata.md), are encrypted in Super Mario Maker 2.

These files start with an unencrypted header, followed by the ciphertext, followed by a footer. The size and format of the header and ciphertext depend on the file format.

The ciphertext is always encrypted with AES-CBC. The footer has the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | Initialization vector |
| 0x10 | 4 x 4 | Random number generator state |
| 0x20 | 16 | AES-CMAC of decrypted data |

The encryption keys are generated with the [ENL key generation algorithm](https://github.com/Kinnay/NintendoClients/wiki/ENL-Key-Generation). However, instead of initializing the random number generator with a specific seed, its internal state is initialized directly with the values from the structure above.

Two keys are generated with the RNG:
1. A 16-byte key to decrypt the [file body](#file-body)
2. A 16-byte key to calculate or verify the CMAC

The integer table that is passed to the key generation algorithm depends on the file format.
