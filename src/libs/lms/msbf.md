## [LMS](../../formats.md#lms) > [Overview](overview.md) > Flow Chart (MSBF)

This file is identified by the magic number `MsgFlwBn`. The format holds flowcharts.

| Type | Description |
| --- | --- |
| `FLW3` | [Nodes](#flw3-block) |
| `FEN1` | [Flowchart Labels](#fen1-block) |
| `REF1` | ? |

## FLW3 Block
This section holds all the [nodes](#nodes).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2  | Node count |
| 0x2 | 2  | Branch table ID count |
| 0x4 | 12 | Padding |
| 0x10 | 16 per node | [Nodes](#nodes)
| | 2 per ID | [Branch table](#branch-table) |
| | | [String table](#string-table)

### Nodes
Actions defined within the FLW3 Section are done via nodes. 

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Node type](#node-types) |
| 0x1 | 1|  [Parameter type](#parameter-type) (Only for [Branch Nodes](#branch-node) and [Event Nodes](#event-node))|
| 0x2 | 2 | Reserved |
| 0x4 | 4 | Parameter data |
| 0x8 | 8 | Node data |

#### Node Types
| Value | Type | Description |
| --- | --- | --- |
| 1 | [Message](#message-node) | Prompts a message from a MSBT file |
| 2 | [Branch](#branch-node) | Branches to a different node depending on a specific condition |
| 3 | [Event](#event-node) | Executes a specific action or game event | 
| 4 | [Entry](#entry-node) | Node that acts as a starting point for a flowchart |
| 5 | [Jump](#jump-node) | Jumps  to a different flowchart |

#### Parameter Type
Branch and event nodes may vary in their functionality depending on the parameter type. This type determines how the parameter data will be parsed by the game. Once the data has been
interpreted, the values obtained are passed to the node as arguments.

| Value | Arguments              | Description                                                                                              |
|-------|------------------------|----------------------------------------------------------------------------------------------------------|
| 0     | `s32`                  | Single node argument                                                                                     |
| 1     | `s32`, `s32`           | Two node arguments                                                                                       |
| 2     | `s16`, `s8`, `s8`      | Three node arguments                                                                                     |
| 3     | `s8`, `s8`, `s16`      | Three node arguments (alternate argument layout)                                                         |
| 4     | `s8`, `s8`, `s8`, `s8` | Four node arguments                                                                                      |
| 5     | `string`               | String value. Stored as an offset from start of block to the string in the [string table](#string-table) |
| 6     | `s32`                  | Single node argument                                                                                     |


### Message Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Next node index |
| 0x2 | 2 | [MSBT](msbt.md) file index |
| 0x4 | 2 | Message index into [TXT2](msbt.md#txt2-block) |
| 0x6 | 2 | Unused |

### Branch Node 
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | `0xFFFF`|
| 0x2 | 2 | Node Identifier |
| 0x4 | 2 | Branch table case count |
| 0x6 | 2 | Starting index into the branch table |

### Event Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Next node index |
| 0x2 | 2 | Node identifier |
| 0x4 | 4 | Unused |

The node identifier allows a game to link the node to a specific action or condition. 

### Entry Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Next node index |
| 0x2 | 6 | Unused |

### Jump Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Flowchart index |
| 0x2 | 6 | Unused |

The next node index when marked as `0xFFFF` is the end of a flowchart unless it is a branch node. The next node for a jump node must refer to the index of the entry node for another flowchart.

### Branch Table
Nodes that are branch will jump to a specifc case based on a condition. These function like switch statements.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 || List of node IDs |

### String Table 
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 || List of null-terminated strings | 

## FEN1 Block
This block contains the flowchart [labels](overview.md#hash-tables). The index of a flowchart is the location of its Entry [node](#nodes).
