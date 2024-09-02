## [DKC:TF](../../formats.md#dkctf) > Level File (ROOM)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor |

## ROOM Form
| Type | Description |
| --- | --- |
| [CFormDescriptor] | [Room header (ROOM)](#room-header-form) |
| [CFormDescriptor]<br>[CFormDescriptor]<br>...<br>[CFormDescriptor] | [Script layers (LAYR)](#cscriptlayer) |

## Room Header Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [RMHD chunk (header)](#rmhd-chunk) |
| [CChunkDescriptor] | [PGRP chunk (performance groups)](#pgrp-chunk) |
| [CChunkDescriptor] | [LGEN chunk (generated objects)](#lgen-chunk) |
| [CFormDescriptor]<br>[CFormDescriptor]<br>...<br>[CFormDescriptor] | [Load unit forms (LUNT)](#lunt-form) |

### RMHD Chunk
| Type | Description |
| --- | --- |
| Uint16 | Unknown |

### PRGP Chunk
| Type | Description |
| --- | --- |
| [List16]&lt;[CScriptPerformanceGroup](#cscriptperformancegroup)&gt; | Performance groups |

#### CScriptPerformanceGroup
| Type | Description |
| --- | --- |
| Uint32 | Name length |
| Char[] | Name |
| [CGuid] | Editor id |
| Bool | Is active |
| [List16]&lt;[CGuid]&gt; | Referenced layers |

### LGEN Chunk
| Type | Description |
| --- | --- |
| [Map]&lt;[CGuid], [CGuid]&gt; | Object map |

### LUNT Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [LUHD chunk (header)](#luhd-chunk) |
| [CChunkDescriptor] | [LRES chunk (resource ids)](#lres-chunk) |
| [CChunkDescriptor] | [LLYR chunk (layer ids)](#llyr-chunk) |

#### LUHD Chunk
| Type | Description |
| --- | --- |
| [String] | Load unit name |
| [CGuid] | Load unit id |
| Uint16 | Flags |

#### LRES Chunk
| Type | Description |
| --- | --- |
| [List]&lt;[CObjectId]&gt; | Resource ids |

#### LLYR Chunk
| Type | Description |
| --- | --- |
| [List]&lt;[CGuid]&gt; | Layer ids |

## CScriptLayer
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [LHED chunk (header)](#lhed-chunk) |
| [CFormDescriptor] | [GSRP form (generated objects)](#gsrp-form) |
| [CFormDescriptor] | [SRIP form (script components)](#srip-form) |

### LHED Chunk
| Type | Description |
| --- | --- |
| [String] | Script layer name |
| [CGuid] | Layer id |
| Uint16 | Unknown |
| [List16]&lt;[CGuid]&gt; | Load unit ids |
| [CGuid] | Unknown |
| Bool | Unknown |

### GSRP Form
These components can be spawned by a GeneratorGOC. This form is filled with GGOB chunks containing the following data:

| Type | Description |
| --- | --- |
| [CGuid] | Object id |
| [List16]&lt;[CGameObjectComponent](#cgameobjectcomponent)&gt; | Components |

### SRIP Form
This form is filled with [CGameObjectComponent](#cgameobjectcomponent) chunks.

### CGameObjectComponent 
A CGameObjectComponent is stored as a COMP chunk with the following content:

| Type | Description |
| --- | --- |
| Uint32 | [Component type hash](components.md) |
| [CGuid] | Component id |
| [String] | Component name |
| [List16]&lt;[SConnection](#sconnection)&gt; | Connections |
| [List16]&lt;[SScriptLink](#sscriptlink)&gt; | Script links |
| ... | [Component data](components.md) |

#### SConnection
| Type | Description |
| --- | --- |
| [CFourCC] | Connection id 1 |
| [CFourCC] | Connection id 2 |
| [CGuid] | Component id |
| Uint16 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |

#### SScriptLink
| Type | Description |
| --- | --- |
| [CFourCC] | Link id |
| [CGuid] | Component id |
| Uint8 | Unknown |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CString]: types.md#cstring
[String]: types.md#string
[List]: types.md#list
[List16]: types.md#list16
[Map]: types.md#map