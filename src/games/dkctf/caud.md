## [DKC:TF](../../formats.md#dkctf) > Audio Sound Effect (CAUD)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor (`CAUD`) |

## CAUD Form
Version: 6

| Type | Description |
| --- | --- |
| [String] | Sound effect name |
| [List]&lt;[String]&gt; | Sound group names |
| Float | Unknown |
| Float | Unknown |
| Uint32 | [Flags](#flags) |
| Uint8 | Audio bus id |
| [List]&lt;[CAudioSoundEffect::CGobData](#caudiosoundeffectcgobdata)&gt; | Audio information |

### Flags
| Mask | Description |
| --- | --- |
| 1 | Unknown |
| 2 | Unknown |
| 4 | Unknown |
| 8 | Unknown |

### CAudioSoundEffect::CGobData
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Float | Unknown |
| [List]&lt;[CAudioMetaSample](#caudiometasample)&gt; | Metadata list |
| [List]&lt;[CAudioSoundEffect::CGobRefData](#caudiosoundeffectcgobrefdata)&gt; | Reference data |

#### CAudioMetaSample
| Type | Description |
| --- | --- |
| [CObjectId] | Audio sample object id |
| Float | field_C |
| Uint32 | field_10 |
| Uint32 | field_14 |
| Float | field_18 |
| Float | field_1C |
| Float | Adjusted default volume |
| Float | field_24 |
| Uint32 | field_28 |
| Uint32 | field_2C |
| Uint32 | field_30 |
| Uint32 | field_34 |
| Uint32 | field_38 |
| Uint32 | field_3C |
| Uint32 | field_40 |
| Float | field_44 |
| Float | field_48 |
| Float | field_4C |
| Float | field_50 |
| Float | Center channel usage |
| Bool | field_58 (1) |
| Bool | field_58 (2) |
| Bool | field_58 (4) |
| Bool | field_58 (8) |
| Bool | field_58 (16) |
| Bool | field_58 (32) |
| Bool | field_58 (64) |
| Bool | Is controller sound |
| [CMayaSpline] | Volume spline |
| [CMayaSpline] | Pitch spline |
| [CMayaSpline] | Pan spline |
| [CMayaSpline] | Surround pan spline |
| [List]&lt;Pair&lt;Float, Float&gt;&gt; | field_11C |
| Uint32 | Priority |
| Float | field_12C |
| [CMayaSpline] | Low pass frequency spline |
| [CVector3f] | field_160 |

#### CAudioSoundEffect::CGobRefData
| Type | Description |
| --- | --- |
| Uint32 | field_0 |
| [List]&lt;Pair&lt;Float, Float&gt;&gt; | field_4 |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[CVector3f]: types.md#cvector3f
[CColor4f]: types.md#ccolor4f
[CMayaSpline]: types.md#cmayaspline
[CTimelineData]: types.md#ctimelinedata
[List]: types.md#list
[String]: types.md#string
[CString]: types.md#cstring