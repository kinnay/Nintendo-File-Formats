## [XLINK](/formats.md#xlink) > Sound / Effect Links

This format is used by `.bslnk` and `.belnk` files.

This file is structured as follows:

| Section |
| --- |
| [Header](#header) |
| [User data table](#user-data-table) |
| [Param define table](#param-define-table) |
| [Resource asset param table](#resource-asset-param-table) |
| [Trigger overwrite param table](#trigger-overwrite-param-table) |
| [Local property name ref table](#local-property-name-ref-table) |
| [Local property enum name ref table](#local-property-enum-name-ref-table) |
| [Direct value table](#direct-value-table) |
| [Random table](#random-table) |
| [Curve table](#curve-table) |
| [Curve point table](#curve-point-table) |
| [Ex region](#ex-region) |
| [Condition table](#condition-table) |
| [Name table](#name-table) |

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | magic (`XLNK`) |
| 0x4 | 4 | dataSize |
| 0x8 | 4 | version |
| 0xC | 4 | numResParam |
| 0x10 | 4 | numResAssetParam |
| 0x14 | 4 | numResTriggerOverwriteParam |
| 0x18 | 4 | triggerOverwriteParamTablePos |
| 0x1C | 4 | localPropertyNameRefTablePos |
| 0x20 | 4 | numLocalPropertyNameRefTable |
| 0x24 | 4 | numLocalPropertyEnumNameRefTable |
| 0x28 | 4 | numDirectValueTable |
| 0x2C | 4 | numRandomTable |
| 0x30 | 4 | numCurveTable |
| 0x34 | 4 | numCurvePointTable |
| 0x38 | 4 | exRegionPos |
| 0x3C | 4 | numUser |
| 0x40 | 4 | conditionTablePos |
| 0x44 | 4 | nameTablePos |

## User Data Table
The number of entries is specified by the `numUser` field in the [header](#header).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 bytes per entry | CRC32 hashes. These must be sorted because a binary search algorithm is used. |
| | 4 bytes per entry | Offset to data in [ex region](#ex-region) (absolute). Must be stored in the same order as the hashes. |

## Param Define Table
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size of this section |
| 0x4 | 4 | Number of user params |
| 0x8 | 4 | Number of asset params |
| 0xC | 4 | Unknown |
| 0x10 | 4 | Number of trigger params |
| 0x14 | | [User params](#param-def) |
| | | [Asset params](#param-def) |
| | | [Trigger params](#param-def) |
| | | Null-terminated strings for param names and default values |

### Param Def
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Name (offset into string table) |
| 0x4 | 4 | [Type](#param-type) |
| 0x8 | 4 | Default value |

### Param Type
| Value | Description |
| --- | --- |
| 4 | String (default value is offset into string table) |

## Resource Asset Param Table
The number of entries is specified by the `numResAssetParam` field in the [header](#header).

Every entry starts with an 8-byte mask, where every bit represents an asset param def from the [param define table](#param-define-table).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Mask |
| 0x8 | 4 | First reference (if `mask & 1`) |
| | 4 | Second reference (if `mask & 2`) |
| | 4 | Third reference (if `mask & 4`) |
| | | ... |

Every reference is stored as `0xXXYYYYYY`, where `X` in indicates the reference type and `Y` its value.

## Trigger Overwrite Param Table
The number of entries in table is specified by the `numResTriggerOverwriteParam` field in the [header](#header), and its position in the file is stored in the `triggerOverwriteParamTablePos` field.

Every entry starts with a 4-byte mask, where every bit represents a trigger param def from the [param define table](#param-define-table).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Mask |
| 0x4 | 4 | First reference (if `mask & 1`) |
| | 4 | Second reference (if `mask & 2`) |
| | 4 | Third reference (if `mask & 4`) |
| | | ... |

Every reference is stored as `0xXXYYYYYY`, where `X` in indicates the reference type and `Y` its value.

## Local Property Name Ref Table
The number of entries in this table is specified by the `numLocalPropertyNameRefTable` field in the [header](#header) and its position in the file is stored in the `localPropertyNameRefTablePos` field.

Every entry is an offset into the [name table](#name-table) (4 bytes).

## Local Property Enum Name Ref Table
This table is stored immediately behind the [local property name ref table](#local-property-name-ref-table). The number of entries is specified by the `numLocalPropertyEnumNameRefTable` field in the [header](#header).

Every entry is an offset into the [name table](#name-table) (4 bytes).

## Direct Value Table
This table is stored immediately behind the [local property enum name ref table](#local-property-enum-name-ref-table). The number of entries is specified by the `numDirectValueTable` field in the [header](#header).

Every entry is just a 4-byte integer.

## Random Table
This table is stored immediately behind the [direct value table](#direct-value-table). The number of entries is specified by the `numRandomTable` field in the [header](#header).

Every entry is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Minimum (float) |
| 0x4 | 4 | Maximum (float) |

## Curve Table
This table is stored immediately behind the [random table](#random-table). The number of entries is specified by the `numCurveTable` field in the [header](#header).

Every entry consists of the following fields:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | curvePointStartPos |
| 0x2 | 2 | numPoint |
| 0x4 | 2 | curveType |
| 0x6 | 2 | isPropGlobal |
| 0x8 | 4 | propName |
| 0xC | 4 | propIdx |
| 0x10 | 2 | localPropertyNameIdx |
| 0x12 | 2 | Padding |

## Curve Point Table
This table is stored immediately behind the [curve table](#curve-table). The number of entries is specified by the `numCurvePointTable` field in the [header](#header).

Every entry is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | X (float) |
| 0x4 | 4 | Y (float) |

## Ex Region
This region contains user data that's pointed to by the [user data table](#user-data-table).

## Condition Table
The position of this table in the file is stored in the `conditionTablePos` field in the [header](#header). The size of this table can be determined by calculating the distance to the [name table](#name-table).

Every entry consists of the following fields:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | parentContainerType |

If parentContainerType is 1 or 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 4 | weight (float) |

Else:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 4 | propertyType |
| 0x8 | 4 | compareType |
| 0xC | 4 | value |
| 0x10 | 2 | localPropertyEnumNameIdx |
| 0x12 | 1 | isSolved |
| 0x13 | 1 | isGlobal |

## Name Table
The position of this table in the file is stored in the `nameTablePos` field in the [header](#header). It is always stored right behind the [condition table](#condition-table). This section contains null-terminated strings.