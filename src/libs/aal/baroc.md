## [AAL](../../formats.md#aal) > Roll Off Curve (BAROC)

This page describes version 1 and 2 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`AROC`) |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number (1 or 2) |
| 0x8 | 4 | Roll off model |
| 0xC | 4 | Ref distance (float) |
| 0x10 | 4 | Max distance (float) |
| 0x14 | 4 | Roll off factor (float) |
| 0x18 | 4 | Start value (float) |
| 0x1C | 4 | Is increase mode |

Only present in version 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x20 | 4 | Culling start distance (float) |