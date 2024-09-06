[AC:NH](../../formats.md#acnh) > BCSV
---

A BCSV file contains a table of information in a compact binary format.

A BCSV file contains three parts:
* [File header](#header)
* [Column information](#column-info)
* [Data rows](#rows)

Everything is encoded in little-endian byte order.

## Header

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of rows |
| 0x4 | 4 | Size of each row |
| 0x8 | 2 | Number of columns |
| 0xA | 1 | Has extended header |
| 0xB | 1 | Unknown flag |

If the extended header flag is set:

| Offset | Size | Description |
| --- | --- | --- |
| 0xC | 4 | Magic number (`BCSV` in reverse) |
| 0x10 | 2 | Version number |
| 0x12 | 10 | Padding |

## Column Info 
This section contains the following data for each column:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Hash of column name and type |
| 0x4 | 4 | Offset to cell data in row |

The hash is the CRC32 of `<name> <type>`, for example `UniqueID u16`.

Unfortunately, the actual column names are not stored in the file, which makes them difficult to recover. Similarly, it is difficult to determine the type, but it can sometimes be guessed by checking the data size.

## Rows
Every row contains the following data:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset of row relative to start of file |
| 0x4 | | Cell data |

Although the offset seems redundant, it is important to the parser. The parser uses it to find the start of the BCSV file, given a pointer to a row.

The format of the cell data depends on the columns that are specified in the [column info](#column-info).
