## [Switch](../../formats.md#nintendo-switch) > NPDM Files

The `main.npdm` file defines the permissions for a title, such as which system calls and IPC services it is allowed to use. It is stored in the `exefs` of the title.

NPDM files are encoded in little-endian byte order.

## File Format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`META`) |
| 0x4 | 4 | [Signature flags](#signature-flags) |
| 0x8 | 4 | Always 0 |
| 0xC | 1 | [Address space flags](#address-space-flags) |
| 0xD | 1 | [Security flags](#security-flags) |
| 0xE | 1 | Main thread priority |
| 0xF | 1 | Main thread core number |
| 0x10 | 4 | Unknown |
| 0x14 | 4 | System resource size |
| 0x18 | 4 | Version |
| 0x1C | 4 | Main thread stack size |
| 0x20 | 16 | Application name |
| 0x30 | 16 | Product code (always empty?)
| 0x40 | 48 | Padding |
| 0x70 | 4 | Offset to [`ACI0` section](#aci0-section) (absolute) |
| 0x74 | 4 | Size of [`ACI0` section](#aci0-section) |
| 0x78 | 4 | Offset to [`ACID` section](#acid-section) (absolute) |
| 0x7C | 4 | Size of [`ACID` section](#acid-section) |
| 0x80 | | [`ACID` section](#acid-section) |
| | | [`ACI0` section](#aci0-section) |

### Signature Flags
| Flag | Description |
| --- | --- |
| 1 | Use alternative public key |

When the alternative public key flag is set, a different [public key](#acid-signature-keys) is used to verify the RSA signature in the [ACID section](#acid-section). This flag does not seem to be used in games.

### Address Space Flags
| Mask | Description |
| --- | --- |
| 0x01 | Is 64 bit |
| 0x0E | [Address space type](#address-space-type) |
| 0x10 | `OptimizeMemoryAllocation` |
| 0x20 | `DisableDeviceAddressSpaceMerge` |
| 0x40 | `EnableAddressSanitizer` |
| 0x80 | Must be 0 |

#### Address Space Type
| Value | Description |
| --- | --- |
| 0 | `AddressSpace32Bit` |
| 1 | `AddressSpace64Bit36` |
| 2 | `AddressSpace32BitNoReserved` |
| 3 | `AddressSpace64Bit39` |
| 4 | `AddressSpace64Bit42` |

## ACID Section
The ACID section starts with an RSA signature that is calculated over the remaining part of the ACID section (over the NCA public key and ACID payload). The public key that is used to validate the signature is [described below](#acid-signature-keys). The signature algorithm is standard RSASSA-PSS with SHA256.

The ACID section defines the maximum permissions that may be requested by the [ACI0 section](#aci0-section).

Nintendo Switch:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 256 | RSA signature over remaining part of ACID section |
| 0x100 | 256 | NCA public key |
| 0x200 | | [ACID payload](#acid-payload)

Nintendo Switch 2:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 384 | RSA signature over remaining part of ACID section |
| 0x180 | 384 | NCA public key |
| 0x300 | | [ACID payload](#acid-payload) |

### ACID Payload
The offsets here are relative to the start of the [ACID section](#acid-section).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`ACID`) |
| 0x4 | 4 | Total size of ACID section, including NCA public key but excluding RSA signature |
| 0x8 | 4 | Always 0 |
| 0xC | 4 | [Flags](#acid-flags) |
| 0x10 | 8 | Minimum title id |
| 0x18 | 8 | Maximum title id |
| 0x20 | 4 | Offset to file access control limits |
| 0x24 | 4 | Size of file access control limits |
| 0x28 | 4 | Offset to service access control limits |
| 0x2C | 4 | Size of service access control limits |
| 0x30 | 4 | Offset to kernel capability limits |
| 0x34 | 4 | Size of kernel capabilitty limits |
| 0x38 | 8 | Always 0 |
| 0x40 | | [File access control limits](#file-access-control-limits) |
| | | [Service accesss control limits](#service-access-controls) |
| | | [Kernel capability limits](#kernel-capabilities) |

#### ACID Flags
| Mask | Description |
| --- | --- |
| 0x01 | Is production |
| 0x02 | `UnqualifiedApproval` |
| 0x3F | [Memory region](#memory-region) |
| 0x40 | Unknown |
| 0x80 | `LoadBrowserCoreDll` |

#### Memory Region
| Value | Description |
| --- | --- |
| 0 | Application |
| 1 | Applet |
| 2 | SecureSystem |
| 3 | NonSecureSystem |

### ACID Signature Keys
This section describes the public keys that are used to verify the RSA signature in the [ACID section](#acid-section). The public exponent is always 65537. The public modulus depends on the signature key revision that is specified in the [header](#file-format), and whether the hardware is a development or production unit.

Production unit, standard key:

```
27997716596311541054315493530229540803505084731323289243013132616045273369204979312211842998785955093203642059372921527880191651695936461591719352645690869117826992797976340551708660832480102892592969563432180807173240490853739571897126628512565666877754127130023316366790781882931483296497257762639972134330053161888461055239242400438683135131231961598648922750627358068491266046679946591608055821848346257813744678527534516494532765431671669636848256131421225091796654655528106219358050699832607089542146847809895402945211973474212057977624801451696506640815762543577831097231381510003892546332593417075037872399101
```

Production unit, alternative key:

```
29244951347492957548716520011745572453259893268825204698245515963623102396947022752845081010438742714558376702167125579272860040720361779531287335336053587055367687644218533724424333517655598330814738421911495311853375338447930859847119376614829441486819820275862764726829681141461622163253253883091014864460735900835180315947002629401281228024683244517882388041664972065074267396589021062720577691777553507503160683047100360962389741341844600150431287628683863404612731059592456358708511465323179603995138219647750363460097532365037819227526390603887652696823972274959181993527602554045727617068761710519851231955203
```

Development unit, standard key:

```
27040958154750948586911961271681771310305446650335602917489851512067658899176520268361986720704370970874673107950888378219339796280610913401914597664670705892844052067365292933141422607936863528846762485637105996325019265988529401236477356358585829094893904836261483917584986843393621171971559475745166845940193464274907095508035505843308532549159193971869950308732327152958605109273824569884440349831826726529554603852364406505323385110545748840535021591394665604594181729393294606915762139617049724104742966403692733616975360161919330055497457866406557391689189631268077424517252735578306916879134820852671147444329
```

Development unit, alternative key:

```
23814371002902656965440080134421761115206477806703422383473416260825878340642860401068897582575058601946371951546405630764981623594327434003580957693798714699565491287764864124080852856000126359450182158238309131003312031024266851295611566174311510465342603415510978858118055736761976136244244250361129237774157136359031255821304074117244385565433127930836150809025587201021666801824662293626591400668945102195159436225710623079833889274071908300366088224423055931387311897402335017003578919067348341029865373492485811022003941421914190773365561921813580731430842481384882235255522669642476762454277543128009969906283
```

## ACI0 Section
This section defines the actual permissions that are requested for the title. There is no RSA signature in this section, but the requested permissions must be a subset of the permissions that are defined in the [ACID section](#acid-section).

The offsets in this section are relative to the start of the ACI0 section.

The ACI0 section is aligned to 16 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`ACI0`) |
| 0x4 | 12 | Always 0 |
| 0x10 | 8 | Title id |
| 0x18 | 8 | Always 0 |
| 0x20 | 4 | Offset to file access controls |
| 0x24 | 4 | Size of file access controls |
| 0x28 | 4 | Offset to service access controls |
| 0x2C | 4 | Size of service access controls |
| 0x30 | 4 | Offset to kernel capabilities |
| 0x34 | 4 | Size of kernel capabilitiies |
| 0x38 | 8 | Always 0 |
| 0x40 | | [File access controls](#file-access-controls) |
| | | [Service accesss controls](#service-access-controls) |
| | | [Kernel capabilities](#kernel-capabilities) |

## File Access Control Limits
This section is part of the [ACID section](#acid-section) and describes the maximum filesystem permissions that may be requested by the [ACI0 section](#aci0-section). It is aligned to 16 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Version number (always 1) |
| 0x1 | 1 | Number of content owner ids (X) |
| 0x2 | 1 | Number of save data owner ids (Y) |
| 0x3 | 1 | Padding |
| 0x4 | 8 | [Filesystem permissions](#filesystem-permissions) |
| 0xC | 8 | Minimum content owner id |
| 0x14 | 8 | Maximum content owner id |
| 0x1C | 8 | Minimum save data owner id |
| 0x24 | 8 | Maximum save data owner id |
| 0x2C | 8 * X | Content owner ids |
| | 8 * Y | Save data owner ids |

## File Access Controls
The section is part of the [ACI0 section](#aci0-section) and describes the actual filesystem permissions that are requested by the application. It is aligned to 16 bytes.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Version number (always 1) |
| 0x1 | 3 | Padding |
| 0x4 | 8 | [Filesystem permissions](#filesystem-permissions) |
| 0xC | 4 | Offset to content owner info |
| 0x10 | 4 | Size of content owner info |
| 0x14 | 4 | Offset to save data owner info |
| 0x18 | 4 | Size of save data owner info |
| 0x1C | 4 | [Content owner info](#content-owner-info) |
| | | [Save data owner info](#save-data-owner-info) |

### Content Owner Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of content owner ids (N) |
| 0x4 | 8 * N | Content owner ids |

### Save Data Owner Info
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Number of save data owner ids (N) |
| 0x4 | N | Permissions flags per save data owner id (1 = Read, 2 = Write) |
| | 8 * N | Save data owner ids |

## Filesystem Permissions
| Bit | Description |
| --- | --- |
| 0 | ApplicationInfo |
| 1 | BootModeControl |
| 2 | Calibration |
| 3 | SystemSaveData |
| 4 | GameCard |
| 5 | SaveDataBackUp |
| 6 | SaveDataManagement |
| 7 | BisAllRaw |
| 8 | GameCardRaw |
| 9 | GameCardPrivate |
| 10 | SetTime |
| 11 | ContentManager |
| 12 | ImageManager |
| 13 | CreateSaveData |
| 14 | SystemSaveDataManagement |
| 15 | BisFileSystem |
| 16 | SystemUpdate |
| 17 | SaveDataMeta |
| 18 | DeviceSaveData |
| 19 | SettingsControl |
| 20 | SystemData |
| 21 | SdCard |
| 22 | Host |
| 23 | FillBis |
| 24 | CorruptSaveData |
| 25 | SaveDataForDebug |
| 26 | FormatSdCard |
| 27 | GetRightsId |
| 28 | RegisterExternalKey |
| 29 | RegisterUpdatePartition |
| 30 | SaveDataTransfer |
| 31 | DeviceDetection |
| 32 | AccessFailureResolution |
| 33 | SaveDataTransferVersion2 |
| 34 | RegisterProgramIndexMapInfo |
| 35 | CreateOwnSaveData |
| 36 | MoveCacheStorage |
| 37 | DeviceTreeBlob |
| 38 | NotifyErrorContextServiceReady |
| 39 | CalibrationSystemData |
| 40 | CalibrationLog |
| 41 | StorageSecure |
| 42 | StorageControl |
| 43 | GameCardReport |
| 44 | MarkBeforeEraseBis |
| 45 | HtmlViewer |
| 46 | ApplicationSaveDataBackUp |
| 47 | StreamPlaySaveData |
| 48 | TemporaryDirectory |
| 62 | Debug |
| 63 | FullPermission |

## Service Access Controls
This section describes IPC service permissions. It is aligned to 16 bytes.

The section contains one entry for every IPC service that the program is allowed to host (`is_server`) or access. Every entry has the following structure:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | `(len(name) - 1) \| (is_server << 7)` |
| 0x1 | | Name |

## Kernel Capabilities
This section describes system call permissions. It is aligned to 16 bytes.

The section contains an array of 32-bit words. In each word, the number of least significant bits that are set define the kernel capability type. The remaining bits contain values that depend on the kernel capability type. This means that, the higher the kernel capability type, the less bits are available to store parameters.

Some types of kernel capabilities, such as the enabled system calls, may have multiple entries in the array.

| Type | Description |
| --- | --- |
| 3 | [Thread info](#thread-info) |
| 4 | [Enabled system calls](#enabled-system-calls) |
| 6 | Memory map |
| 7 | I/O memory map |
| 10 | Memory region map |
| 11 | Enabled interrupts |
| 13 | Miscellaneous values |
| 14 | Kernel version |
| 15 | Handle table size |
| 16 | Miscellaneous flags |

### Thread Info
| Bits | Description |
| --- | --- |
| 4 - 9 | Minimum thread priority |
| 10 - 15 | Maximum thread priority |
| 16 - 23 | Minimum core number |
| 24 - 31 | Maximum core number |

### Enabled System Calls
This type of entry can occur multiple times. Each entry describes which system calls are permitted for the application, for a specific range of system calls.

Every bit in the mask represents one system call. The least significant bit represents the lowest system call id in the group. The most significant bit represents the highest system call id in the group. If a bit is set, the system call may be used by the application.

The group id defines the range of system call ids that are specified by the entry. If the group id has value `n`, this entry affects system call id `n * 24` up to `n * 24 + 23`.

| Bits | Description |
| --- | --- |
| 5 - 28 | Enabled system call mask |
| 29 - 31 | Group id |

## References
* [https://switchbrew.org/wiki/NPDM](https://switchbrew.org/wiki/NPDM)
