## [NW](/formats.md#nw) > [Sound](./sound.md) > Sequence Sound (FSEQ)

This file contains a sequence sound. A sequence sound specifies which notes should be played at what time using instruments from a [bank file](./bfbnk.md).

| Block id | Description |
| --- | --- |
| `0x5000` | [Data block](#data-block) |
| `0x5001` | [Label block](#label-block) |

## Data Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("INFO") |
| 0x4 | 4 | Block size |
| 0x8 | | Data |

A sequence track consists of a stream of commands. These are stored in the data block. Every command starts with a single byte that specifies the type of the command, which is usually followed by one or more parameters (depending on the command).

Time is divided into beats, which are futher divided into ticks. The default number of beats per minute is 120, and the default number of ticks per beat is 48.

Some commands operate on variables. These are accessed by index, and can be divided into the following categories:

| Variable | Description |
| --- | --- |
| 0 - 15 | Local variables (per sequence file) |
| 16 - 31 | Global variables (shared for all sequence files) |
| 32 - 47 | Track variables (per sequence track) |

### Command Table
| Command | Description |
| --- | --- |
| 0x0 - 0x7F | [Play note](#note-command) |
| 0x80 | [Sleep](#sleep-command) |
| 0x81 | [Change instrument](#change-instrument-command) |
| 0x88 | [Start track](#start-track-command) |
| 0x89 | [Jump](#jump-command) |
| 0xB0 | [Set ticks per beat](#set-ticks-per-beat-command) |
| 0xE1 | [Set beats per minute](#set-beats-per-minute) |
| 0xF0 | [Extended command](#extended-command) |
| 0xFE | [Allocate tracks](#alloc-tracks-command) |
| 0xFF | [End](#end-command) |

### Variable Length Int
Some commands take an integer of variable length. This integer is parsed as follows:

```python
def read_varint():
    value = 0
    while True:
        byte = read_u8()
        value = (value << 7) | (byte & 0x7F)
        if not byte & 0x80:
            return value
```

### Note Command
All commands between 0 and 127 play a note. The command number specifies the 'key'.

| Type | Description |
| --- | --- |
| Uint8 | Velocity |
| [Varint] | Length |

### Sleep Command
| Type | Description |
| --- | --- |
| [Varint] | Number of ticks |

### Change Instrument Command
| Type | Description |
| --- | --- |
| [Varint] | Instrument index |

### Start Track Command
| Type | Description |
| --- | --- |
| Uint8 | Track index |
| Uint24 | Start offset |

### Jump Command
This is a simple control flow command.

| Type | Description |
| --- | --- |
| Uint24 | Offset into data block |

### Set Ticks Per Beat Command
| Type | Description |
| --- | --- |
| Uint8 | Ticks per beat |

### Set Beats Per Minute Command
| Type | Description |
| --- | --- |
| Uint16 | Beats per minute |

### Alloc Tracks Command
This command specifies the number of tracks that are allocated for this sequence sound. If present, this command must be the first command in the data block.

| Type | Description |
| --- | --- |
| Uint16 | Track mask |

### End Command
This command stops the current track.

### Extended Command
This command starts with a single byte that indicates the type of its subcommand.

| Subcommand | Description |
| --- | --- |
| 0x80 - 0x8B | [Variable operation](#variable-operation) |
| 0x90 - 0x95 | [Variable comparison](#variable-comparison) |

#### Variable Operation
| Type | Description |
| --- | --- |
| Uint8 | Variable index |
| Int16 | Value |

<br>

| Command ID | Description |
| --- | --- |
| 0x80 | `var = value` |
| 0x81 | `var = var + value` |
| 0x82 | `var = var - value` |
| 0x83 | `var = var * value` |
| 0x84 | `var = var / value` |
| 0x85 | `var = var << value` (negative value shifts to right instead) |
| 0x86 | `var` is set to random value between 0 and `value` |
| 0x87 | `var = var & value` |
| 0x88 | <code>var = var &vert; value</code> |
| 0x89 | `var = var ^ value` |
| 0x8A | `var = ~value` |
| 0x8B | `var = var % value` |

#### Variable Comparison
| Type | Description |
| --- | --- |
| Uint8 | Variable index |
| Int16 | Value |

This command compares a variable with a given value and writes the result (0 or 1) into the internal condition register of the command processor.

| Command ID | Description |
| --- | --- |
| 0x90 | `var == value` |
| 0x91 | `var >= value` |
| 0x92 | `var > value` |
| 0x93 | `var <= value` |
| 0x94 | `var < value` |
| 0x95 | `var != value` |

## Label Block
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("LABL") |
| 0x4 | 4 | Block size |
| 0x8 | 4 | Number of labels |
| 0xC | | [References] to [labels](#label) (0x5100) |

### Label
All labels are aligned to 4 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Reference] into [data block](#data-block) (0x1F00) |
| 0x8 | 4 | Name length without null terminator |
| 0xC | | Null-terminated label name |

[VarInt]: #variable-length-int
[references]: ./sound.md#section-reference
[reference]: ./sound.md#section-reference
[Item id]: ./sound.md#item-id
[Item ids]: ./sound.md#item-id