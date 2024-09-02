## [DKC:TF](/formats.md#dkctf) > Enums

This page lists enums used by more than one file format.

## Texture Filter
| ETextureFilter | GX2TexXYFilterMode |
| --- | --- |
| 0 | GX2_TEX_XY_FILTER_MODE_POINT |
| 1 | GX2_TEX_XY_FILTER_MODE_LINEAR |

## Texture Wrap
| ETextureWrap | GX2TexClampMode |
| --- | --- |
| 0 | GX2_TEX_CLAMP_MODE_CLAMP |
| 1 | GX2_TEX_CLAMP_MODE_WRAP |
| 2 | GX2_TEX_CLAMP_MODE_MIRROR |
| 3 | GX2_TEX_CLAMP_MODE_MIRROR_ONCE |

## Vertex Component
| EVertexComponent | Name |
| --- | --- |
| 0 | in_position |
| 1 | in_normal |
| 2 | in_tangent[0] |
| 3 | in_tangent[1] |
| 4 | in_texCoord[0] |
| 5 | in_texCoord[1] |
| 6 | in_texCoord[2] |
| 7 | in_texCoord[3] |
| 8 | in_color |
| 9 | in_boneIndices |
| 10 | in_boneWeights |
| 11 | in_bakedLightingCoord |
| 12 | in_bakedLightingTangent |
| 13 | in_vertInstanceColor |
| 14 | in_vertTransform[0] |
| 15 | in_vertTransform[1] |
| 16 | in_vertTransform[2] |
| 17 | in_vertTransformIT[0] |
| 18 | in_vertTransformIT[1] |
| 19 | in_vertTransformIT[2] |
| 20 | in_lastPosition |
| 21 | in_currentPosition |

## Material Type
| Type | Description |
| --- | --- |
| EXPL | Explicit |
| GBUF | GBuffer |
| LITP | LightPrePass |
| VIEW | DataView |
| FONT | Font |
| PART | Particle |
| DEPH | DepthPass |
| POST | PostFX |
| FOGV | FogVolume |
| WATR | Water |
| WATD | WaterDecal |
| MSIL | ModelSilhouette |
| SURF | Surface |
| LAMB | Lambert |
| REFL | Reflect |
| PHNG | Phong |
| FURM | Fur |