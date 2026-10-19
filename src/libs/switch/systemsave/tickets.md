## [Switch](../../formats.md#nintendo-switch) > [System Save](../systemsave.md) > Tickets

This page describes the content of the following save data archives:
* `80000000000000E1`, which is mounted to `escommon:/` by the `es` process.
* `80000000000000E2`, which is mounted to `espersonalized:/` by the `es` process.

Both archives have the same structure. The difference is that personalized tickets are bound to a specific device, using device-specific encryption keys. Common tickets are not bound to a specific device.

The following files can be found in the archive:

* `ticket.bin`
* [`ticket_list.bin`](#ticket_listbin)
* `version.bin`

## ticket_list.bin
This file contains 32 bytes per ticket. Each entry has the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | Rights id |
| 0x10 | 8 | Ticket id |
| 0x18 | 4 | Account id |
| 0x1C | 4 | Unknown |

For common tickets, the ticket id and account id are 0.

An end-of-file record is written to the file behind the last ticket entry. The end-of-file record has the rights id, ticket id and account id set ot -1. Further entries in the file have all fields set to 0.

The total size of the `ticket_list.bin` file is always `0x7D000` bytes for common tickets, and `0x1F4000` bytes for personalized tickets.
