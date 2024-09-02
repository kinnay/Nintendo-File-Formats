## [AAL](/formats.md#aal) > Audio Resource List

A .barslist file contains an audio resource list.

This page describes version 1 of the file format.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`ARSL`) |
| 0x4 | 2 | BOM (always 0xFEFF) |
| 0x6 | 2 | Version number |
| 0x8 | 4 | Offset into string table for the name of this audio resource list |
| 0xC | 4 | Number of audio resources |
| 0x10 | | For every audio resource, an offset (4 bytes) into the string table for its filename |
| | | String table (list of null terminated strings) |
