## [NW](../../formats.md#nw) > [Model Archive](bfres.md) > Texture (FTEX)

An FTEX file is always contained in a [BFRES archive](bfres.md).

All offsets are relative to themselves.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FTEX`) |
| 0x4 | 156 | [Texture](../wiiu/gx2.md#gx2texture) |
| 0xA0 | 4 | Unknown |
| 0xA4 | 4 | Unknown |
| 0xA8 | 4 | Name offset |
| 0xAC | 4 | Path offset |
| 0xB0 | 4 | Image data offset |
| 0xB4 | 4 | Image mipmap offset |
| 0xB8 | 4 | Offset to user data [dictionary](bfres.md#dictionary) |
| 0xBC | 4 | Unknown |
