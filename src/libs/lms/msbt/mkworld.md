## [LMS](../../../formats.md#lms) > [MSBT](../msbt.md) > Mario Kart World

In addition to the standard [MSBT blocks](../msbt.md), the following block types are only seen in Mario Kart World:

| Type | Description |
| --- | --- |
| `LMF1` | [Unknown](#lmf1-block) |
| `LMT1` | [Unknown](#lmt1-block) |
| `RMF1` | [Unknown](#rmf1-block) |
| `RMT1` | [Unknown](#rmt1-block) |

## LMF1 Block
This block seems to be used only in `LayoutMsg.msarc`. It contains the layout name:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of layout names |
| 0x4 | | Layout names |

Every layout name is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Name size |
| 0x1 | | Name |

There is no null terminator behind the name.

## LMT1 Block
This block seems to be used only in `LayoutMsg.msarc`. Its format and purpose are unknown.

## RMF1 Block
This block is always empty, if present. Its purpose is unknown.

## RMT1 Block
This block contains one byte per message that is either 0 or 1. Its purpose is unknown.
