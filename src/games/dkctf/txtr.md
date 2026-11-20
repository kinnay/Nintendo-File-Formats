## [DKC:TF](../../formats.md#dkctf) > Texture File (TXTR)

Meta data: [NTextureFormat::SMetaData](#ntextureformatsmetadata)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

## TXTR Form
| Game | Reader Version | Writer Version |
| --- | --- | --- |
| DKC:TF Wii U | 14 | 14 |
| DKC:TF Switch | 15 | 16 |

Form content:

| Type | Description |
| --- | --- |
| [CChunkDescriptor] | HEAD chunk ([NTextureFormat::STextureHeader](#ntextureformatstextureheader)) |
| [CChunkDescriptor] | GPU chunk. This chunk contains the texture buffers |

### NTextureFormat::STextureHeader
| Type | Description |
| --- | --- |
| Uint32 | [Type](#etexturetype) |
| Uint32 | [Format](#etextureformat) |
| Uint32 | Width |
| Uint32 | Height |
| Uint32 | Depth |
| Uint32 | Tile mode |
| Uint32 | Swizzle |
| [List]&lt;Uint32&gt; | Mipmap sizes |
| [NTextureFormat::STextureSamplerData](#ntextureformatstexturesamplerdata) | Sampler data |

The tile mode and swizzle contain native values. On the Wii U, this is [`GX2TileMode`](../../libs/wiiu/gx2.md#gx2tilemode).

#### NTextureFormat::STextureSamplerData
| Type | Description |
| --- | --- |
| Uint32 | Flags |
| Uint8 | [Texture filter](enums.md#etexturefilter) |
| Uint8 | [Texture wrap (x)](enums.md#etexturewrap) |
| Uint8 | [Texture wrap (y)](enums.md#etexturewrap) |
| Uint8 | [Texture wrap (z)](enums.md#etexturewrap) |

#### ETextureType
| Value | Description |
| --- | --- |
| 0 | 1D |
| 1 | 2D |
| 2 | 3D |
| 3 | Cubemap |
| 4 | 1D array |
| 5 | 2D array |
| 6 | 2D multisample |
| 7 | 2D multisample array |
| 8 | Cubemap array |

#### ETextureFormat
| Value | Description |
| --- | --- |
| 0 | `R8 UNORM` |
| 1 | `R8 SNORM` |
| 2 | `R8 UINT` |
| 3 | `R8 SINT` |
| 4 | `R16 UNORM` |
| 5 | `R16 SNORM` |
| 6 | `R16 UINT` |
| 7 | `R16 SINT` |
| 8 | `R16 FLOAT` |
| 9 | `R32 UINT` |
| 10 | `R32 SINT` |
| 11 | `RGB8 UNORM` |
| 12 | `RGBA8 UNORM` |
| 13 | `RGBA8 SRGB` |
| 14 | `RGBA16 FLOAT` |
| 15 | `RGBA32 FLOAT` |
| 16 | `DEPTH16 UNORM` |
| 17 | `DEPTH16 UNORM` |
| 18 | `DEPTH24 STENCIL8 UNORM` |
| 19 | `DEPTH32 FLOAT` |
| 20 | `BC1 UNORM` |
| 21 | `BC1 SRGB` |
| 22 | `BC2 UNORM` |
| 23 | `BC2 SRGB` |
| 24 | `BC3 UNORM` |
| 25 | `BC3 SRGB` |
| 26 | `BC4 UNORM` |
| 27 | `BC4 SNORM` |
| 28 | `BC5 UNORM` |
| 29 | `BC5 SNORM` |
| 30 | `RG11B10 FLOAT` |
| 31 | `R32 FLOAT` |
| 32 | `RG8 UNORM` |
| 33 | `RG8 SNORM` |
| 34 | `RG8 UINT` |
| 35 | `RG8 SINT` |
| 36 | `RG16 FLOAT` |
| 37 | `RG16 UNORM` |
| 38 | `RG16 SNORM` |
| 39 | `RG16 UINT` |
| 40 | `RG16 SINT` |
| 41 | `RGB10A2 UNORM` |
| 42 | `RGB10A2 UINT` |
| 43 | `RG32 UINT` |
| 44 | `RG32 SINT` |
| 45 | `RG32 FLOAT` |
| 46 | `RGBA16 UNORM` |
| 47 | `RGBA16 SNORM` |
| 48 | `RGBA16 UINT` |
| 49 | `RGBA16 SINT` |
| 50 | `RGBA32 UINT` |
| 51 | `RGBA32 SINT` |
| 52 | Invalid |
| 53 | `RGBA ASTC 4x4 UNORM` |
| 54 | `RGBA ASTC 5x4 UNORM` |
| 55 | `RGBA ASTC 5x5 UNORM` |
| 56 | `RGBA ASTC 6x5 UNORM` |
| 57 | `RGBA ASTC 6x6 UNORM` |
| 58 | `RGBA ASTC 8x5 UNORM` |
| 59 | `RGBA ASTC 8x6 UNORM` |
| 60 | `RGBA ASTC 8x8 UNORM` |
| 61 | `RGBA ASTC 10x5 UNORM` |
| 62 | `RGBA ASTC 10x6 UNORM` |
| 63 | `RGBA ASTC 10x8 UNORM` |
| 64 | `RGBA ASTC 10x10 UNORM` |
| 65 | `RGBA ASTC 12x10 UNORM` |
| 66 | `RGBA ASTC 12x12 UNORM` |
| 67 | `RGBA ASTC 4x4 SRGB` |
| 68 | `RGBA ASTC 5x4 SRGB` |
| 69 | `RGBA ASTC 5x5 SRGB` |
| 70 | `RGBA ASTC 6x5 SRGB` |
| 71 | `RGBA ASTC 6x6 SRGB` |
| 72 | `RGBA ASTC 8x5 SRGB` |
| 73 | `RGBA ASTC 8x6 SRGB` |
| 74 | `RGBA ASTC 8x8 SRGB` |
| 75 | `RGBA ASTC 10x5 SRGB` |
| 76 | `RGBA ASTC 10x6 SRGB` |
| 77 | `RGBA ASTC 10x8 SRGB` |
| 78 | `RGBA ASTC 10x10 SRGB` |
| 79 | `RGBA ASTC 12x10 SRGB` |
| 80 | `RGBA ASTC 12x12 SRGB` |

## NTextureFormat::SMetaData
| Type | Description |
| --- | --- |
| Uint32 | Unknown (always 4) |
| Uint32 | Alloc category |
| Uint32 | Filesize without GPU chunk |
| Uint32 | Required data alignment |
| Uint32 | Compressed data offset |
| Uint32 | Compressed data size |
| [List]&lt;[NTextureFormat::SCompressedBufferInfo](#ntextureformatscompressedbufferinfo)&gt; | Buffer info |

### NTextureFormat::SCompressedBufferInfo
| Type | Description |
| --- | --- |
| Uint32 | Decompressed size |
| Uint32 | Compressed size |
| Uint32 | Offset |

See [compression algorithms](compression.md).

[List]: types.md#list
[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
