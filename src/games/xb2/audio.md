## [XB2](../../formats.md#xb2)

Every offset have 4 hexa bytes

| Offset | Value | Description |
| --- | --- | --- |
| 0x0 | 0x10 | [File header](#file-header) |
| 0x10 | 0x5BFC0 | [File body](#file-body) ([encrypted](#encryption)) |
| 0x5BFD0 | 0x30 | [Crypto parameters](#encryption) |
