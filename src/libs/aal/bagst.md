## [AAL](../../formats.md#aal) > Audio Group Settings (BAGST)

This is an audio group file.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number ("AGST") |
| 0x4 | 2 | Endianness (0xFFFE for little endian) |
| 0x6 | 2 | Version number (2) |
| 0x8 | 4 | Filesize |
| 0xC | 4 | Offset to [tree section](#tree-section) |
| 0x10 | 4 | Offset to [group section](#group-section) |
| 0x14 | 4 | Offset to [string section](#string-section) |

## Tree Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("TREE") |
| 0x4 | 4 | Section size |
| 0x8 | 4 | Default group name (offset into string table) |
| 0xC | | [Root node](#tree-node) |

### Tree Node
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Node size (including children) |
| 0x4 | 4 | Group index |
| 0x8 | 4 | Number of children |
| 0xC | | [Child nodes](#tree-node) |

## Group Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("GRP ") |
| 0x4 | 4 | Section size |
| 0x8 | 4 | Number of groups  |
| 0xC | | Offset to [group param](#group-param) for each group (4 bytes each) |

### Group Param
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (offset into string table) |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 0x48 | [Default sound param](#default-sound-param) |
| 0x58 | 0x2C | [Group limiter param](#group-limiter-param) |
| 0x84 | 4 | Unknown |
| 0x88 | | [Ducking param](#ducking-param) |

### Default Sound Param
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Volume (float) |
| 0x4 | 4 | Pitch (float) |
| 0x8 | 4 | Lfe (float) |
| 0xC | 4 | Lpf (float) |
| 0x10 | 4 | Biquad filter type |
| 0x14 | 4 | Biquad filter value (float) |
| 0x18 | 4 | Angle index |
| 0x1C | 4 | Spread (float) |
| 0x20 | 4 | Device volume (float) |
| 0x24 | 4 | Unknown |
| 0x28 | 4 | Unknown |
| 0x2C | 4 | Unknown |
| 0x30 | 4 | Unknown |
| 0x34 | 4 | Unknown |
| 0x38 | 4 | Bus volume 0 (float) |
| 0x3C | 4 | Bus volume 1 (float) |
| 0x40 | 4 | Bus volume 2 (float) |
| 0x44 | 4 | Bus volume 3 (float) |

### Group Limiter Param
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Active sound limiter type](#active-sound-limiter-type) |
| 0x4 | 8 | [Active sound limiter settings](#active-sound-limiter-settings) |
| 0xC | 4 | Request sound limiter type |
| 0x10 | 0x14 | [Request sound limiter settings](#request-sound-limiter-settings) |
| 0x24 | 4 | Request interval limiter type |
| 0x28 | 4 | [Request interval limiter settings](#request-interval-limiter-settings) |

#### Active Sound Limiter Type
| Value | Description |
| --- | --- |
| 1 | Priority Earlier |
| 2 | Priority Later |
| 3 | Earlier |
| 4 | Later |

#### Active Sound Limiter Settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |

#### Request Sound Limiter Settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Unknown |

#### Request Interval Limiter Settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown (float) |

### Ducking Param
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 12 | [Group ducker settings](#group-ducker-settings) |
| 0xC | 4 | Ducking volume floor (float) |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | Number of targets |
| 0x18 | | Target settings |

#### Group Ducker Settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Unknown |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |

#### Target Settings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Offset into string table |
| 0x4 | 4 | Unknown |
| 0x8 | 4 | Unknown |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Unknown |

## String Section
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Identifier ("STRG") |
| 0x4 | 4 | Section size |
| 0x8 | | Null-terminated strings |