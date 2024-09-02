## [AAL](/formats.md#aal) > Audio Resource (BARS)

A BARS file is an audio resource. BARS files are referenced by [BARSLIST files](./barslist.md).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("BARS") |
| 0x4 | 4 | Filesize |
| 0x8 | 2 | BOM (always 0xFEFF) |
| 0xA | 2 | Version number (0x0101) |
| 0xC | 4 | Number of assets |
| 0x10 | | For each asset the CRC32 hash of its name. This table is used to look up the index of an asset. This table must be sorted, because a binary search is used. |
| | | For each asset a [file offset set](#file-offset-set). These entries must be ordered the same way as their hashes, because they are looked up by index, which is obtained by searching the hash table. |
| | | Audio meta files |
| | | Asset files |

AAL assumes that there are no hash collisions.

Asset files are aligned to a mulitple of 64 bytes.

## File Offset Set
These are absolute offsets.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to [audio meta file](./bamta.md) |
| 0x4 | 4 | Offset to asset file ([bfwav](../nw/bfwav.md) or [bfstp](../nw/bfstp.md)) |

If a resource does not have an asset file, the offset to the asset file is -1.