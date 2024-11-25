## [NW](../../formats.md#nw) > Layout File (FLYT)

A BFLYT file contains a layout, which defines a part the UI. This page describes version `2.2.0.0` of the file format.

All offsets are relative to the start of the section that they appear in.

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`FLYT`) |
| 0x4 | 2 | BOM (Always 0xFEFF) |
| 0x6 | 2 | Header size (always 0x14) |
| 0x8 | 4 | Version number |
| 0xC | 4 | Filesize |
| 0x10 | 2 | Number of sections |
| 0x12 | 2 | Padding |

## Sections
Every section is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Section identifier |
| 0x4 | 4 | Section size, including this header |
| 0x8 | | Section data |

The following sections may be found in a BFLYT file:

| Identifier | Description |
| --- | --- |
| `lyt1` | [Layout](#layout) |
| `cnt1` | Control data |
| `usd1` | User data |
| `txl1` | [Texture list](#resource-list) |
| `fnl1` | [Font list](#resource-list) |
| `mat1` | Material |
| `grp1` | [Group info](#group) |
| `grs1` | [Group start](#group) |
| `gre1` | [Group end](#group) |
| `pan1` | [Pane info](#pane) |
| `pas1` | [Pane start](#pane) |
| `pae1` | [Pane end](#pane) |
| `bnd1` | Bounding pane |
| `pic1` | Picture pane |
| `prt1` | Parts pane |
| `txt1` | Textbox pane |
| `wnd1` | Window pane |

## Layout
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Section header](#sections) |
| 0x8 | 1 | Is drawn from middle |
| 0x9 | 3 | Padding |
| 0xC | 4 | Layout width (float) |
| 0x10 | 4 | Layout height (float) |
| 0x14 | 4 | Maximum parts height (float) |
| 0x18 | 4 | Maximum parts width (float) |
| 0x1C | | Null-terminated layout name |

## Resource List
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Section header](#sections) |
| 0x8 | 2 | Number of filenames (N) |
| 0xA | 4 * N | Offsets to null-terminated filenames |
| | | Null-terminated filenames |

## Group
A `grp1` section contains the following data:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Section header](#sections) |
| 0x8 | 24 | Null-terminated group name |
| 0x20 | 2 | Number of children (N) |
| 0x22 | 2 | Padding |
| 0x24 | 24 * N | Names of children |

The `grs1` section and `gre1` section are always empty. They mark the start and end of a group respectively. A `grs1` section must always be preceded by a `grp1` section.

## Pane
The `pan1`, `bnd1` and `prt1` sections contain the following data. The `pic1`, `txt1` and `wnd1` sections also start with this data.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [Section header](#sections) |
| 0x8 | 1 | Flags:<br>1 = is visible<br>2 = transmit alpha to children |
| 0x9 | 1 | This is a bitfield:<br>`0x03`: origin X (0=center, 1=left, 2=right)<br>`0x0C`: origin Y (0=center, 1=top, 2=bottom)<br>`0x30`: origin of parent X (0=center, 1=left, 2=right)<br>`0xC0`: origin of parent Y (0=center, 1=top, 2=bottom) |
| 0x0A | 1 | Alpha value |
| 0x0B | 1 | Part scaling |
| 0xC | 24 | Name of pane |
| 0x24 | 8 | User data |
| 0x2C | 4 | X position (float) |
| 0x30 | 4 | Y position (float) |
| 0x34 | 4 | Z position (float) |
| 0x38 | 4 | X rotation (float) |
| 0x3C | 4 | Y rotation (float) |
| 0x40 | 4 | Z rotation (float) |
| 0x44 | 4 | X scale (float) |
| 0x48 | 4 | Y scale (float) |
| 0x4C | 4 | Width (float) |
| 0x50 | 4 | Height (float) |

The `pas1` section and `pae1` section are always empty. They mark the start and end of the children of the pane respectively. A `pas1` section must always be preceded by a pane section.

## Picture
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 84 | [Pane info](#pane) |
| 0x54 | | [Material info](#material-info) |

## Textbox
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 84 | [Pane info](#pane) |
| 0x54 | 2 | Length |
| 0x56 | 2 | Restrict length |
| 0x58 | 2 | Index into material list |
| 0x5A | 2 | Index into font list |
| 0x5C | 1 | Origin |
| 0x5D | 1 | Line alignment |
| 0x5E | 1 | Active shadows |
| 0x5F | 1 | Padding |
| 0x60 | 4 | Italic tilt (float) |
| 0x64 | 4 | Offset to string |
| 0x68 | 4 | Top color |
| 0x6C | 4 | Bottom color |
| 0x70 | 4 | Font size X (float) |
| 0x74 | 4 | Font size Y (float) |
| 0x78 | 4 | Character size (float) |
| 0x7C | 4 | Line size (float) |
| 0x80 | 4 | Offset to textbox name |
| 0x84 | 4 | Shadow offset X (float) |
| 0x88 | 4 | Shadow offset Y (float) |
| 0x8C | 4 | Shadow scale X (float) |
| 0x90 | 4 | Shadow scale Y (float) |
| 0x94 | 4 | Shadow color top (float) |
| 0x98 | 4 | Shadow color bottom (float) |
| 0x9C | 4 | Shadow italic tilt (float) |
| 0xA0 | | Unknown |

## Window
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 84 | [Pane info](#pane) |
| 0x54 | 4 * 4 | Rectangle (floats) |
| 0x64 | 1 | Frame data count |
| 0x65 | 1 | Flags |
| 0x66 | 2 | Padding |
| 0x68 | 4 | Offset to [material info](#material-info) |
| 0x6C | 4 | Unknown offset |

## Material Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Top left color |
| 0x4 | 4 | Top right color |
| 0x8 | 4 | Bottom left color |
| 0xC | 4 | Bottom right color |
| 0x10 | 2 | Index into `mat1` section |
| 0x12 | 2 | Number of texture coordinate sets (N) |
| 0x14 | 32 * N | Texture coordinate sets |

Every texture coordinate set is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Top left |
| 0x8 | 8 | Top right |
| 0x10 | 8 | Bottom left |
| 0x18 | 8 | Bottom right |

Every corner is stored as follows:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | X coordinate (float) |
| 0x4 | 4 | Y coordinate (float) |
