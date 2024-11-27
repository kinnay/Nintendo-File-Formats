## [GFD](../../formats.md#gfd) > Texture / Shader (Gfx2)

This file contains textures or shaders and usually has the filename extension 'gtx' or 'gsh'. The file starts with a [header](#file-header), which is followed by one or more [blocks](#block). A special [block type](#block-types) indicates the end of the file.

The file format is closely tied to the GX2 framework, which is the graphics library of the Wii U.

## File Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`Gfx2`) |
| 0x4 | 4 | Header size (always 0x20) |
| 0x8 | 4 | Major version (should be 7) |
| 0xC | 4 | Minor version (should be 1) |
| 0x10 | 4 | GPU version (should be 2) |
| 0x14 | 4 | Alignment mode (0 or 1). If enabled, padding blocks are added to align shader and texture data. |
| 0x18 | 8 | Padding |

## Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`BLK{`) |
| 0x4 | 4 | Header size (always 0x20) |
| 0x8 | 4 | Major version (should be 1) |
| 0xC | 4 | Minor version (should be 0) |
| 0x10 | 4 | Block type |
| 0x14 | 4 | Data size |
| 0x18 | 8 | Padding |
| 0x20 | | Data |

### Block Types
| Value | Type |
| --- | --- |
| 1 | End of file |
| 2 | Padding (for alignment) |
| 3 | Vertex [shader header](#shader-blocks) |
| 5 | Vertex [shader program](#shader-blocks) |
| 6 | Pixel [shader header](#shader-blocks) |
| 7 | Pixel [shader program](#shader-blocks) |
| 8 | Geometry [shader header](#shader-blocks) |
| 9 | Geometry [shader program](#shader-blocks) |
| 10 | Geometry [shader copy program](#shader-blocks) |
| 11 | [Texture header](#texture-blocks) |
| 12 | [Texture image data](#texture-blocks) |
| 13 | [Texture mipmap data](#texture-blocks) |

### Texture Blocks
The texture header block contains a [`GX2Texture`](../wiiu/gx2.md#gx2texture) structure. The image and mipmap data blocks contain raw texture data, and are stored immediately behind the texture header block that they belong to. The mipmap block is optional.

### Shader Blocks
The shader program blocks contain raw shader data and are stored immediately behind the shader header block that they belong to.

The shader header block is a bit complicated. In essence, it contains a [`GX2VertexShader`](../wiiu/gx2.md#gx2vertexshader), [`GX2PixelShader`](../wiiu/gx2.md#gx2pixelshader) or [`GX2GeometryShader`](../wiiu/gx2.md#gx2geometryshader) structure (depending on the block type). However, these structure contain several pointers, and, for obvious reasons, it is impossible to store raw pointers in a file.

The shader header block is layed out as follows:

* Main shader structure
* Other structures that are required by main structure
* String table
* [Relocation table](#relocation-table)
* [Relocation info](#relocation-info)

Each pointer in a structure is stored as `0xAAABBBBB`, where `AAA` is a tag that specifies the type of offset, and `BBBBB` is the actual offset (relative to the start of the shader header block body).

The following tags are used:

| Tag | Description |
| --- | --- |
| 0xCA7 | String |
| 0xD06 | Data |

### Relocation Info
The relocation info is always stored at the end of the shader header block and makes it possible to convert offsets to pointers without knowing anything about the shader structures.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`}BLK`) |
| 0x4 | 4 | Size (always 0x28) |
| 0x8 | 4 | Always 0 |
| 0xC | 4 | Total size of shader structures and string table |
| 0x10 | 4 | Data pointer to shader structures and string table |
| 0x14 | 4 | Size of string table |
| 0x18 | 4 | Data pointer to string table |
| 0x1C | 4 | Must be 0 (updated at runtime) |
| 0x20 | 4 | Number of relocations |
| 0x24 | 4 | Data pointer to relocation table |

### Relocation Table
The relocation table tells the loader which fields are offsets that need fixing. It contains a list of offsets (with tag) that point to the offsets that should be relocated.