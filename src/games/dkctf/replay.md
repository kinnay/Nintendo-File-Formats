## [DKC:TF](/formats.md#dkctf) > Replay File

## Header
| Type | Description |
| --- | --- |
| Uint8 | Version number (always 5) |
| Uint32 | Number of frames |
| Uint32 | Size of replay data |
| ... | [Replay data](#replay-data) |

## Replay Data
| Type | Description |
| --- | --- |
| [List]&lt;[CCommandFrame]&gt; | Command frames (always one) |
| Uint32 | Main [character](#character-type) |
| Uint32 | Partner [character](#character-type) |
| [Bits]&lt;1&gt; | Is main player active (normally 1) |
| [Bits]&lt;1&gt; | Is partner active (normally 0) |
| [Bits]&lt;1&gt; | Inventory disabled (normally 0) |
| [CPlayerState::SInventory](#cplayerstatesinventory) | Inventory. *Only present if inventory is enabled.* | [Bits]&lt;4&gt; | Number of collected puzzle pieces |
| [Bits]&lt;2&gt; | Number of gold hearts (main player) |
| [Bits]&lt;2&gt; | Number of gold hearts (partner) |
| ... | Replay frames |

### Character Type
| Value | Description |
| --- | --- |
| 0 | Invalid |
| 1 | Donkey kong |
| 2 | Diddy kong |
| 3 | Rambi |
| 4 | Minecart |
| 5 | Rocket |
| 6 | Dixie kong |
| 7 | Cranky kong |

### CPlayerState::SInventory
| Type | Description |
| --- | --- |
| [Bits]&lt;32&gt; | Number of bananas |
| [Bits]&lt;32&gt; | Number of coins |
| [Bits]&lt;32&gt; | Number of balloons |
| [Bits]&lt;32&gt; | Super combined ability meter |
| [Bits]&lt;32&gt; | Trophy key 1 | 
| [Bits]&lt;32&gt; | Trophy key 2 |
| [Bits]&lt;32&gt; | Trophy key 3 |
| [Bits]&lt;32&gt; | Trophy key 4 |
| [Bits]&lt;32&gt; | Trophy key 5 |
| [Bits]&lt;32&gt; | Trophy key 6 |
| [Bits]&lt;32&gt; | Trophy key 7 |
| [Bits]&lt;32&gt; | Number of squawks |
| [Bits]&lt;32&gt; | Number of crash guard items |
| [Bits]&lt;32&gt; | Number of heart boost items |
| [Bits]&lt;32&gt; | Number of blue balloons |
| [Bits]&lt;32&gt; | Number of green balloons |
| [Bits]&lt;32&gt; | Number of banana juice items |
| [Bits]&lt;32&gt; | Number of diddy barrels |
| [Bits]&lt;32&gt; | Number of dixie barrels |
| [Bits]&lt;32&gt; | Number of cranky barrels |
| [Bits]&lt;32&gt; | Final boss award |

## CCommandFrame
| Type | Description |
| --- | --- |
| [List]&lt;[List]&lt;[CCommandFrame::SCommandInfo](#ccommandframescommandinfo)&gt;&gt; | Command info lists (always two lists) |
| Uint8 | Unknown |

### CCommandFrame::SCommandInfo
| Type | Description |
| --- | --- |
| Uint8 | Command |

[CCommandFrame]: #ccommandframe

[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[CVector3f]: types.md#cvector3f
[CColor4f]: types.md#ccolor4f
[CMayaSpline]: types.md#cmayaspline
[CTimelineData]: types.md#ctimelinedata
[Property]: #property-format
[List]: types.md#list
[String]: types.md#string
[CString]: types.md#cstring
[Bits]: types.md#bits