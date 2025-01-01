## [LMS](../../formats.md#lms) > [Overview](overview.md) > Flow Chart (MSBF)

This file is identified by the magic number `MsgFlwBn`. The format is responsible for handling of event actions defined by nodes.

| Type | Description |
| --- | --- |
| `FLW3` | [Nodes](#flw3-Block) |
| `FEN1` | [Flowchart Labels](#ref1-Block) |
| `REF1` | ? |

## FEN1 Block
This block contains the flowchart [labels](overview.md#hash-tables). The index of a flowchart is the location of it's Entry Node.

## FLW3 Block
This section is responsible for holding all the [nodes](#Nodes).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2  | Node count |
| 0x2 | 2  | Branch table node count  (See [branch table](#branch-table)) |
| 0x4 | 12 | Padding |
| 0x10 | 16 per node | [Nodes](#Nodes)
|      | 2 per ID | [Branch table](#branch-table)
|      |         | [String table](#string-table)

## Nodes
Actions defined within the FLW3 Section are done via nodes. 

| Offset | Size | Description |
| --- | --- | --- |
| 0x00 | 1 | [Node type](#node-types) |
| 0x01 | 1|  [Subtype](#sub-types) |
| 0x02 | 2 | Reserved |
| 0x04 | 2 | Subtype value |
| 0x06 | 10 | Collection of 5 shorts |

### Node Types
| Value | Type | Description |
| --- | --- | --- |
| 0x01 | [Message](#message-node) | Prompts a message from a MSBT. |
| 0x02 | [Branch](#branch-node) | Branches into different nodes based on a condition. |
| 0x03 | [Event](#event-node) | Pompts an action or event. | 
| 0x04 | [Entry](#entry-node) | Node that acts as a starting point. |
| 0x05 | [Jump](#jump-node) | Jumps to a different node. |

### Subtypes
Implementations of type specifc data vary between game. These types are only valid for Branch and Event nodes.

| Value | Description |
| --- | --- |
| 0x00 | Unknown |
| 0x01 | Unknown |
| 0x02 | Unknown | 
| 0x03 | Unknown |
| 0x04 | Unknown |
| 0x05 | Offset from start of block to null-terminated string in the [string table](#string-table) | |
| 0x06 | Unknown |

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
| 0x4 | 2 | Unused   |
| 0x6 | 2 | Unused   |
| 0x8 | 2 | Unused   |

### Jump Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unused  |
| 0x2 | 2 | Next node index |
| 0x4 | 2 | Unused  |
| 0x6 | 2 | Unused  |
| 0x8 | 2 | Unused  |

0xFFFF marks the end of a flowchart.

## Branch Table
Nodes that are branch will jump to a specifc case based on a condition.

| Offset | Size | Description |
| --- | --- | --- |
| 0x00 |    | List of node IDs |


## String Table 
| Offset | Size | Description |
| --- | --- | --- |
| 0x00 |    | List of null-terminated strings. Only referenced by Event nodes with type of 0x5. |
