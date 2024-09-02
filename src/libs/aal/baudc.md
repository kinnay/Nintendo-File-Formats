## [AAL](/formats.md#aal) > Unit Distance Curve (BAUDC)

This file is referenced by an [audio attenuator](./baatn.md) and contains a unit distance curve.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("AUDC") |
| 0x4 | 2 | Endianness |
| 0x6 | 2 | Version number (1) |
| 0x8 | 4 | Curve type (0=logarithmic, 1=linear) |
| 0xC | 4 | Start value (float) |
| 0x10 | 4 | End value (float) |
| 0x14 | 4 | Hold distance (float) |
| 0x18 | 4 | Unit distance (float) |
| 0x1C | 4 | Decay ratio (float) |
| 0x20 | 4 | Culling start distance (float) |