## [AAL](../../formats.md#aal) > Attenuation Culling (BAACL)

This page describes version 1 and 2 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`AACL`) |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number (1 or 2) |
| 0x8 | 4 | Culling distance (float) |
| 0xC | 4 | Culling mergin (float) |

Only present in version 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x10 | 1 | Is priority down enabled |