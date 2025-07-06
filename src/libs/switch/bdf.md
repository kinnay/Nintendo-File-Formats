## [Switch](../../formats.md#nintendo-switch) > BDF Files

A BDF file contains a list of certificates for the SSL sysmodule.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`sslT`) |
| 0x4 | 4 | Number of entries |

Every entry is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Data size |
| 0xC | 4 | Data offset (relative to start of entry table) |
