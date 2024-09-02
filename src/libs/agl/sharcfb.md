## [AGL](/formats.md#agl) > Binary Shader Archive (SHARCFB)

A SHARCFB file contains compiled shaders. This page describes version 8 of the file format.

| File structure |
| --- |
| [Header](#header) |
| [Shader binary section](#shader-binary-section) |
| [Shader program section](#shader-program-section) |

## Header
In little endian mode, the whole header is swapped (even the magic number).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `SHAB` |
| 0x4 | 4 | Version number |
| 0x8 | 4 | Filesize |
| 0xC | 4 | Endianness (0=big, 1=little) |
| 0x10 | 4 | Always 0 |
| 0x14 | 4 | Length of filename string (including null terminator) |
| 0x18 | | Filename string (null-terminated) |

## Shader Binary Section
This section contains the compiled shader binaries.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of shader binary section |
| 0x4 | 4 | Number of shader binaries |
| 0x8 | | Shader binaries |

### Shader Binary
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (or offset to next shader binary) |
| 0x4 | 4 | Type:<br>0 = GX2VertexShader<br>1 = GX2PixelShader<br>2 = GX2GeometryShader |
| 0x8 | 4 | Offset to shader data |
| 0xC | 4 | Size of shader data |
| 0x10 | | Shader data. This uses the same format as the GX2 structures, but pointers are stored as offsets relative to the start of the shader data. |

## Shader Program Section
This section contains named shader programs that reference shaders from the shader binary section.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of shader program section |
| 0x4 | 4 | Number of shader programs |
| 0x8 | | Shader programs |

### Shader Program
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (or offset to next shader program) |
| 0x4 | 4 | Length of name string (including null terminator) |
| 0x8 | 4 | A bitfield defining the kind of shaders in this program:<br>`0x1`: Vertex shader<br>`0x2`: Pixel shader<br>`0x4`: Geometry shader<br><br>A shader program must contain a vertex and a pixel shader and may optionally contain a geometry shader. |
| 0xC | 4 | Index of first shader binary (`base_index`) |
| 0x10 | | Null-terminated name string |
| | | Shader variation section (possible values) |
| | | Shader variation section (symbols / default values) |
| | | Shader symbol section (uniform vars) |
| | | Shader symbol section (uniform blocks) |
| | | Shader symbol section (sampler vars) |
| | | Shader symbol section (attrib vars) |

### Shader Variation Section
A single shader program may have different variations. Variations are defined by a set of macros, each of which can be set to a predefined set of values. Every possible combination of macro values has its own shader binaries, so the number of shader binaries in a program grows exponentially with its number of variation macros. This is why some sharcfb files are much bigger than others.

Each shader program has two shader variation sections. The first one defines the list of possible values for each shader macro. The second section only has one value per macro: its default value.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of this section |
| 0x4 | 4 | Number of variation macros |
| 0x8 | | Variations macros |

The following algorithm can be used to find the shader binary index of a specific variation:
```python
def get_variation_index(base_index, shader_program, settings):
    index = 0
    for macro in shader_program.variation_macros:
        index *= len(macro.possible_values)
        index += macro.possible_values.index(settings[macro.name])
    
    if shader_program.has_geometry_shader:
        return base_index + index * 3
    return base_index + index * 2
```
Now load the vertex shader from `variation_index`, the pixel shader from `variation_index + 1` and the geometry shader from `variation_index + 2` (if it exists).

#### Variation Macro
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (or offset to next variation macro) |
| 0x4 | 4 | Length of macro name |
| 0x8 | 4 | Number of values |
| 0xC | 4 | Length of symbol name |
| 0x10 | | Variation macro name (null-terminated) |
| | | List of values. These are null-terminated strings stored directly after each other (without padding) |
| | | Symbol name (null-terminated) |

### Shader Symbol Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of this section |
| 0x4 | 4 | Number of shader symbols |
| 0x8 | | Shader symbols |

#### Shader Symbol
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (or offset to next shader symbol) |
| 0x4 | 4 | Shader variable size |
| 0x8 | 4 | Length of variable name |
| 0xC | 4 | Length of symbol name |
| 0x10 | 4 | Size of default value |
| 0x14 | 4 | Number of shader variations |
| 0x18 | | Variable name (null-terminated) |
| | | Symbol name (null-terminated) |
| | | Default value |
| | | For each shader variation, a bool (one byte) indicating whether this variable is used by that variation |