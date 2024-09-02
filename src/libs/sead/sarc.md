## [SEAD](../../formats.md#sead) > Archives (SARC)

This page describes version 0x100 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`SARC`) |
| 0x4 | 2 | Header size (must be 0x14) |
| 0x6 | 2 | Endianness (0xFEFF=Big, 0xFFFE=Little) |
| 0x8 | 4 | Filesize |
| 0xC | 4 | Offset to data section |
| 0x10 | 2 | Version number |
| 0x12 | 2 | Padding |
| 0x14 | | [SFAT section](#sfat-section) |
| | | [SFNT section](#sfnt-section) |
| | | Data section |

Certain files, such as textures, have specific alignment requirements. For this reason, there may be padding between the SFNT and data section, and between individual files within the data section.

## SFAT Section
The hash multiplier is always 101 in official files.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`SFAT`) |
| 0x4 | 2 | Header size (must be 0xC) |
| 0x6 | 2 | Number of files (up to 0x3FFF) |
| 0x8 | 4 | Hash multiplier |
| 0xC | | [FAT entries](#fat-entry) (one per file) |

### FAT entry
These must be sorted by filename hash, because they are looked up with a binary search algorithm.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Filename hash](#filename-hash) |
| 0x4 | 4 | [Filename attributes](#filename-attributes) (see below) |
| 0x8 | 4 | Offset into data section (start of file) |
| 0xC | 4 | Offset into data section (end of file) |

### Filename Hash
The filename hash is calculated as follows, using the hash multiplier from the [SFAT header](#file-table-header):

```python
def calculate_hash(filename, multiplier):
    hash = 0
    for byte in filename:
        hash = hash * multiplier + byte
    return hash & 0xFFFFFFFF
```

In Switch games, each byte of the filename is sign extended. This is important if the filename uses non-ascii characters.

### Filename Attributes
If this field is zero, the archive contains exactly one file with the given hash and no filename is stored.

Otherwise, this field is stored as `0xAABBBBBB`. For a given hash, `AA` starts at 1 and is incremented on every FAT entry that has the same hash. In practice, `AA` is almost always 1 because the probability of hash collisions is quite low. `BBBBBB` is an offset into the [filename table](#filename-table) divided by 4.

## SFNT Section
This section simply contains an array of filenames. Each filename is a null-terminated string, and must be aligned on 4 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`SFNT`) |
| 0x4 | 2 | Header size (must be 8) |
| 0x6 | 2 | Padding |
| 0x8 | | Filename table |
