## [DKC:TF](../../formats.md#dkctf) > Character File (CHAR)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

## CHAR Form
| Type | Description |
| --- | --- |
| [CAssetHeader] | Asset header |
| [NCharacter::SInfo](#ncharactersinfo) | Character info |
| [CString] | Name |
| [CObjectId] | Skeleton file id |
| [List]&lt;[CCharacterModelSet](#ccharactermodelset)&gt; | Character model sets |
| [List]&lt;[CAnimationInfo](#canimationinfo)&gt; | Animation infos |
| [CAnimationIdMap](#canimationidmap) | *Only present if `flags & 0x2000`* |
| CTransitionInfo | *Only present if `flags & 0x8000`* |
| [List]&lt;CCharacterTransformBits&gt; | *Only present if `flags & 0x4000`* |
| [List]&lt;Int32&gt; | field_4C |
| [List]&lt;CSkelJointSet&gt; | Skel joint sets |
| CAnimEffectResSetInfo | *Only present if `flags & 0x1000`* |
| CAnimEventData | *Only present if `flags & 0x800`* |
| CAnimStateData | *Only present if `flags & 0x400`* |
| CAnimSequenceInfoSet | *Only present if `flags & 0x200`* |
| CAnimGridInfoSet | *Only present if `flags & 0x100`* |
| CAnimRandomInfoSet | *Only present if `flags & 0x80`* |
| CAnimEffectData | *Only present if `flags & 0x40`* |
| CPASDatabase | *Only present if `flags & 0x20`* |
| CAnimCollisionPrimData | *Only present if `flags & 0x10`* |
| [CAABox] | AA box |

### NCharacter::SInfo
| Type | Description |
| --- | --- |
| Uint8 | field_0 |
| Uint8 | field_1 |
| Uint8 | field_2 |
| Uint8 | field_3 |
| Uint8 | field_4 |
| Uint8 | field_5 |
| Uint8 | field_6 |
| Uint8 | field_7 |
| Uint8 | field_8 |
| Uint8 | field_9 |
| Uint8 | field_A |
| Uint8 | field_B |
| Uint8 | field_C |
| Uint8 | field_D |
| Uint8 | field_E |
| Uint8 | field_F |
| Uint24 | Flags. This field determines which fields will be loaded later in this file. |

### CCharacterModelSet
| Type | Description |
| --- | --- |
| [CString] | Name |
| [CObjectId] | [Skinned model](model.md) file id |
| [CAABox] | AA box |

### CAnimationInfo
| Type | Description |
| --- | --- |
| [CString] | Name |
| [CObjectId] | File id |
| Uint32 | field_1C |
| Uint32 | field_20 |
| Uint16 | field_24 |
| Uint16 | field_26 |
| Bool | field_28 |
| [CAABox] | AA box |

### CAnimationIdMap
| Type | Description |
| --- | --- |
| [List]&lt;Int32&gt; | Hash nodes |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CAssetHeader]: types.md#cassetheader
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[List]: types.md#list
[CString]: types.md#cstring
[Map]: types.md#map