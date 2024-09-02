## [DKC:TF](../../formats.md#dkctf) > Loose Data (LDTA)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

### CHAR Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [LDCH chunk](#ldch-chunk) |

### LDCH Chunk
The name 'loose data' suggests that this file may contain any kind of data. However, in DKC:TF this file is only used to store controller button mappings, and the LDCH chunk simply contains a [SLdrGameControls](structs.md#sldrgamecontrols) struct.

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor