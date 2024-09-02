## [LMS](/formats.md#lms) > [Overview](overview.md) > Message File (MSBT)

This file is identified by the magic number `MsgStdBn`. It contains text strings that are looked up by label.

| Type | Description |
| --- | --- |
| LBL1 | [Message labels](#message-labels) |
| TXT2 | [Message strings](#txt2-block) |
| ATR1 | [Attributes](#atr1-block) |
| TSY1 | [Text style](#tsy1-block) |

## LBL1 Block
This block contains [labels](overview.md#hash-tables) for the TXT2, ATR1 and TSY1 blocks.

## TXT2 Block
This block contains the actual text strings.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of messages |
| 0x4 | 4 per message | Offsets to message strings | 
| | | Null-terminated message strings |

A message string may contain control tags, which may for example change the style of the text. A control tag always starts with character 0xE, which is followed by:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Tag group |
| 0x2 | 2 | Tag type |
| 0x4 | 2 | Size of parameters |
| 0x6 | | Parameters |

Character 0xF marks the end of a region that is affected by a control tag. This character always takes up exactly 6 bytes (including the 0xF character), regardless of the character encoding.

All tags and their parameters are defined in the [TGG2 block](msbp.md#tgg2-block) of the MSBP file.

### Predefined Tags
Tag group 0 (called 'System') contains predefined tags, while all other tag groups are game-specific. The following tags are defined under tag group 0:

| Tag | Name | Parameters |
| --- | --- | --- |
| 0 | Ruby | `rt` |
| 1 | Font | `face` |
| 2 | Size | `percent` |
| 3 | Color | `r`, `g`, `b` and `a` |
| 4 | PageBreak | None |

## ATR1 Block
This block contains attributes for each message. The format of the attributes is game-specific. Depending on the game, the attributes may contain offsets to strings that are stored behind the attribute table.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of attributes |
| 0x4 | 4 | Bytes per attribute |
| 0x8 | | Attributes |
| | | Strings |

## TSY1 Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 per message | Style index in [MSBP file](msbp.md) |