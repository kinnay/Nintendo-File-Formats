## [NW](../../formats.md#nw) > Textures (BNTX)

This is the texture archive format that is used on the Nintendo Switch and Switch 2. This page describes version 4.0.0 of the file format.

A BNTX file can contain multiple textures.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | [Binary file header](../switch/binary.md#file-header) (`BNTX\0\0\0\0`) |
| 0x20 | 56 | [Texture container data](#texture-container-data) |
| 0x58 | 320 | [Memory pool](#memory-pool) (filled with zeros) |
| 0x198 | 8 * N | Addresses of [nn::gfx::ResTexture](#nngfxrestexture) blocks (relocated) |
| | | [String pool](#string-pool) |
| | | [nn::gfx::ResTexture](#nngfxrestexture) blocks |
| | | [Texture data](#texture-data-block) block |
| | | [Relocation table](../switch/binary.md#relocation-table) |

A BNTX file contains two [relocations sections](../switch/binary.md#relocation-table):
* The first section contains addresses that point into the file header, string table or a [nn::gfx::ResTexture](#nngfxrestexture) block.
* The second section contains addresses that point into the [texture data block](#texture-data-block).

Pointers that are relocated are marked as such on this page.

### Texture Container Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x20 | 4 | Platform (`NX  ` or `OUNC`) |
| 0x24 | 4 | Number of textures (N) |
| 0x28 | 8 | Address of texture pointers (relocated) |
| 0x30 | 8 | Address of [texture data](#texture-data-block) block (relocated) |
| 0x38 | 8 | Address of [dictionary](#string-pool) (relocated) |
| 0x40 | 8 | Address of [memory pool](#memory-pool) (relocated) |
| 0x48 | 16 | Padding |

### Memory Pool
This section is only used at runtime and always contains 320 null bytes in the file.

### String Pool
This is a standard [string pool section](../switch/binary.md#string-pool), except there is a [dictionary](../switch/binary.md#dictionary) embedded in the string pool section behind the strings.

The dictionary contains the texture names.

### nn::gfx::ResTexture
This contains information about a texture. There is one `nn::gfx::ResTexture` block per texture.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [Block header](../switch/binary.md#block-header) (`BRTI`) |
| 0x10 | 64 | [Texture information](#nngfxtextureinfo) |
| 0x50 | 4 | Image data size |
| 0x54 | 4 | Image data alignment |
| 0x58 | 1 | [Channel mapping](#nngfxchannelmapping) (red) |
| 0x59 | 1 | [Channel mapping](#nngfxchannelmapping) (green) |
| 0x5A | 1 | [Channel mapping](#nngfxchannelmapping) (blue) |
| 0x5B | 1 | [Channel mapping](#nngfxchannelmapping) (alpha) |
| 0x5C | 1 | [Image dimension](#nngfximagedimension) |
| 0x5D | 3 | Padding |
| 0x60 | 8 | Address of texture name in [string pool](#string-pool) (relocated) |
| 0x68 | 8 | Address of [texture container data](#texture-container-data) (relocated) |
| 0x70 | 8 | Address of mipmap address table (relocated) |
| 0x78 | 8 | Address of user data (relocated) |
| 0x80 | 8 | Address of texture object (relocated) |
| 0x88 | 8 | Address of texture view (relocated) |
| 0x90 | 8 | Filled at runtime, always 0 |
| 0x98 | 8 | Unknown |
| 0xA0 | 256 | Texture object (filled at runtime, always 0) |
| 0x1A0 | 256 | Texture view (filled at runtime, always 0) |
| 0x2A0 | | Mipmap address table (8 bytes per mipmap, relocated) |

#### nn::gfx::TextureInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Flags |
| 0x1 | 1 | [Storage dimension](#nngfximagestoragedimension) |
| 0x2 | 2 | [Tile mode](#nngfxtilemode) |
| 0x4 | 2 | Swizzle value |
| 0x6 | 2 | Mipmap count |
| 0x8 | 2 | Multisample count |
| 0xA | 2 | Padding |
| 0xC | 4 | [Image format](#nngfximageformat) |
| 0x10 | 4 | Usage flags |
| 0x14 | 4 | Width |
| 0x18 | 4 | Height |
| 0x1C | 4 | Depth |
| 0x20 | 4 | Array length |
| 0x24 | 8 | Packaged texture layout |
| 0x2C | 20 | Padding |

#### nn::gfx::ImageStorageDimension
| Value | Description |
| --- | --- |
| 1 | 1D |
| 2 | 2D |
| 3 | 3D |

#### nn::gfx::ImageDimension
| Value | Description |
| --- | --- |
| 0 | 1D |
| 1 | 2D |
| 2 | 3D |
| 3 | Cube map |
| 4 | 1D array |
| 5 | 2D array |
| 8 | Cube map array |

#### nn::gfx::ImageFormat
The image format is encoded as <code>([channel_format](#nngfxchannelformat) << 8) | [type_format](#nngfxtypeformat)</code>.

#### nn::gfx::TypeFormat
| Value | Description |
| --- | --- |
| 1 | `UNORM` |
| 2 | `SNORM` |
| 3 | `UINT` |
| 4 | `SINT` |
| 5 | `SINGLE` |
| 6 | `SRGB` |
| 7 | `UHALF` |

#### nn::gfx::ChannelFormat
| Value | Description |
| --- | --- |
| 2 | `R8` |
| 3 | `RGBA4` |
| 5 | `RGB5A1` |
| 6 | `A1BGR5` |
| 7 | `RGB565` |
| 8 | `BGR565` |
| 9 | `RG8` |
| 10 | `R16` |
| 11 | `RGBA8` |
| 12 | `BGRA8` |
| 13 | `RGB9E5` |
| 14 | `RGB10A2` |
| 15 | `R11G11B10` |
| 18 | `RG16` |
| 19 | `DEPTH24_STENCIL8` |
| 20 | `R32` |
| 21 | `RGBA16` |
| 22 | `DEPTH32_STENCIL8` |
| 23 | `RG32` |
| 24 | `RGB32` |
| 25 | `RGBA32` |
| 26 | `RGBA_DXT1` |
| 27 | `RGBA_DXT3` |
| 28 | `RGBA_DXT5` |
| 29 | `RGTC1` |
| 30 | `RGTC2` |
| 31 | `BPTC_FLOAT` |
| 32 | `BPTC_UNORM` |
| 45 | `RGBA_ASTC_4x4` |
| 46 | `RGBA_ASTC_5x4` |
| 47 | `RGBA_ASTC_5x5` |
| 48 | `RGBA_ASTC_6x5` |
| 49 | `RGBA_ASTC_6x6` |
| 50 | `RGBA_ASTC_8x5` |
| 51 | `RGBA_ASTC_8x6` |
| 52 | `RGBA_ASTC_8x8` |
| 53 | `RGBA_ASTC_10x5` |
| 54 | `RGBA_ASTC_10x6` |
| 55 | `RGBA_ASTC_10x8` |
| 56 | `RGBA_ASTC_10x10` |
| 57 | `RGBA_ASTC_12x10` |
| 58 | `RGBA_ASTC_12x12` |
| 59 | `BGR5A1` |

#### nn::gfx::TileMode
| Value | Description |
| --- | --- |
| 0 | Swizzled |
| 1 | Linear |

#### nn::gfx::ChannelMapping
| Value | Description |
| --- | --- |
| 0 | Constant zero |
| 1 | Constant one |
| 2 | Red |
| 3 | Green |
| 4 | Blue |
| 5 | Alpha |

### Texture Data Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [Block header](../switch/binary.md#block-header) (`BRTD`) |
| 0x10 | | Raw texture data |

The block header is placed so that the raw texture data is aligned on the required byte boundary.

### References
* [https://github.com/Tyulis/3DSkit/blob/master/doc/BNTX.md](https://github.com/Tyulis/3DSkit/blob/master/doc/BNTX.md)
