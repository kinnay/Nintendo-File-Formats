
On the Wii U, GX2 is the system library that provides an interface to the GPU, similar to OpenGL or Vulkan.

This page describes the various data structures and enums that are exposed by the GX2 library that may be seen in file formats.

Some structures contain pointers. These are usually replaced by offsets, but the details depend on the file format.

Structures:

* [GX2Surface](#gx2surface)
* [GX2Texture](#gx2texture)
* [GX2VertexShader](#gx2vertexshader)
* [GX2PixelShader](#gx2pixelshader)
* [GX2GeometryShader](#gx2geometryshader)
* [GX2ComputeShader](#gx2computeshader)
* [GX2UniformBlock](#gx2uniformblock)
* [GX2UniformVar](#gx2uniformvar)
* [GX2UniformInitialValue](#gx2uniforminitialvalue)
* [GX2LoopVar](#gx2loopvar)
* [GX2SamplerVar](#gx2samplervar)
* [GX2AttribVar](#gx2attribvar)
* [GX2RBuffer](#gx2rbuffer)

Enums:

* [GX2SurfaceDim](#gx2surfacedim)
* [GX2SurfaceFormat](#gx2surfaceformat)
* [GX2AAMode](#gx2aamode)
* [GX2SurfaceUse](#gx2surfaceuse)
* [GX2TileMode](#gx2tilemode)
* [GX2ShaderMode](#gx2shadermode)
* [GX2ShaderVarType](#gx2shadervartype)
* [GX2SamplerVarType](#gx2samplervartype)
* [GX2ResourceFlags](#gx2resourceflags)

## GX2Surface
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Dimension](#gx2surfacedim) |
| 0x4 | 4 | Width |
| 0x8 | 4 | Height |
| 0xC | 4 | Depth |
| 0x10 | 4 | Mip levels |
| 0x14 | 4 | [Format](#gx2surfaceformat) |
| 0x18 | 4 | [AA mode](#gx2aamode) |
| 0x1C | 4 | [Surface use](#gx2surfaceuse) |
| 0x20 | 4 | Image size |
| 0x24 | 4 | Image data (pointer) |
| 0x28 | 4 | Mipmap size |
| 0x2C | 4 | Mipmap data (pointer) |
| 0x30 | 4 | [Tile mode](#gx2tilemode) |
| 0x34 | 4 | Swizzle value |
| 0x38 | 4 | Alignment |
| 0x3C | 4 | Pitch |
| 0x40 | 4 * 13 | Mip level offsets |

## GX2Texture
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 116 | [Surface](#gx2surface) |
| 0x74 | 4 | View first mip |
| 0x78 | 4 | View num mips |
| 0x7C | 4 | View first slice |
| 0x80 | 4 | View num slices |
| 0x84 | 4 | Comp map |
| 0x88 | 4 * 5 | Registers |

## GX2VertexShader
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 * 52 | Registers |
| 0xD0 | 4 | Program size |
| 0xD4 | 4 | Program pointer |
| 0xD8 | 4 | [Shader mode](#gx2shadermode) |
| 0xDC | 4 | Number of [uniform blocks](#gx2uniformblock) |
| 0xE0 | 4 | Pointer to [uniform blocks](#gx2uniformblock) |
| 0xE4 | 4 | Number of [uniform vars](#gx2uniformvar) |
| 0xE8 | 4 | Pointer to [uniform vars](#gx2uniformvar) |
| 0xEC | 4 | Number of [initial values](#gx2uniforminitialvalue) |
| 0xF0 | 4 | Pointer to [initial values](#gx2uniforminitialvalue) |
| 0xF4 | 4 | Number of [loop vars](#gx2loopvar) |
| 0xF8 | 4 | Pointer to [loop vars](#gx2loopvar) |
| 0xFC | 4 | Number of [sampler vars](#gx2samplervar) |
| 0x100 | 4 | Pointer to [sampler vars](#gx2samplervar) |
| 0x104 | 4 | Number of [attrib vars](#gx2attribvar) |
| 0x108 | 4 | Pointer to [attrib vars](#gx2attribvar) |
| 0x10C | 4 | Ring item size |
| 0x110 | 4 | Has stream out |
| 0x114 | 4 * 4 | Stream out stride |
| 0x124 | 16 | [R buffer](#gx2rbuffer) |

## GX2PixelShader
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 * 41 | Registers |
| 0xA4 | 4 | Program size |
| 0xA8 | 4 | Program pointer |
| 0xAC | 4 | [Shader mode](#gx2shadermode) |
| 0xB0 | 4 | Number of [uniform blocks](#gx2uniformblock) |
| 0xB4 | 4 | Pointer to [uniform blocks](#gx2uniformblock) |
| 0xB8 | 4 | Number of [uniform vars](#gx2uniformvar) |
| 0xBC | 4 | Pointer to [uniform vars](#gx2uniformvar) |
| 0xC0 | 4 | Number of [initial values](#gx2uniforminitialvalue) |
| 0xC4 | 4 | Pointer to [initial values](#gx2uniforminitialvalue) |
| 0xC8 | 4 | Number of [loop vars](#gx2loopvar) |
| 0xCC | 4 | Pointer to [loop vars](#gx2loopvar) |
| 0xD0 | 4 | Number of [sampler vars](#gx2samplervar) |
| 0xD4 | 4 | Pointer to [sampler vars](#gx2samplervar) |
| 0xD8 | 16 | [R buffer](#gx2rbuffer) |

## GX2GeometryShader
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 * 19 | Registers |
| 0x4C | 4 | Program size |
| 0x50 | 4 | Program pointer |
| 0x54 | 4 | Vertex program size |
| 0x58 | 4 | Vertex program pointer |
| 0x5C | 4 | [Shader mode](#gx2shadermode) |
| 0x60 | 4 | Number of [uniform blocks](#gx2uniformblock) |
| 0x64 | 4 | Pointer to [uniform blocks](#gx2uniformblock) |
| 0x68 | 4 | Number of [uniform vars](#gx2uniformvar) |
| 0x6C | 4 | Pointer to [uniform vars](#gx2uniformvar) |
| 0x70 | 4 | Number of [initial values](#gx2uniforminitialvalue) |
| 0x74 | 4 | Pointer to [initial values](#gx2uniforminitialvalue) |
| 0x78 | 4 | Number of [loop vars](#gx2loopvar) |
| 0x7C | 4 | Pointer to [loop vars](#gx2loopvar) |
| 0x80 | 4 | Number of [sampler vars](#gx2samplervar) |
| 0x84 | 4 | Pointer to [sampler vars](#gx2samplervar) |
| 0x88 | 4 | Ring item size |
| 0x8C | 4 | Has stream out |
| 0x90 | 4 * 4 | Stream out stride |
| 0xA0 | 16 | [R buffer](#gx2rbuffer) |

## GX2ComputeShader
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 * 12 | Registers |
| 0x30 | 4 | Program size |
| 0x34 | 4 | Program pointer |
| 0x38 | 4 | Number of [uniform blocks](#gx2uniformblock) |
| 0x3C | 4 | Pointer to [uniform blocks](#gx2uniformblock) |
| 0x40 | 4 | Number of [uniform vars](#gx2uniformvar) |
| 0x44 | 4 | Pointer to [uniform vars](#gx2uniformvar) |
| 0x48 | 4 | Number of [initial values](#gx2uniforminitialvalue) |
| 0x4C | 4 | Pointer to [initial values](#gx2uniforminitialvalue) |
| 0x50 | 4 | Number of [loop vars](#gx2loopvar) |
| 0x54 | 4 | Pointer to [loop vars](#gx2loopvar) |
| 0x58 | 4 | Number of [sampler vars](#gx2samplervar) |
| 0x5C | 4 | Pointer to [sampler vars](#gx2samplervar) |
| 0x60 | 4 | Work group size X |
| 0x64 | 4 | Work group size Y |
| 0x68 | 4 | Work group size Z |
| 0x6C | 4 | Over 64 mode |
| 0x70 | 4 | Number of waves per SIMD |
| 0x74 | 16 | [R buffer](#gx2rbuffer) |

## GX2UniformBlock
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name pointer |
| 0x4 | 4 | Offset |
| 0x8 | 4 | Size |

## GX2UniformVar
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name pointer |
| 0x4 | 4 | [Type](#gx2shadervartype) |
| 0x8 | 4 | Count |
| 0xC | 4 | Offset |
| 0x10 | 4 | Block |

## GX2UniformInitialValue
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 * 4 | Value (floats) |
| 0x10 | 4 | Offset |

## GX2LoopVar
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset |
| 0x4 | 4 | Value |

## GX2SamplerVar
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name pointer |
| 0x4 | 4 | [Type](#gx2samplervartype) |
| 0x8 | 4 | Location |

## GX2AttribVar
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name pointer |
| 0x4 | 4 | [Type](#gx2shadervartype) |
| 0x8 | 4 | Count |
| 0xC | 4 | Location |

## GX2RBuffer
This structure is only used internally and always cleared in files.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Resource flags](#gx2resourceflags) |
| 0x4 | 4 | Element size |
| 0x8 | 4 | Element count |
| 0xC | 4 | Buffer pointer |

## GX2SurfaceDim
| Value | Description |
| --- | --- |
| 0 | `GX2_SURFACE_DIM_TEXTURE_1D` |
| 1 | `GX2_SURFACE_DIM_TEXTURE_2D` |
| 2 | `GX2_SURFACE_DIM_TEXTURE_3D` |
| 3 | `GX2_SURFACE_DIM_TEXTURE_CUBE` |
| 4 | `GX2_SURFACE_DIM_TEXTURE_1D_ARRAY` |
| 5 | `GX2_SURFACE_DIM_TEXTURE_2D_ARRAY` |
| 6 | `GX2_SURFACE_DIM_TEXTURE_2D_MSAA` |
| 7 | `GX2_SURFACE_DIM_TEXTURE_2D_MSAA_ARRAY` |

## GX2SurfaceFormat
| Value | Description |
| --- | --- |
| `0x0` | `GX2_SURFACE_FORMAT_INVALID` |
| `0x1` | `GX2_SURFACE_FORMAT_UNORM_R8` |
| `0x2` | `GX2_SURFACE_FORMAT_UNORM_R4_G4` |
| `0x5` | `GX2_SURFACE_FORMAT_UNORM_R16` |
| `0x7` | `GX2_SURFACE_FORMAT_UNORM_R8_G8` |
| `0x8` | `GX2_SURFACE_FORMAT_UNORM_R5_G6_B5` |
| `0xA` | `GX2_SURFACE_FORMAT_UNORM_R5_G5_B5_A1` |
| `0xB` | `GX2_SURFACE_FORMAT_UNORM_R4_G4_B4_A4` |
| `0xC` | `GX2_SURFACE_FORMAT_UNORM_A1_B5_G5_R5` |
| `0xF` | `GX2_SURFACE_FORMAT_UNORM_R16_G16` |
| `0x11` | `GX2_SURFACE_FORMAT_UNORM_R24_X8` |
| `0x19` | `GX2_SURFACE_FORMAT_UNORM_R10_G10_B10_A2` |
| `0x1A` | `GX2_SURFACE_FORMAT_UNORM_R8_G8_B8_A8` |
| `0x1B` | `GX2_SURFACE_FORMAT_UNORM_A2_B10_G10_R10` |
| `0x1F` | `GX2_SURFACE_FORMAT_UNORM_R16_G16_B16_A16` |
| `0x31` | `GX2_SURFACE_FORMAT_UNORM_BC1` |
| `0x32` | `GX2_SURFACE_FORMAT_UNORM_BC2` |
| `0x33` | `GX2_SURFACE_FORMAT_UNORM_BC3` |
| `0x34` | `GX2_SURFACE_FORMAT_UNORM_BC4` |
| `0x35` | `GX2_SURFACE_FORMAT_UNORM_BC5` |
| `0x81` | `GX2_SURFACE_FORMAT_UNORM_NV12` |
| `0x101` | `GX2_SURFACE_FORMAT_UINT_R8` |
| `0x105` | `GX2_SURFACE_FORMAT_UINT_R16` |
| `0x107` | `GX2_SURFACE_FORMAT_UINT_R8_G8` |
| `0x10D` | `GX2_SURFACE_FORMAT_UINT_R32` |
| `0x10F` | `GX2_SURFACE_FORMAT_UINT_R16_G16` |
| `0x111` | `GX2_SURFACE_FORMAT_UINT_X24_G8` |
| `0x119` | `GX2_SURFACE_FORMAT_UINT_R10_G10_B10_A2` |
| `0x11A` | `GX2_SURFACE_FORMAT_UINT_R8_G8_B8_A8` |
| `0x11B` | `GX2_SURFACE_FORMAT_UINT_A2_B10_G10_R10` |
| `0x11C` | `GX2_SURFACE_FORMAT_UINT_G8_X24` |
| `0x11D` | `GX2_SURFACE_FORMAT_UINT_R32_G32` |
| `0x11F` | `GX2_SURFACE_FORMAT_UINT_R16_G16_B16_A16` |
| `0x122` | `GX2_SURFACE_FORMAT_UINT_R32_G32_B32_A32` |
| `0x201` | `GX2_SURFACE_FORMAT_SNORM_R8` |
| `0x205` | `GX2_SURFACE_FORMAT_SNORM_R16` |
| `0x207` | `GX2_SURFACE_FORMAT_SNORM_R8_G8` |
| `0x20F` | `GX2_SURFACE_FORMAT_SNORM_R16_G16` |
| `0x219` | `GX2_SURFACE_FORMAT_SNORM_R10_G10_B10_A2` |
| `0x21A` | `GX2_SURFACE_FORMAT_SNORM_R8_G8_B8_A8` |
| `0x21F` | `GX2_SURFACE_FORMAT_SNORM_R16_G16_B16_A16` |
| `0x234` | `GX2_SURFACE_FORMAT_SNORM_BC4` |
| `0x235` | `GX2_SURFACE_FORMAT_SNORM_BC5` |
| `0x301` | `GX2_SURFACE_FORMAT_SINT_R8` |
| `0x305` | `GX2_SURFACE_FORMAT_SINT_R16` |
| `0x307` | `GX2_SURFACE_FORMAT_SINT_R8_G8` |
| `0x30D` | `GX2_SURFACE_FORMAT_SINT_R32` |
| `0x30F` | `GX2_SURFACE_FORMAT_SINT_R16_G16` |
| `0x319` | `GX2_SURFACE_FORMAT_SINT_R10_G10_B10_A2` |
| `0x31A` | `GX2_SURFACE_FORMAT_SINT_R8_G8_B8_A8` |
| `0x31D` | `GX2_SURFACE_FORMAT_SINT_R32_G32` |
| `0x31F` | `GX2_SURFACE_FORMAT_SINT_R16_G16_B16_A16` |
| `0x322` | `GX2_SURFACE_FORMAT_SINT_R32_G32_B32_A32` |
| `0x41A` | `GX2_SURFACE_FORMAT_SRGB_R8_G8_B8_A8` |
| `0x431` | `GX2_SURFACE_FORMAT_SRGB_BC1` |
| `0x432` | `GX2_SURFACE_FORMAT_SRGB_BC2` |
| `0x433` | `GX2_SURFACE_FORMAT_SRGB_BC3` |
| `0x806` | `GX2_SURFACE_FORMAT_FLOAT_R16` |
| `0x80E` | `GX2_SURFACE_FORMAT_FLOAT_R32` |
| `0x810` | `GX2_SURFACE_FORMAT_FLOAT_R16_G16` |
| `0x811` | `GX2_SURFACE_FORMAT_FLOAT_D24_S8` |
| `0x816` | `GX2_SURFACE_FORMAT_FLOAT_R11_G11_B10` |
| `0x81C` | `GX2_SURFACE_FORMAT_FLOAT_X8_X24` |
| `0x81E` | `GX2_SURFACE_FORMAT_FLOAT_R32_G32` |
| `0x820` | `GX2_SURFACE_FORMAT_FLOAT_R16_G16_B16_A16` |
| `0x823` | `GX2_SURFACE_FORMAT_FLOAT_R32_G32_B32_A32` |

## GX2AAMode
| Value | Description |
| --- | --- |
| 0 | `GX2_AA_MODE_1X` |
| 1 | `GX2_AA_MODE_2X` |
| 2 | `GX2_AA_MODE_4X` |
| 3 | `GX2_AA_MODE_8X` |

## GX2SurfaceUse
This is a bitfield.

| Mask | Description |
| --- | --- |
| `0x0` | `GX2_SURFACE_USE_NONE` |
| `0x1` | `GX2_SURFACE_USE_TEXTURE` |
| `0x2` | `GX2_SURFACE_USE_COLOR_BUFFER` |
| `0x4` | `GX2_SURFACE_USE_DEPTH_BUFFER` |
| `0x8` | `GX2_SURFACE_USE_SCAN_BUFFER` |
| `0x80000000` | `GX2_SURFACE_USE_TV` |

## GX2TileMode
| Value | Description |
| --- | --- |
| 0 | `GX2_TILE_MODE_DEFAULT` |
| 1 | `GX2_TILE_MODE_LINEAR_ALIGNED` |
| 2 | `GX2_TILE_MODE_TILED_1D_THIN1` |
| 3 | `GX2_TILE_MODE_TILED_1D_THICK` |
| 4 | `GX2_TILE_MODE_TILED_2D_THIN1` |
| 5 | `GX2_TILE_MODE_TILED_2D_THIN2` |
| 6 | `GX2_TILE_MODE_TILED_2D_THIN4` |
| 7 | `GX2_TILE_MODE_TILED_2D_THICK` |
| 8 | `GX2_TILE_MODE_TILED_2B_THIN1` |
| 9 | `GX2_TILE_MODE_TILED_2B_THIN2` |
| 10 | `GX2_TILE_MODE_TILED_2B_THIN4` |
| 11 | `GX2_TILE_MODE_TILED_2B_THICK` |
| 12 | `GX2_TILE_MODE_TILED_3D_THIN1` |
| 13 | `GX2_TILE_MODE_TILED_3D_THICK` |
| 14 | `GX2_TILE_MODE_TILED_3B_THIN1` |
| 15 | `GX2_TILE_MODE_TILED_3B_THICK` |
| 16 | `GX2_TILE_MODE_LINEAR_SPECIAL` |

## GX2ShaderMode
| Value | Description |
| --- | --- |
| 0 | `GX2_SHADER_MODE_UNIFORM_REGISTER` |
| 1 | `GX2_SHADER_MODE_UNIFORM_BLOCK` |
| 2 | `GX2_SHADER_MODE_GEOMETRY_SHADER` |
| 3 | `GX2_SHADER_MODE_COMPUTE_SHADER` |

## GX2ShaderVarType
| Value | Description |
| --- | --- |
| 0 | `GX2_SHADER_VAR_TYPE_VOID` |
| 1 | `GX2_SHADER_VAR_TYPE_BOOL` |
| 2 | `GX2_SHADER_VAR_TYPE_INT` |
| 3 | `GX2_SHADER_VAR_TYPE_UINT` |
| 4 | `GX2_SHADER_VAR_TYPE_FLOAT` |
| 5 | `GX2_SHADER_VAR_TYPE_DOUBLE` |
| 6 | `GX2_SHADER_VAR_TYPE_DOUBLE2` |
| 7 | `GX2_SHADER_VAR_TYPE_DOUBLE3` |
| 8 | `GX2_SHADER_VAR_TYPE_DOUBLE4` |
| 9 | `GX2_SHADER_VAR_TYPE_FLOAT2` |
| 10 | `GX2_SHADER_VAR_TYPE_FLOAT3` |
| 11 | `GX2_SHADER_VAR_TYPE_FLOAT4` |
| 12 | `GX2_SHADER_VAR_TYPE_BOOL2` |
| 13 | `GX2_SHADER_VAR_TYPE_BOOL3` |
| 14 | `GX2_SHADER_VAR_TYPE_BOOL4` |
| 15 | `GX2_SHADER_VAR_TYPE_INT2` |
| 16 | `GX2_SHADER_VAR_TYPE_INT3` |
| 17 | `GX2_SHADER_VAR_TYPE_INT4` |
| 18 | `GX2_SHADER_VAR_TYPE_UINT2` |
| 19 | `GX2_SHADER_VAR_TYPE_UINT3` |
| 20 | `GX2_SHADER_VAR_TYPE_UINT4` |
| 21 | `GX2_SHADER_VAR_TYPE_FLOAT2X2` |
| 22 | `GX2_SHADER_VAR_TYPE_FLOAT2X3` |
| 23 | `GX2_SHADER_VAR_TYPE_FLOAT2X4` |
| 24 | `GX2_SHADER_VAR_TYPE_FLOAT3X2` |
| 25 | `GX2_SHADER_VAR_TYPE_FLOAT3X3` |
| 26 | `GX2_SHADER_VAR_TYPE_FLOAT3X4` |
| 27 | `GX2_SHADER_VAR_TYPE_FLOAT4X2` |
| 28 | `GX2_SHADER_VAR_TYPE_FLOAT4X3` |
| 29 | `GX2_SHADER_VAR_TYPE_FLOAT4X4` |
| 30 | `GX2_SHADER_VAR_TYPE_DOUBLE2X2` |
| 31 | `GX2_SHADER_VAR_TYPE_DOUBLE2X3` |
| 32 | `GX2_SHADER_VAR_TYPE_DOUBLE2X4` |
| 33 | `GX2_SHADER_VAR_TYPE_DOUBLE3X2` |
| 34 | `GX2_SHADER_VAR_TYPE_DOUBLE3X3` |
| 35 | `GX2_SHADER_VAR_TYPE_DOUBLE3X4` |
| 36 | `GX2_SHADER_VAR_TYPE_DOUBLE4X2` |
| 37 | `GX2_SHADER_VAR_TYPE_DOUBLE4X3` |
| 38 | `GX2_SHADER_VAR_TYPE_DOUBLE4X4` |

## GX2SamplerVarType
| Value | Description |
| --- | --- |
| 0 | `GX2_SAMPLER_VAR_TYPE_SAMPLER_1D` |
| 1 | `GX2_SAMPLER_VAR_TYPE_SAMPLER_2D` |
| 3 | `GX2_SAMPLER_VAR_TYPE_SAMPLER_3D` |
| 4 | `GX2_SAMPLER_VAR_TYPE_SAMPLER_CUBE` |

## GX2ResourceFlags
This is a bitfield.

| Mask | Description |
| --- | --- |
| `0x0` | `GX2R_RESOURCE_BIND_NONE` |
| `0x1` | `GX2R_RESOURCE_BIND_TEXTURE` |
| `0x2` | `GX2R_RESOURCE_BIND_COLOR_BUFFER` |
| `0x4` | `GX2R_RESOURCE_BIND_DEPTH_BUFFER` |
| `0x8` | `GX2R_RESOURCE_BIND_SCAN_BUFFER` |
| `0x10` | `GX2R_RESOURCE_BIND_VERTEX_BUFFER` |
| `0x20` | `GX2R_RESOURCE_BIND_INDEX_BUFFER` |
| `0x40` | `GX2R_RESOURCE_BIND_UNIFORM_BLOCK` |
| `0x80` | `GX2R_RESOURCE_BIND_SHADER_PROGRAM` |
| `0x100` | `GX2R_RESOURCE_BIND_STREAM_OUTPUT` |
| `0x200` | `GX2R_RESOURCE_BIND_DISPLAY_LIST` |
| `0x400` | `GX2R_RESOURCE_BIND_GS_RING_BUFFER` |
| `0x800` | `GX2R_RESOURCE_USAGE_CPU_READ` |
| `0x1000` | `GX2R_RESOURCE_USAGE_CPU_WRITE` |
| `0x2000` | `GX2R_RESOURCE_USAGE_GPU_READ` |
| `0x4000` | `GX2R_RESOURCE_USAGE_GPU_WRITE` |
| `0x8000` | `GX2R_RESOURCE_USAGE_DMA_READ` |
| `0x10000` | `GX2R_RESOURCE_USAGE_DMA_WRITE` |
| `0x20000` | `GX2R_RESOURCE_USAGE_FORCE_MEM1` |
| `0x40000` | `GX2R_RESOURCE_USAGE_FORCE_MEM2` |
| `0x100000` | `GX2R_RESOURCE_DISABLE_CPU_INVALIDATE` |
| `0x200000` | `GX2R_RESOURCE_DISABLE_GPU_INVALIDATE` |
| `0x400000` | `GX2R_RESOURCE_LOCKED_READ_ONLY` |
| `0x20000000` | `GX2R_RESOURCE_GX2R_ALLOCATED` |
| `0x40000000` | `GX2R_RESOURCE_LOCKED` |
