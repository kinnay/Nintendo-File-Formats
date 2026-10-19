## [Switch](../../formats.md#nintendo-switch) > System Save Data

On the Nintendo Switch, system save data is organized into archives, which are identified by a hardcoded number (data id).

The following save data archives are documented here:

| ID | Module | Description |
| --- | --- | --- |
| [`8000000000000010`](systemsave/8000000000000010.md) | `account` | User profiles |
| [`8000000000000011`](systemsave/8000000000000011.md) | `account` | ID generation |
| [`8000000000000040`](systemsave/8000000000000040.md) | `ns` | Application records |
| [`8000000000000043`](systemsave/8000000000000043.md) | `ns` | SD card encryption |
| [`80000000000000E1`](systemsave/80000000000000e1.md) | `es` | Common tickets |
| [`80000000000000E2`](systemsave/80000000000000e2.md) | `es` | Personalized tickets |
| [`8000000000000110`](systemsave/8000000000000110.md) | `npns` | Push notification service storage |
| [`8000000000000210`](systemsave/8000000000000210.md) | `account` | DAuth / AAuth token cache |

For other archives, a brief description can be found on the [SwitchBrew wiki](https://switchbrew.org/wiki/SystemSaveData).
