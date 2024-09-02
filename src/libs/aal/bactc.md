## [AAL](../../formats.md#aal) > Custom Curve (BACTC)

This page describes version 1 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`ACTC`) |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number (1) |
| 0x8 | 4 | Number of segments |
| 0xC | | Segment param (16 bytes per segment) |