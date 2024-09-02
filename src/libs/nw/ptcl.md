## [NW](/formats.md#nw) > Particle File

This file contains resources for particle effects. This page describes version 0x41 of the file format.

The file is structured as follows:

* [File header and effects](#file-header)
* [Texture section](#texture-section)
* [String table](#string-table)
* [Shader section](#shader-section)
* [Keyframe animation section](#keyframe-animation-section)
* [Primitive section](#primitive-section)
* Parameter section

## File Header
The offsets are absolute.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`EFTF`) |
| 0x4 | 4 | Version number |
| 0x8 | 4 | Number of effects |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Offset to [string table](#string-table) |
| 0x14 | 4 | [Texture section](#texture-section) offset |
| 0x18 | 4 | [Texture section](#texture-section) size |
| 0x1C | 4 | [Shader section](#shader-section) offset |
| 0x20 | 4 | [Shader section](#shader-section) size |
| 0x24 | 4 | [Keyframe animation section](#keyframe-animation-section) offset |
| 0x28 | 4 | [Keyframe animation section](#keyframe-animation-section) size |
| 0x2C | 4 | [Primitive section](#primitive-section) offset |
| 0x30 | 4 | [Primitive section](#primitive-section) size |
| 0x34 | 4 | Parameter section offset |
| 0x38 | 4 | Parameter section size |
| 0x3C | 4 | Unknown |
| 0x40 | 4 | Unknown |
| 0x44 | 4 | Unknown |
| 0x48 | | [Effects](#effect) |

### Effect
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Name offset (into string table) |
| 0xC | 4 | Name address (filled in at runtime) |
| 0x10 | 4 | Emitter count |
| 0x14 | 4 | Emitter offset (absolute) |
| 0x18 | 4 | Unknown |

### Emitter
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset to [emitter data](#emitter-data) (absolute) |
| 0x4 | 4 | Pointer to emitter data (filled in at runtime) |
| 0x8 | 4 | Pointer to static uniform block 1 (filled in at runtime) |
| 0xC | 4 | Pointer to static uniform block 2 (filled in at runtime) |

#### Emitter Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Type (0=Simple, 1=Complex) |
| 0x4 | 4 | Flags:<br>0x0000400 - Reverse particle order<br>0x0010000 - Emission rate is limited (can't be sped up) |
| 0x8 | 0x2C | Unknown |
| 0x34 | 4 | Custom action callback id |
| 0x38 | 4 | Name offset (into string table) |
| 0x3C | 4 | Name address (filled in at runtime) |
| 0x40 | 0xD8 | [Texture res 1](#texture-res) |
| 0x118 | 0xD8 | [Texture res 2](#texture-res) |
| 0x1F0 | 0xD8 | [Texture res 3](#texture-res) |
| 0x2C8 | 4 | Pointer to [keyframe animations](#keyframe-animation-section) (filled in at runtime) |
| 0x2CC | 4 | Offset into [keyframe animation section](#keyframe-animation-section) |
| 0x2D0 | 4 | Size of [keyframe animation](#keyframe-animation-section) data |
| 0x2D4 | 8 | Unknown |
| 0x2DC | 4 | Primitive index |
| 0x2E0 | 8 | Unknown |
| 0x2E8 | 4 | Primitive index 2 |
| 0x2EC | 4 | Number of parameters |
| 0x2F0 | 4 | Offset into parameter section |
| 0x2F4 | 4 | Pointer into parameter section (filled in at runtime) |
| 0x2F8 | 0x28 | Unknown |
| 0x320 | 4 | Display side type |
| 0x324 | 4 | Blend type |
| 0x328 | 4 | ZBuf A test type |
| 0x32C | 4 | [Animation function](#animation-functions) scale |
| 0x330 | 4 | [Animation function](#animation-functions) color 0 |
| 0x334 | 4 | [Animation function](#animation-functions) color 1|
| 0x338 | 4 | [Animation function](#animation-functions) alpha 0 |
| 0x33C | 4 | [Animation function](#animation-functions) alpha 1 |
| 0x340 | 4 | [Emit function type](#emit-functions) |
| 0x344 | 0x100 | Unknown |
| 0x444 | 4 | Base emission ratio (float) |
| 0x448 | 4 | Emission ratio randomness |
| 0x44C | 0x10 | Unknown |
| 0x45C | 4 | Initial particle speed |
| 0x460 | 0x24 | Unknown |
| 0x484 | 4 | Speed acceleration (float) |
| 0x488 | 0x1C | Unknown |
| 0x4A4 | 4 | X acceleration (float) |
| 0x4A8 | 4 | Y acceleration (float) |
| 0x4AC | 4 | Z acceleration (float) |
| 0x4B0 | 8 | Unknown |
| 0x4B8 | 4 | Mesh type (0=Square, 1=[Primitive](#primitive-section)) |
| 0x4BC | 4 | Unknown |
| 0x4C0 | 4 | Base speed randomness (float) |
| 0x4C4 | 0x10 | Unknown |
| 0x4D4 | 0x7C | [Texture emitter data 1](#texture-emitter-data) |
| 0x550 | 0x7C | [Texture emitter data 2](#texture-emitter-data) |
| 0x5CC | 0x7C | [Texture emitter data 3](#texture-emitter-data) |
| 0x648 | 8 | Unknown |
| 0x650 | 8 x 16 | Color table 0 |
| 0x6D0 | 8 x 16 | Color table 1 |
| 0x750 | 0x34 | Unknown |
| 0x784 | 0x14 | [3v4k animation key](#animation-key) alpha 0 |
| 0x798 | 0x14 | [3v4k animation key](#animation-key) alpha 1 |
| 0x7AC | 0x7C | Unknown |
| 0x828 | 4 | Rotation acceleration (float) |
| 0x82C | 5 | Unknown |
| 0x831 | 1 | Custom shader callback id |
| 0x832 | 0x12 | Unknown |
| 0x844 | 4 | Shader index 1 |
| 0x848 | 4 | Shader index 2 |
| 0x84C | 4 | Shader index 3 |
| 0x850 | 0x6C | Unknown |

Only present if type is complex:

| Offset | Size | Description |
| --- | --- | --- |
| 0x8BC | ? | Unknown |

#### Animation Functions
| ID | Function |
| --- | --- |
| 0 | None |
| 1 | 4k3v |
| 2 | 8key |

#### Emit Functions
| ID | Function |
| --- | --- |
| 0 | Point |
| 1 | Circle |
| 2 | Circle same divide |
| 3 | Fill circle |
| 4 | Sphere |
| 5 | Sphere same divide |
| 6 | Sphere same divide 64 |
| 7 | Fill sphere |
| 8 | Cylinder |
| 9 | Fill cylinder |
| 10 | Box |
| 11 | Fill box |
| 12 | Line |
| 13 | Line same divide |
| 14 | Rectangle |
| 15 | Primitive |

#### Animation Key
This animation uses four keys and three values (3v4k).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | First key value |
| 0x4 | 4 | Difference between first and second key value |
| 0x8 | 4 | Difference between second and last key value |
| 0xC | 4 | Time of second key value |
| 0x10 | 4 | Time of third key value |

The animation is constructed as follows:

```
float value1 = StartValue;
float value2 = StartValue + StartDifference;
float value3 = value2 + EndDifference;

KeyFrame(0, value1)
KeyFrame(Time2, value2)
KeyFrame(Time3, value2)
KeyFrame(1, value3 )
```

#### Texture Res
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Width |
| 0x2 | 2 | Height |
| 0x4 | 4 | Tile mode |
| 0x8 | 4 | Swizzle |
| 0xC | 1 | Wrap mode |
| 0xD | 1 | Filter mode |
| 0xE | 1 | Depth |
| 0xF | 1 | Padding |
| 0x10 | 4 | Mipmap count |
| 0x14 | 4 | Components selector |
| 0x18 | 4 | LOD max (float) |
| 0x1C | 4 | LOD bias (float) |
| 0x20 | 4 | Original [texture format](#texture-format) |
| 0x24 | 4 | Offset into [texture section](#texture-section) for original texture data |
| 0x28 | 4 | Size of original texture data |
| 0x2C | 4 | FTX [texture format](#texture-format) |
| 0x30 | 4 | Size of FTX texture data |
| 0x34 | 4 | Offset into [texture section](#texture-section) for FTX texture data |
| 0x38 | 4 | Is GX2Texture initialized (must be 0, updated at runtime) |
| 0x3C | 0x9C | GX2Texture structure |

#### Texture Format
| ID | Description |
| --- | --- |
| 1 | RGBA8 UNORM |
| 2 | RGB8 UNORM |
| 3 | BC1 UNORM |
| 4 | BC1 SRGB |
| 5 | BC2 UNORM |
| 6 | BC2 SRGB |
| 7 | BC3 UNORM |
| 8 | BC3 SRGB |
| 9 | BC4 UNORM |
| 10 | BC4 SNORM |
| 11 | BC5 UNORM |
| 12 | BC5 SNORM|
| 13 | R8 UNORM |
| 14 | RG8 UNORM |
| 15 | RGBA8 SRGB |
| 16 | R8 SNORM |
| 17 | RG4 UNORM |
| 18 | RG11B10 FLOAT |
| 19 | R16 FLOAT |
| 20 | RG16 FLOAT |
| 21 | RGBA16 FLOAT |
| 22 | R32 FLOAT |
| 23 | RG32 FLOAT |
| 24 | RGBA32 FLOAT |
| 25 | R5G6B5 UNORM |
| 26 | RGB5A1 UNORM |

#### Texture Emitter Data
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x7C | Unknown |

## Texture Section
This section contains raw image data that may be referenced by [emitters](#emitter-data).

## String Table
The string table simply contains a bunch of null-terminated strings. The first string in the string table is the name of the particle set.

## Shader Section
The offsets are relative to the start of the shader section.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of shaders |
| 0x4 | 4 | Shader section size |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Offset to [shader files](#shader-files) |
| 0x14 | 4 | Offset to [shader info](#shader-info) list |

### Shader Files
This section simply contains a bunch of [GSH files](Gfx2-File-Format).

### Shader Info
One per shader. The shader file offset is relative to the first shader file.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x28 | [Shader resource info](#shader-resource-info) |
| 0x28 | 0x3C | [Texture sampler info](#texture-sampler-info) |
| 0x64 | 4 | Unknown |
| 0x68 | 4 | Shader file size |
| 0x6C | 4 | Shader file offset |
| 0x70 | 4 | Unknown |
| 0x74 | 4 | Unknown |

#### Shader Resource Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Flags:<br>0x02000000 - Use GPU calc for emitter |
| 0x8 | 32 | Unknown |

#### Texture sampler info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Unknown |
| 0x1 | 1 | Maximum texture sampler id (0, 1 or 2) |
| 0x2 | 17 | Unknown |
| 0x13 | 1 | Is texture sampler 0 an array |
| 0x14 | 1 | Is texture sampler 1 an array |
| 0x15 | 0x27 | Unknown |

## Keyframe Animation Section
This section contains keyframe animations that may be used by [emitters](#emitter-data). It contains zero or more copies of the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier (`KEYA`) |
| 0x4 | 4 | Number of animations |
| 0x8 | | [Animations](#keyframe-animation) |

### Keyframe Animation
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of [keyframes](#keyframe) |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | [Animated attribute](#attribute) |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Number of frames |
| 0x14 | 4 | Unknown |
| 0x18 | 4 | Size of this structure |
| 0x1C | | [Keyframes](#keyframe) |

#### Keyframe
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Frame (float) |
| 0x4 | 4 | Value (float) |

#### Attribute
| ID | Description |
| --- | -- |
| 0 | Emission ratio |
| 1 | Random |
| 2 | Matrix scale X |
| 3 | Matrix scale Y |
| 4 | Matrix scale Z |
| 5 | Rotation X |
| 6 | Rotation Y |
| 7 | Rotation Z |
| 8 | Position X |
| 9 | Position Y |
| 10 | Position Z |
| 15 | Particle speed |
| 17 | Scale X |
| 18 | Scale Y |
| 25 | Particle acceleration |

| ID | Description |
| --- | --- |
| 28 | Random X |
| 29 | Random Y |
| 30 | Random Z |
| 31 | Magnet |
| 32 | Spin 1 |
| 33 | Spin 2 |
| 34 | Convergence |
| 35 | Position X |
| 36 | Position Y |
| 37 | Position Z |
| 38 | Color 0 Red |
| 39 | Color 0 Green |
| 40 | Color 0 Blue |
| 41 | Color 1 Red |
| 42 | Color 1 Green |
| 43 | Color 1 Blue |
| 44 | Alpha 0 |
| 45 | Alpha 1 |
| 46 | Scale X |
| 47 | Scale Y |

## Primitive Section
The offset is relative to the start of the primitive section.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of primitives |
| 0x4 | 4 | Size of primitive section |
| 0x8 | 4 | Offset to primitives (0xC) |
| 0xC | | [Primitives](#primitive) |
| | | Vertex buffers |

### Primitive
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 5 x 16 | [Buffer info](#buffer-info) |

| Index | Name | Type |
| --- | --- | --- |
| 0 | v_inPos | Vec3 |
| 1 | v_inNormal | Vec3 |
| 2 | v_inColor | Vec4 |
| 3 | v_inTexCoord | Vec4 |
| 4 | v_inIndex | Uint32 |

#### Buffer Info
Offset is relative to start of vertex buffers in [primitive section](#primitive-section).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of elements |
| 0x4 | 4 | Stride (number of elements) |
| 0x8 | 4 | Buffer offset |
| 0xC | 4 | Buffer size |