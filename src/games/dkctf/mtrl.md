## [DKC:TF](/formats.md#dkctf) > Material File (MTRL)

Meta data: [NMaterialFormat::SMetaData](#nmaterialformatsmetadata)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

The data in this form is zlib compressed.

| Type | Description |
| --- | --- |
| [CChunkDescriptor] | EXPT chunk ([NMaterialFormat::SMaterialIdentifier](#nmaterialformatsmaterialidentifier)) |
| [CFormDescriptor] | [MTRL form](#mtrl-form) |

## NMaterialFormat::SMaterialIdentifier
| Type | Description |
| --- | --- |
| [CFourCC] | [Material type](enums.md#material-type) |
| [List]&lt;[NMaterialFormat::CMaterialPermutation](#nmaterialformatcmaterialpermutation)&gt; | Permutation list |

### NMaterialFormat::CMaterialPermutation
| Type | Description |
| --- | --- |
| Uint32 | Shader id |
| Uint32 | Permutation id |

## MTRL Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | SGX2 chunk |

### SGX2 Chunk
| Type | Description |
| --- | --- |
| Uint32 | Flags<br>`0x1`: toc present |
| Uint32 | Size of toc. *Only present if `flags & 1`.* |
| [NMaterialArchive::SMaterialArchiveTOC](#nmaterialarchivesmaterialarchivetoc) | Material archive toc. *Only present if `flags & 1`.* |
| [List]&lt;[CShaderPart](#cshaderpart)&gt; | Shader parts |
| [List]&lt;[NMaterialArchive::SMaterialImportDesc](#nmaterialarchivesmaterialimportdesc)&gt; | Material import descs |

### NMaterialArchive::SMaterialArchiveTOC
| Type | Description |
| --- | --- |
| [List]&lt;NMaterialArchive::SShaderSourceTOCEntry&gt; | Shader source toc entries |
| [List]&lt;NMaterialArchive::SMaterialTOCEntry&gt; | Material toc entries |

### CShaderPart
A shader part contains a Gfx2 shader. Shader parts are referenced by the [shader import descs](#nmaterialarchivesmaterialimportdesc).

| Type | Description |
| --- | --- |
| Bool | State |
| [CString] | Name |
| Uint32 | Data size |
| | Data |

### NMaterialArchive::SMaterialImportDesc
| Type | Description |
| --- | --- |
| [CFourCC] | [Material type](enums.md#material-type) |
| Uint16 | Unknown (always 1) |
| [List]&lt;[NMaterialArchive::SShaderImportDesc](#nmaterialarchivesshaderimportdesc)&gt; | Shader import descs |

### NMaterialArchive::SShaderImportDesc
| Type | Description |
| --- | --- |
| Uint64 | Shader id |
| Uint32 | Shader part index for vertex shader |
| Uint32 | Shader part index for fragment shader |
| Uint32 | Shader part index for geometry shader |
| Uint32 | Unknown (always 0) |
| [CShaderDefines](#cshaderdefines) | Shader defines |
| [List]&lt;Uint8&gt; | [Additional data](#additional-shader-data) |

#### CShaderDefines
| Type | Description |
| --- | --- |
| [List]&lt;[CString]&gt; | Strings |
| Uint32 | Total length of shader define strings |

#### Additional Shader Data
| Type | Description |
| --- | --- |
| [NShaderCore::SAdditionalDataHeader](#nshadercoresadditionaldataheader) | Header |
| ... | Data buffer |

#### NShaderCore::SAdditionalDataHeader
The first 6 offsets in the table below are relative to the start of the data buffer behind this header. The remaining offsets are relative to the start of the constant buffer.

| Type | Description |
| --- | --- |
| Uint32 | Offset to string table |
| Uint32 | Size of string table |
| Uint32 | Offset to [serialized uniform table](#nshadercoresserializeduniform) |
| Uint32 | Number of [serialized uniforms](#nshadercoresserializeduniform) |
| Uint32 | Offset of [uniform block data table](#cshaderuniformblockdata) |
| Uint32 | Number of [uniform block data entries](#cshaderuniformblockdata) |
| Uint32 | Offset to [shader vertex layout entries](#sshadervertexlayoutentry) |
| Uint32 | Number of [shader vertex layout entries](#sshadervertexlayoutentry) |
| Uint32 | Offset to bitmask (uint32) indicating [which matrices](#ecachedgraphicstransform) are used by this shader |
| Uint32 | Always 1 |
| Uint32 | Offset to constant buffer |
| Uint32 | Size of constant buffer |
| Uint32 | Offset to [constant buffer refs](#nshadercoresconstantbufferref) for vertex shader |
| Uint32 | Number of [constant buffer refs](#nshadercoresconstantbufferref) for vertex shader |
| Uint32 | Offset to [constant buffer refs](#nshadercoresconstantbufferref) for pixel shader |
| Uint32 | Number of [constant buffer refs](#nshadercoresconstantbufferref) for pixel shader |
| Uint32 | Offset to [constant buffer refs](#nshadercoresconstantbufferref) for geometry shader |
| Uint32 | Number of [constant buffer refs](#nshadercoresconstantbufferref) for geometry shader |
| Uint32 | Offset to [serialized shader bindings](#nshadercoresserializedshaderbinding) |
| Uint32 | Number of [serialized shader bindings](#nshadercoresserializedshaderbinding) |

#### NShaderCore::SSerializedUniform
| Type | Description |
| --- | --- |
| Uint32 | Offset into string table |
| Uint32 | Uniform block data index |
| Uint32 | Offset into uniform block data divided by 4 |

#### CShaderUniformBlockData
| Type | Description |
| --- | --- |
| Uint32 | Size |
| Uint32 | Flags:<br>`0x1`: This block uses the global transform cache |

#### SShaderVertexLayoutEntry
| Type | Description |
| --- | --- |
| Uint32 | [Vertex component](enums.md#vertex-component) |
| Uint32 | Unknown |

#### ECachedGraphicsTransform
| Value | Name |
| --- | --- |
| 0 | uc_modelToWorldMatrix |
| 1 | uc_worldToModelMatrix |
| 2 | uc_worldToViewMatrix |
| 3 | uc_projectionMatrix |
| 4 | uc_modelViewMatrix |
| 5 | uc_modelViewProjectionMatrix |
| 6 | uc_projectionInverseMatrix |
| 7 | uc_normalMatrix |
| 8 | uc_customMatrix0 |

#### NShaderCore::SConstantBufferRef
| Type | Description |
| --- | --- |
| Uint32 | Uniform block location |
| Uint32 | Uniform block index |

#### NShaderCore::SSerializedShaderBinding
| Type | Description |
| --- | --- |
| Uint32 | Offset into string table |
| Uint32 | Unknown |
| Uint32 | Unknown |

## NMaterialFormat::SMetaData
| Type | Description |
| --- | --- |
| Uint32 | Unknown (always 1) |
| Uint32 | Version (always 12) |
| Uint32 | Compressed data size |
| Uint32 | Decompressed data size |
| Uint32 | Offset to compressed data in material file |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CFourCC]: types.md#cfourcc
[List]: types.md#list
[CString]: types.md#cstring