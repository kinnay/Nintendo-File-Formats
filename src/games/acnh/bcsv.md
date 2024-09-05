[AC:NH](../../formats.md#acnh) > BCSV
---

Everything is encoded in little-endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of rows |
| 0x4 | 4 | Size of each row |
| 0x8 | 2 | Number of columns |
| 0xA | 1 | Flag 1 |
| 0xB | 1 | Flag 2 |

If flag 1 is set:

| Offset | Size | Description |
| --- | --- | --- |
| 0xC | 4 | Magic number (`BCSV` in reverse) |
| 0x10 | 2 | Version number |
| 0x12 | 10 | Padding |
| 0x1C | | [Column info](#column-info) |
| | | [Rows](#rows) |

If flag 1 is not set:

| Offset | Size | Description |
| --- | --- | --- |
| 0xC | | [Column info](#column-info) |
| | | [Rows](#rows) |

### Column Info
This section contains the following data for each column:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | CRC32 hash of column name |
| 0x4 | 4 | Offset to cell data in row |

### Rows
Every row contains the following data:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset of row relative to start of file |
| 0x4 | | Cell data |

Although the offset seems redundant, it is important to the parser. The parser uses it to find the start of the BCSV file, given a pointer to a row.

The format of the cell data depends on the columns that are specified in the [column info](#column-info).
