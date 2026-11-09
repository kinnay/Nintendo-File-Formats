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
| 0x70 | 16 | Unknown |
| 0x80 | 8 | Address of texture data (relocated) |
| 0x88 | 8 | Address of texture view (relocated) |
| 0x90 | 8 | User descriptor slot (filled at runtime, always 0) |
| | | Unknown |

#### nn::gfx::TextureInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Flags |
| 0x1 | 1 | [Storage dimension](#nngfximagestoragedimension) |
| 0x2 | 2 | Tile mode |
| 0x4 | 2 | Swizzle value |
| 0x6 | 2 | Mipmap count |
| 0x8 | 2 | Multisample count |
| 0xA | 2 | Unknown |
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
| Value | Description |
| --- | --- |
| ? | ? |

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
This section contains the raw texture data.
