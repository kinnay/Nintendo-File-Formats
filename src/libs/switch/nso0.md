## [Switch](../../formats.md#nintendo-switch) > NSO0 Files

An `NSO0` file contains an executable.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`NSO0`) |
| 0x4 | 4 | Version (always 0) |
| 0x8 | 4 | Padding (always 0) |
| 0xC | 4 | [Flags](#flags) |
| 0x10 | 4 | Offset to `.text` segment in file (absolute) |
| 0x14 | 4 | Address of `.text` segment in memory |
| 0x18 | 4 | Size of `.text` segment in memory |
| 0x1C | 4 | Offset to null-terminated module name in file (absolute) |
| 0x20 | 4 | Offset to `.rodata` segment in file (absolute) |
| 0x24 | 4 | Address of `.rodata` segment in memory |
| 0x28 | 4 | Size of `.rodata` segment in memory |
| 0x2C | 4 | Size of module name, including null terminator |
| 0x30 | 4 | Offset to `.data` segment in file (absolute) |
| 0x34 | 4 | Address of `.data` segment in memory |
| 0x38 | 4 | Size of `.data` segment in memory |
| 0x3C | 4 | Size of `.bss` segment in memory |
| 0x40 | 32 | Module id (random bytes / hash) |
| 0x60 | 4 | Size of `.text` segment in file |
| 0x64 | 4 | Size of `.rodata` segment in file |
| 0x68 | 4 | Size of `.data` segment in file |
| 0x6C | 28 | Padding (always 0) |
| 0x88 | 4 | "Embedded offset" (?) |
| 0x8C | 4 | "Embedded size" (?) |
| 0x90 | 4 | Offset to `.dynstr` section, relative to `.rodata` segment |
| 0x94 | 4 | Size of `.dynstr` section |
| 0x98 | 4 | Offset to `.dynsym` section, relative to `.rodata` segment |
| 0x9C | 4 | Size of `.dynsym` section |
| 0xA0 | 32 | SHA-256 of decompressed `.text` segment |
| 0xC0 | 32 | SHA-256 of decompressed `.rodata` segment |
| 0xE0 | 32 | SHA-256 of decompressed `.data` segment |
| 0x100 | | Null-terminated module name |
| | | `.text` segment data (optionally compressed) |
| | | `.rodata` segment data (optionally compressed) |
| | | `.data` segment data (optionally compressed) |

Notes:
* The module name seems to be empty for games.
* The `.text`, `.rodata` and `.data` segments do not need to be aligned to word boundary (there is no padding between them).

## Flags
| Flag | Description |
| --- | --- |
| `0x1` | `.text` segment is compressed |
| `0x2` | `.rodata` segment is compressed |
| `0x4` | `.data` segment is compressed |
| `0x8` | `.text` hash is valid |
| `0x10` | `.rodata` hash is valid |
| `0x20` | `.data` hash is valid |
| `0x40` | Execute-only memory is enabled |
| `0x80` | ZBIC compression is used instead of LZ4 |

### References
* [https://switchbrew.org/wiki/NSO0](https://switchbrew.org/wiki/NSO0)
