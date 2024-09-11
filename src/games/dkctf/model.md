## [DKC:TF](../../formats.md#dkctf) > Model File (CMDL/SMDL/WMDL)

Meta data: [NModelFormat::SMetaData](#nmodelformatsmetadata)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor (CMDL/SMDL/WMDL) |

## CMDL Form
| Type | Description |
| --- | --- |
| [Model Chunks](#model-chunks) | Model data |

## SMDL Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | SKHD chunk ([NModelFormat::SSkinnedModelHeader](#nmodelformatsskinnedmodelheader)) |
| [Model Chunks](#model-chunks) | Model data |

### NModelFormat::SSkinnedModelHeader
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## WMDL Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | WDHD chunk ([NModelFormat::SWorldModelHeader](#nmodelformatsworldmodelheader)) |
| [Model Chunks](#model-chunks) | Model data |

### NModelFormat::SWorldModelHeader
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| [CRenderOctree](#crenderoctree) | Render octree |
| [List]&lt;[CAABox]&gt; | AA box list |
| [List]&lt;Float&gt; | Unknown |

### CRenderOctree
| Type | Description |
| --- | --- |
| [CFourCC] | Type |
| Uint32 | Unknown |
| Uint32 | field_0 |
| Uint32 | field_4 |
| Uint32 | field_8 |
| [CAABox] | field_C |
| [List]&lt;Uint32&gt; | field_28 |
| [List]&lt;Uint32&gt; | field_34 |
| [List]&lt;Uint8&gt; | field_40 |
| [List]&lt;[CAABox]&gt; | field_4C |

## Model Chunks
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | HEAD chunk ([NModelFormat::SModelHeader](#nmodelformatsmodelheader)) |
| [CChunkDescriptor] | MTRL chunk ([List]&lt;[CMaterialCache::SData](#cmaterialcachesdata)) |
| [CChunkDescriptor] | MESH chunk ([List]&lt;[CRenderMesh](#crendermesh)&gt;) |
| [CChunkDescriptor] | VBUF chunk ([List]&lt;[CGraphicsVertexBufferToken](#cgraphicsvertexbuffertoken)&gt;) |
| [CChunkDescriptor] | IBUF chunk ([List]&lt;[CGraphicsIndexBufferToken](#cgraphicsindexbuffertoken)&gt;) |
| [CChunkDescriptor] | GPU chunk. This chunk contains the actual vertex and index buffers. |

### NModelFormat::SModelHeader
| Type | Description |
| --- | --- |
| Uint32 | Number of opaque meshes |
| Uint32 | Number of 1-pass trans meshes |
| Uint32 | Number of 2-pass trans meshes |
| Uint32 | Number of 1-bit meshes |
| Uint32 | Number of additive meshes |
| [CAABox] | AA box |
| [List]&lt;[CModelDataSource](#cmodeldatasource)&gt; | Data sources |

#### CModelDataSource
| Type | Description |
| --- | --- |
| Uint32 | Type |
| | Object |

| ID | Type |
| --- | --- |
| 0 | [CModelAnimUvDataSource](#cmodelanimuvdatasource) |
| 1 | CWindModelDataSource |
| 2 | CCausticModelDataSource |
| 3 | CFurModelDataSource |

#### CModelAnimUvDataSource
| Type | Description |
| --- | --- |
| [CEvalSystem](#cevalsystem) | Eval system |
| [List]&lt;[CEvalId](#cevalid)&gt; | Eval ids |
| [List]&lt;[CVector4i]&gt; | field_1C |
| [List]&lt;Uint8&gt; | field_28 |

#### CEvalSystem
| Type | Description |
| --- | --- |
| [CEvalDataContext](#cevaldatacontext) | Eval data context |
| Uint32 | Update function |
| Uint32 | SetTime function |
| Uint32 | SetPhase function |

#### CEvalDataContext
| Type | Description |
| --- | --- |
| Uint32 | Number of input values |
| Uint32 | Number of data handles |
| Uint32[] | Input values |
| [CEvalDataHandle](#cevaldatahandle)[] | Data handles |

#### CEvalDataHandle
| Type | Description |
| --- | --- |
| [List]&lt;Uint8&gt; | Data |

#### CEvalId
| Type | Description |
| --- | --- |
| Uint32 | Id |

### CMaterialCache::SData
| Type | Description |
| --- | --- |
| [CString] | Name |
| [CObjectId] | Material file id |
| [CFourCC] | [Material type](enums.md#material-type) |
| Uint32 | Material flags |
| [List]&lt;[CMaterialData](#cmaterialdata)&gt; | Data list |

#### CMaterialData
| Type | Description |
| --- | --- |
| [CFourCC] | [Data id](#ematerialdataid) |
| Uint32 | Type |
| | Data |

| ID | Type |
| --- | --- |
| 0 | [CMaterialTextureTokenData](#cmaterialtexturetokendata) |
| 1 | [CMaterialColorData](#cmaterialcolordata) |
| 2 | [CMaterialScalarData](#cmaterialscalardata) |
| 4 | [CLayeredTextureData](#clayeredtexturedata) |
| 5 | [CMaterialInt4Data](#cmaterialint4data) |

#### EMaterialDataId
| FourCC | ID | Type | Uniform name |
| --- | --- | --- | --- |
| `GBUF` | 0 | Texture | |
| `DIFT` | 1 | Texture | uc_diffuseMap<br>uc_diffuseMapTexCoordIndex |
| `ICAN` | 2 | Texture | uc_incanMap<br>uc_incanMapTexCoordIndex |
| `NMAP` | 3 | Texture | uc_normalMap<br>uc_normalMapTexCoordIndex |
| `REFL` | 4 | Texture | uc_reflectionCubeMap |
| `REFS` | 5 | Texture | uc_reflectionSphereMap |
| `REFV` | 6 | Texture | uc_reflectivityMap<br>uc_reflectivityMapTexCoordIndex |
| `SHRT` | 7 | Texture | |
| `SPCT` | 8 | Texture | uc_specularMap<br>uc_specularMapTexCoordIndex |
| `LIBD` | 9 | Texture | uc_lightBufferDiffuse |
| `LIBS` | 10 | Texture | uc_lightBufferSpecular |
| `BLND` | 11 | Texture | uc_vertexBlenderMask<br>uc_vertexBlenderMaskTexCoordIndex |
| `FOGR` | 12 | Texture | uc_fogDepthDensityRamp |
| `INDI` | 13 | Texture | uc_diffuseIndirectionMap<br>uc_diffuseIndirectionMapTexCoordIndex |
| `SPCF` | 14 | Texture | uc_specularFalloffMap |
| `FURT` | 15 | Texture | uc_furMap |
| `FURL` | 16 | Texture | uc_furLengthMap |
| `FURF` | 17 | Texture | uc_furFlowMap |
| `ALPH` | 18 | Color | uc_alphaTestParams |
| `DIFC` | 19 | Color | uc_diffuseColor |
| `SHRC` | 20 | Color | uc_directionalIrradianceMapAmbientColor |
| `SPCC` | 21 | Color | uc_specularColor |
| `ANFP` | 22 | Color | |
| `ICNC` | 23 | Color | uc_incanColor |
| `ICMC` | 24 | Color | uc_incanUnmaskedColor |
| `CHC0` | 25 | Int | |
| `CHC1` | 26 | Int | |
| `CHC2` | 27 | Int | |
| `AUVI` | 28 | Int4 | uc_animatedUVIndices |
| `ALPH` | 29 | Scalar | uc_fogInvRange |
| `SPCP` | 30 | Scalar | uc_specularPower |
| `INDS` | 31 | Scalar | uc_diffuseIndirectionScale |
| `LCNT` | 32 | Scalar | |
| `RFMN` | 33 | Scalar | uc_rimFresnelMin |
| `RFMX` | 34 | Scalar | uc_rimFresnelMax |
| `RBRT` | 35 | Scalar | |
| `NMHT` | 36 | Scalar | |
| `FRDN` | 37 | Scalar | uc_furDensity |
| `FRTH` | 38 | Scalar | |
| `FROC` | 39 | Scalar | |
| `FROS` | 40 | Scalar | uc_furOcclusionStartLength |
| `FRFS` | 41 | Scalar | uc_furFlowStrength |
| `DRAG` | 42 | Scalar | uc_drag |
| `SCOF` | 43 | Scalar | uc_stiffnessCoefficient |
| `CONH` | 44 | Scalar | uc_constraintHeight |
| `CONE` | 45 | Scalar | uc_constraintEllipseRatioSqr |
| `FRBP` | 46 | Scalar | uc_furBendPower |
| `SHDD` | 47 | CSimpleShadowMaterialData<br>CProjectedSimpleShaderMaterialData | |
| `SKIN` | 48 | CSkinningMaterialData | |
| `DIMD` | 49 | NBakedLighting::CDIMMaterialData | |
| `PDTA` | 50 | CParticleMaterialData | |
| `LIT ` | 51 | CLightMaterialData | |
| `AUXF` | 52 | CAnimatedUVMaterialData | |
| `WIND` | 53 | CWindAnimMaterialData | |
| `WATR` | 54 | CWaterMaterialData | |
| `DFXS` | 55 | CDepthFxSceneMaterialData | |
| `DFXN` | 56 | CDepthFXNodeMaterialData | |
| `CAUS` | 57 | CCausticMaterialData | |
| `FURC` | 58 | CFurMaterialData | |
| `INST` | 59 | CInstanceMaterialData | |
| `DIFL` | 60 | CLayeredTextureData | uc_diffuseMap |
| `SPCL` | 61 | CLayeredTextureData | uc_specularMap |
| `ICNL` | 62 | CLayeredTextureData | |
| `NRML` | 63 | CLayeredTextureData | uc_normalMap |

#### CMaterialTextureTokenData
| Type | Description |
| --- | --- |
| [CObjectId] | File id |
| [STextureUsageInfo](#stextureusageinfo) | Usage info |

#### CLayeredTextureData
| Type | Description |
| --- | --- |
| Uint32 | field_C |
| [CColor4f] | field_10 |
| [CColor4f] | field_20 |
| [CColor4f] | field_30 |
| Uint8 | Flags |
| [CObjectId] | Texture 1 |
| [STextureUsageInfo](#stextureusageinfo) | Usage info 1. *Only present if the `CObjectId` of this texture is nonzero.* |
| [CObjectId] | Texture 2 |
| [STextureUsageInfo](#stextureusageinfo) | Usage info 2. *Only present if the `CObjectId` of this texture is nonzero.* |
| [CObjectId] | Texture 3 |
| [STextureUsageInfo](#stextureusageinfo) | Usage info 3. *Only present if the `CObjectId` of this texture is nonzero.* |

#### STextureUsageInfo
| Type | Description |
| --- | --- |
| Uint32 | Flags |
| Uint32 | [Texture filter](enums.md#texture-filter) |
| Uint32 | [Texture wrap (x)](enums.md#texture-wrap) |
| Uint32 | [Texture wrap (y)](enums.md#texture-wrap)|
| Uint32 | [Texture wrap (z)](enums.md#texture-wrap)|

#### CMaterialColorData
| Type | Description |
| --- | --- |
| [CColor4f] | Value |

#### CMaterialScalarData
| Type | Description |
| --- | --- |
| Float | Value |

#### CMaterialInt4Data
| Type | Description |
| --- | --- |
| [CVector4i] | Value |

### CRenderMesh
| Type | Description |
| --- | --- |
| Uint32 | [Primitive mode](#primitive-mode) |
| Uint16 | Material cache index |
| Uint8 | Vertex buffer index |
| Uint8 | Index buffer index |
| Uint32 | Index buffer offset |
| Uint32 | Count |
| Uint16 | field_10 |
| Uint8 | field_12 |
| Uint8 | field_13 |
| Uint8 | Flags |

#### Primitive Mode
| EPrimitive | GX2PrimitiveMode |
| --- | --- |
| 0 | GX2_PRIMITIVE_MODE_POINTS |
| 1 | GX2_PRIMITIVE_MODE_LINES |
| 2 | GX2_PRIMITIVE_MODE_LINE_STRIP |
| 3 | GX2_PRIMITIVE_MODE_TRIANGLES |
| 4 | GX2_PRIMITIVE_MODE_TRIANGLE_STRIP |
| 5 | 10 |
| 6 | 11 |
| 7 | 12 |
| 8 | 13 |

### CGraphicsVertexBufferToken
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [List]&lt;[SVertexDataComponent](#svertexdatacomponent)&gt; | Components |

#### SVertexDataComponent
| Type | Description |
| --- | --- |
| Uint32 | field_0 |
| Uint32 | Offset |
| Uint32 | Stride |
| Uint32 | [Format](#attribute-format) |
| Uint32 | [Type](enums.md#vertex-component) |

#### Attribute Format
| Value | GX2AttribFormat |
| --- | --- |
| 0 | GX2_ATTRIB_FORMAT_UNORM_8 |
| 1 | GX2_ATTRIB_FORMAT_UINT_8 |
| 2 | GX2_ATTRIB_FORMAT_SNORM_8 |
| 3 | GX2_ATTRIB_FORMAT_SINT_8 |
| 4 | 0x2 |
| 5 | 0x102 |
| 6 | 0x202 |
| 7 | 0x302 |
| 8 | 0x803 |
| 9 | GX2_ATTRIB_FORMAT_UNORM_8_8 |
| 10 | GX2_ATTRIB_FORMAT_UINT_8_8 |
| 11 | GX2_ATTRIB_FORMAT_SNORM_8_8 |
| 12 | GX2_ATTRIB_FORMAT_SINT_8_8 |
| 13 | 0x105 |
| 14 | 0x305 |
| 15 | GX2_ATTRIB_FORMAT_FLOAT_32 |
| 16 | 0x7 |
| 17 | 0x107 |
| 18 | 0x207 |
| 19 | 0x307 |
| 20 | 0x808 |
| 21 | GX2_ATTRIB_FORMAT_UNORM_8_8_8_8 |
| 22 | GX2_ATTRIB_FORMAT_UINT_8_8_8_8 |
| 23 | GX2_ATTRIB_FORMAT_SNORM_8_8_8_8 |
| 24 | GX2_ATTRIB_FORMAT_SINT_8_8_8_8 |
| 25 | 0xB |
| 26 | 0x10B |
| 27 | 0x10C |
| 28 | 0x30C |
| 29 | GX2_ATTRIB_FORMAT_FLOAT_32_32 |
| 30 | 0xE |
| 31 | 0x10E |
| 32 | 0x20E |
| 33 | 0x30E |
| 34 | 0x80F |
| 35 | 0x110 |
| 36 | 0x310 |
| 37 | GX2_ATTRIB_FORMAT_FLOAT_32_32_32 |
| 38 | 0x112 |
| 39 | 0x312 |
| 40 | GX2_ATTRIB_FORMAT_FLOAT_32_32_32_32 |

### CGraphicsIndexBufferToken
| Type | Description |
| --- | --- |
| Uint32 | Index type |

| Value | GX2IndexType |
| --- | --- |
| 0 | GX2_INDEX_TYPE_U16 |
| 1 | GX2_INDEX_TYPE_U16 |
| 2 | GX2_INDEX_TYPE_U32 |

## NModelFormat::SMetaData
| Type | Description |
| --- | --- |
| Uint32 | Unknown (always 4) |
| Uint32 | Offset to GPU chunk in model file |
| [List]&lt;[NModelFormat::SReadBufferInfo](#nmodelformatsreadbufferinfo)&gt; | Buffer info |
| [List]&lt;[NModelFormat::SBufferInfo](#nmodelformatsbufferinfo)&gt; | Vertex buffers |
| [List]&lt;[NModelFormat::SBufferInfo](#nmodelformatsbufferinfo)&gt; | Index buffers |

### NModelFormat::SReadBufferInfo
| Type | Description |
| --- | --- |
| Uint32 | Size |
| Uint32 | Offset |

### NModelFormat::SBufferInfo
| Type | Description |
| --- | --- |
| Uint32 | Read buffer index |
| Uint32 | Offset |
| Uint32 | Compressed size |
| Uint32 | Decompressed size |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CAABox]: types.md#caabox
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CVector4i]: types.md#cvector4i
[CColor4f]: types.md#ccolor4f
[CString]: types.md#cstring
[String]: types.md#string
[List]: types.md#list
[Map]: types.md#map