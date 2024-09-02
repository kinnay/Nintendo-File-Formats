## [DKC:TF](../../formats.md#dkctf) > Texture File (TXTR)

Meta data: [NTextureFormat::SMetaData](#ntextureformatsmetadata)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

## TXTR Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | HEAD chunk ([NTextureFormat::STextureHeader](#ntextureformatstextureheader)) |
| [CChunkDescriptor] | GPU chunk. This chunk contains the texture buffers |

### NTextureFormat::STextureHeader
| Type | Description |
| --- | --- |
| Uint32 | [Type](#texture-type) |
| Uint32 | [Format](#texture-format) |
| Uint32 | Width |
| Uint32 | Height |
| Uint32 | Depth |
| Uint32 | Tile mode |
| Uint32 | Swizzle |
| [List]&lt;Uint32&gt; | Mipmap sizes |
| [NTextureFormat::STextureSamplerData](#ntextureformatstexturesamplerdata) | Sampler data |

#### NTextureFormat::STextureSamplerData
| Type | Description |
| --- | --- |
| Uint32 | Flags (always 0) |
| Uint8 | [Texture filter](enums.md#texture-filter) |
| Uint8 | [Texture wrap (x)](enums.md#texture-wrap) |
| Uint8 | [Texture wrap (y)](enums.md#texture-wrap) |
| Uint8 | [Texture wrap (z)](enums.md#texture-wrap) |

#### Texture Type
| ETextureType | GX2SurfaceDim |
| --- | --- |
| 0 | GX2_SURFACE_DIM_TEXTURE_1D |
| 1 | GX2_SURFACE_DIM_TEXTURE_2D |
| 2 | GX2_SURFACE_DIM_TEXTURE_3D |
| 3 | GX2_SURFACE_DIM_TEXTURE_CUBE |
| 4 | GX2_SURFACE_DIM_TEXTURE_1D_ARRAY |
| 5 | GX2_SURFACE_DIM_TEXTURE_2D_ARRAY |
| 6 | GX2_SURFACE_DIM_TEXTURE_2D_MSAA |
| 7 | GX2_SURFACE_DIM_TEXTURE_2D_MSAA_ARRAY |

#### Texture Format
| ETextureFormat | GX2SurfaceFormat |
| --- | --- |
| 0 | GX2_SURFACE_FORMAT_UNORM_R8 |
| 1 | GX2_SURFACE_FORMAT_SNORM_R8 |
| 2 | GX2_SURFACE_FORMAT_UINT_R8 |
| 3 | GX2_SURFACE_FORMAT_SINT_R8 |
| 4 | GX2_SURFACE_FORMAT_UNORM_R16 |
| 5 | GX2_SURFACE_FORMAT_SNORM_R16 |
| 6 | GX2_SURFACE_FORMAT_UINT_R16 |
| 7 | GX2_SURFACE_FORMAT_SINT_R16 |
| 8 | GX2_SURFACE_FORMAT_FLOAT_R16 |
| 9 | GX2_SURFACE_FORMAT_UINT_R32 |
| 10 | GX2_SURFACE_FORMAT_SINT_R32 |
| 11 | GX2_SURFACE_FORMAT_INVALID |
| 12 | GX2_SURFACE_FORMAT_UNORM_R8_G8_B8_A8 |
| 13 | GX2_SURFACE_FORMAT_SRGB_R8_G8_B8_A8 |
| 14 | GX2_SURFACE_FORMAT_FLOAT_R16_G16_B16_A16 |
| 15 | GX2_SURFACE_FORMAT_FLOAT_R32_G32_B32_A32 |
| 16 | GX2_SURFACE_FORMAT_UNORM_R16 |
| 17 | GX2_SURFACE_FORMAT_UNORM_R16 |
| 18 | GX2_SURFACE_FORMAT_UNORM_R24_X8 |
| 19 | GX2_SURFACE_FORMAT_FLOAT_R32 |
| 20 | GX2_SURFACE_FORMAT_UNORM_BC1 |
| 21 | GX2_SURFACE_FORMAT_SRGB_BC1 |
| 22 | GX2_SURFACE_FORMAT_UNORM_BC2 |
| 23 | GX2_SURFACE_FORMAT_SRGB_BC2 |
| 24 | GX2_SURFACE_FORMAT_UNORM_BC3 |
| 25 | GX2_SURFACE_FORMAT_SRGB_BC3 |
| 26 | GX2_SURFACE_FORMAT_UNORM_BC4 |
| 27 | GX2_SURFACE_FORMAT_SNORM_BC4 |
| 28 | GX2_SURFACE_FORMAT_UNORM_BC5 |
| 29 | GX2_SURFACE_FORMAT_SNORM_BC5 |
| 30 | GX2_SURFACE_FORMAT_FLOAT_R11_G11_B10 |
| 31 | GX2_SURFACE_FORMAT_FLOAT_R32 |
| 32 | GX2_SURFACE_FORMAT_FLOAT_R16_G16 |
| 33 | GX2_SURFACE_FORMAT_UNORM_R8_G8 |

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

[List]: types.md#list
[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor