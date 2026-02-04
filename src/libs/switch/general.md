
## [Switch](../../formats.md#nintendo-switch) > General

This page describes structures that are defined by the Nintendo Switch SDK that may be seen in multiple file formats.

* [`nn::time::SteadyClockTimePoint`](#nntimesteadyclocktimepoint)
* [`nn::util::Uuid`](#nnutiluuid)

## `nn::time::SteadyClockTimePoint`

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | Value in seconds |
| 0x8 | 16 | [Source id (UUID)](#nnutiluuid) |

## `nn::util::Uuid`
This structure represents a UUID with no particular version.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | UUID bytes |
