## [LMS](../../formats.md#lms) > [Overview](overview.md) > Flow Chart (MSBF)

This file is identified by the magic number `MsgFlwBn`. The format is responsible for holding flowcharts.

| Type | Description |
| --- | --- |
| `FLW3` | [Nodes](##flw3-block) |
| `FEN1` | [Flowchart Labels](##ref1-block) |
| `REF1` | ? |

## FLW3 Block
This section is responsible for holding all the [nodes](#nodes).

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
| 0x1 | 1|  [Subtype](#sub-types) |
| 0x2 | 2 | Reserved |
| 0x4 | 2 | Subtype value |
| 0x6 | 10 | Node specifc data |

#### Node Types
| Value | Type | Description |
| --- | --- | --- |
| 1 | [Message](#message-node) | Prompts a message from a MSBT. |
| 2 | [Branch](#branch-node) | Branches into different nodes based on a condition. |
| 3 | [Event](#event-node) | Pompts an action or event. | 
| 4 | [Entry](#entry-node) | Node that acts as a starting point. |
| 5 | [Jump](#jump-node) | Jumps to a different node. |

#### Subtypes
Implementations of type specifc data vary between game. These types are only valid for Branch and Event nodes.

| Value | Description |
| --- | --- |
| 0 | Unknown |
| 1 | Unknown |
| 2 | Unknown | 
| 3 | Unknown |
| 4 | Unknown |
| 5 | Offset from start of block to string in [string table](#string-table). Specific to Event and Branch nodes. |
| 6 | Unknown |

### Message Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unused  |
| 0x2 | 2 | Next node index |
| 0x4 | 2 | MSBT file index  |
| 0x6 | 2 | TXT2 message index |
| 0x8 | 2 | Unused |

### Branch Node 
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Short 1  |
| 0x2 | 2 | 0xFFFF (always as next node index) |
| 0x4 | 2 | Short 3 |
| 0x6 | 2 | Branch table case count |
| 0x8 | 2 | Starting index into the branch table |

Short data is specifc to the game and subtype of the node.

### Event Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Short 1  |
| 0x2 | 2 | Next node index |
| 0x4 | 2 | Short 3  |
| 0x6 | 2 | Short 4  |
| 0x8 | 2 | Short 5  |

Short data is specifc to the game and subtype of the node.

### Entry Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unused  |
| 0x2 | 2 | Next node index |
| 0x4 | 2 | Unused |
| 0x6 | 2 | Unused |
| 0x8 | 2 | Unused |

### Jump Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unused  |
| 0x2 | 2 | Next node index |
| 0x4 | 2 | Unused |
| 0x6 | 2 | Unused |
| 0x8 | 2 | Unused |

0xFFFF marks the end of a flowchart for any node that isn't a branch node.

### Branch Table
Nodes that are branch will jump to a specifc case based on a condition.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 || List of node IDs |

### String Table 
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | | List of null-terminated strings. |

## FEN1 Block
This block contains the flowchart [labels](overview.md#hash-tables). The index of a flowchart is the location of it's Entry Node.
