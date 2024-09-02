## [DKC:TF](../../formats.md#dkctf) > Types

In DKC:TF, some types appear in multiple different file formats. This page lists the most common types.

Basic types:

* [String](#string)
* [CString](#cstring)
* [List](#list)
* [List16](#list16)
* [Map](#map)
* [Bits](#bits)

Class types:

* [CFourCC](#cfourcc)
* [CGuid](#cguid)
* [CObjectId](#cobjectid)
* [CObjectTag](#cobjecttag)
* [CAssetHeader](#cassetheader)
* [CFormDescriptor](#cformdescriptor)
* [CChunkDescriptor](#cchunkdescriptor)
* [CVector3f](#cvector3f)
* [CVector4i](#cvector4i)
* [CColor4f](#ccolor4f)
* [CAABox](#caabox)
* [CMayaSpline](#cmayaspline)

## String
| Type | Description |
| --- | --- |
| Uint32 | Length |
| Char[] | Data |

## CString
| Type | Description |
| --- | --- |
| Char[] | Null-terminated string |

## List
| Type | Description |
| --- | --- |
| Uint32 | Number of entries |
| | Entries |

## List16
| Type | Description |
| --- | --- |
| Uint16 | Number of entries |
| | Entries |

## Map
| Type | Description |
| --- | --- |
| Uint16 | Number of key-value pairs |
| | First key |
| | First value |
| | ... |
| | Last key |
| | Last value |

## Bits
Some file formats ignore byte boundaries and read individual bits from a file. When a larger type (such as Uint32) is extracted and not all bits in a byte have been read, the remaining bits in the byte are discarded and the stream becomes byte-aligned again.

## CFourCC
| Type | Description |
| --- | --- |
| Char[4] | Identifier |

## CGuid
| Type | Description |
| --- | --- |
| Uint32 | Part 1 |
| Uint16 | Part 2 |
| Uint16 | Part 3 |
| Uint64 | Part 4 |

## CObjectId
| Type | Description |
| --- | --- |
| [CGuid](#cguid) | Guid |

## CObjectTag
| Type | Description |
| --- | --- |
| [CFourCC](#cfourcc) | Type |
| [CObjectId](#cobjectid) | Object id |

## CAssetHeader
| Type | Description |
| --- | --- |
| Uint16 | Type id |
| Uint16 | Version |

## CFormDescriptor
| Type | Description |
| --- | --- |
| [CFourCC](#cfourcc) | Identifier ("RFRM") |
| Uint64 | Data size |
| Uint64 | Unknown |
| [CFourCC](#cfourcc) | Form type |
| Uint32 | Version number |
| Uint32 | Version number |
| ... | Form data |

## CChunkDescriptor
| Type | Description |
| --- | --- |
| [CFourCC](#cfourcc) | Chunk type |
| Uint64 | Data size |
| Uint32 | Unknown |
| Uint64 | Data offset |

## CVector3f
| Type | Description |
| --- | --- |
| Float | x |
| Float | y |
| Float | z |

## CVector4i
| Type | Description |
| --- | --- |
| Int32 | x |
| Int32 | y |
| Int32 | z |
| Int32 | w |

## CColor4f
| Type | Description |
| --- | --- |
| Float | red |
| Float | green |
| Float | blue |
| Float | alpha |

## CAABox
| Type | Description |
| --- | --- |
| [CVector3f](#cvector3f) | Low edge |
| [CVector3f](#cvector3f) | High edge |

## CMayaSpline
| Type | Description |
| --- | --- |
| [List](#list)&lt;[CMayaSplineKnot](#cmayasplineknot)&gt; | Knots |
| Float | Minimum |
| Float | Maximum |
| [EInfinityType](#einfinitytype) | Pre infinity |
| [EInfinityType](#einfinitytype) | Post infinity |
| [EClampMode](#eclampmode) | Clamp mode |

### EInfinityType
This enum specifies how the spline behaves before the first knot and behind the last knot.

| Value | Description |
| --- | --- |
| 0 | Constant |
| 1 | Linear |
| 2 | Cycle |
| 3 | CycleRelative |
| 4 | Oscillate |

### EClampMode
This enum specifies how the spline is clamped if it is not between the minimum and maximum values.

| Value | Description |
| --- | --- |
| 0 | Don't clamp |
| 1 | Standard clamp (force to minimum/maximum) |
| 2 | Cyclic clamp (if it's too high, wrap around to minimum) |

### CMayaSplineKnot
| Type | Description |
| --- | --- |
| Float | Time |
| Float | Value |
| [ETangentType](#etangenttype) | Tangent type 1 |
| [ETangentType](#etangenttype) | Tangent type 2 |
| Float | field_C; *Only present if tangent type 1 is `Fixed`*. |
| Float | field_10; *Only present if tangent type 1 is `Fixed`*. |
| Float | field_14; *Only present if tangent type 2 is `Fixed`*. |
| Float | field_18; *Only present if tangent type 2 is `Fixed`*. |

#### ETangentType
| Value | Description |
| --- | --- |
| 0 | Linear |
| 1 | Flat |
| 2 | Smooth |
| 3 | Step |
| 4 | Clamped |
| 5 | Fixed |
