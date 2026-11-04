## [DKC:TF](../../formats.md#dkctf) > Audio Samples (CSMP)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor (`CSMP`) |

## CSMP Form
Version: 10

| Type | Description |
| --- | --- |
| [CChunkDescriptor] | FMTA chunk ([NAxal::SADPCMFormatInfo](#naxalsadpcmformatinfo)) |
| [CChunkDescriptor] | DATA chunk. This chunk contains raw ADPCM samples. |
| [CChunkDescriptor] | LABL chunk (optional) |

### NAxal::SADPCMFormatInfo
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |

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