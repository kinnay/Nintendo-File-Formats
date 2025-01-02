## [LMS](../../formats.md#lms) > File Format Overview

This page describes the general structure of files loaded by the LMS library. The files start with a [header](#file-header) which is followed by different kinds of [blocks](#block-header). All blocks are aligned to 16 bytes. The space between two blocks is padded with 0xAB bytes.

The following file formats are used by LMS:
* [MSBT files (messages)](msbt.md)
* [MSBP files (projects)](msbp.md)
* [MSBF files (flowcharts)](msbf.md)

## File Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Magic number |
| 0x8 | 2 | Endianness (0xFEFF=Big, 0xFFFE=Little) |
| 0xA | 2 | Unknown (always 0?) |
| 0xC | 1 | Message encoding (0=UTF-8, 1=UTF-16, 2=UTF-32) |
| 0xD | 1 | Version number |
| 0xE | 2 | Number of blocks |
| 0x10 | 2 | Unknown (always 0?) |
| 0x12 | 4 | Filesize |
| 0x16 | 10 | Padding |

## Block Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Block type |
| 0x4 | 4 | Block size (without header) |
| 0x8 | 8 | Padding |
| 0x10 | | Block data |

## Hash Tables
Many items (such as messages in [msbt files](msbt.md) or colors in [msbp files](msbp.md)) are looked up by label. The labels are looked up with a hash table and are stored in a different block than the items themselves. In official files the hash table always has a fixed number of buckets (101 in [msbt files](msbt.md), 29 in [msbp files](msbp.md)), even if it contains only a few labels.

The following hash algorithm is used:

```python
def calc_hash(label, num_buckets):
    hash = 0
    for char in label:
        hash = hash * 0x492 + ord(char)
    return (hash & 0xFFFFFFFF) % num_buckets
```

The block with the labels contains the following data:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of buckets |
| 0x4 | 8 per bucket | [Hash table buckets](#hash-table-bucket) |
| | Labels |

### Hash Table Bucket
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of labels |
| 0x4 | 4 | Offset to [labels](#label) |

### Label
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Length of label string |
| 0x1 | | Label string (without null terminator) |
| | 4 | Item index |