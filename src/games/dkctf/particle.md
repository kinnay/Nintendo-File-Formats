## [DKC:TF](../../formats.md#dkctf) > Particle File (GENP/SWSH/XFRM)

Meta data: [NParticleFormat::SMetaData](#nparticleformatsmetadata)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | Form descriptor (GENP/SWSH/XFRM) |

## GENP/SWSH/XFRM Form
Version: 15

| Type | Description |
| --- | --- |
| [CChunkDescriptor] | DESC chunk (particle generator description) |

The chunk contains a parse tree. Every element starts with a [CFourCC] that indicates its type, followed by type-specific fields. Depending on the file type, the root element is either a [GPSM](#gpsm-node), SWSH or XFRM node.

## GPSM Node
This element contains an arbitrary number of elements of the following types.

| Class id | Description |
| --- | --- |
| `ADV1` | |
| `ADV2` | |
| `ADV3` | |
| `ADV4` | |
| `ADV5` | |
| `ADV6` | |
| `ADV7` | |
| `ADV8` | |
| `ADV9` | |
| `ALSC` | |
| `CAV0` | |
| `CAV1` | |
| `CAV2` | |
| `CAV3` | |
| `CIND` | |
| `COLR` | |
| `DBIS` | |
| `DBPS` | |
| `DBSO` | |
| `DDIT` | |
| `DEFX` | |
| `DFLG` | |
| `DFOG` | |
| `EMTE` | |
| `EMTR` | |
| `EMTU` | |
| `FXBI` | |
| `FXBM` | |
| `FXBO` | |
| `FXBR` | |
| `FXBT` | |
| `GRTE` | |
| `IAV0` | |
| `IAV1` | |
| `IAV2` | |
| `IAV3` | |
| `INDM` | |
| `INDP` | |
| `INTP` | |
| `INTR` | |
| `INTS` | |
| `INTT` | |
| `ISTR` | |
| `ISVF` | |
| `ITPE` | |
| `IVSE` | |
| `KSSM` | |
| `LCLR` | |
| `LDIR` | |
| `LFOR` | |
| `LFOT` | |
| `LINT` | |
| `LIT_` | |
| `LOFF` | |
| `LSLA` | |
| `LSNM` | |
| `LTME` | |
| `LTYP` | |
| `MAXP` | |
| `NTIK` | |
| `ONET` | |
| `ORNT` | |
| `ORTC` | |
| `PBDM` | |
| `PMDL` | |
| `PMLT` | |
| `PMOO` | |
| `PMOP` | |
| `PMOV` | |
| `PMPV` | |
| `PMRB` | |
| `PMRQ` | |
| `PMRT` | |
| `PMSC` | |
| `PMUS` | |
| `PSLT` | |
| `PSTP` | |
| `PSTS` | |
| `PSWT` | |
| `PWGT` | |
| `RAV0` | |
| `RAV1` | |
| `RDOP` | |
| `ROTA` | |
| `RSV0` | |
| `RSV1` | |
| `RSV2` | |
| `RSV3` | |
| `SAXS` | |
| `SBIS` | |
| `SCNV` | |
| `SCTR` | |
| `SCX0` | |
| `SEED` | |
| `SIZE` | |
| `SORT` | |
| `SPCL` | |
| `SSZE` | |
| `SPWR` | |
| `SPWS` | |
| `SPWT` | |
| `SSWT` | |
| `SSZE` | |
| `SVC0` | |
| `SVC1` | |
| `SVI0` | |
| `SVI1` | |
| `SVR0` | |
| `SVR1` | |
| `SVR2` | |
| `SVR3` | |
| `SVR4` | |
| `SVV0` | |
| `SVV1` | |
| `SVV2` | |
| `SVV3` | |
| `SVV4` | |
| `SYSR` | |
| `SYSS` | |
| `SYST` | |
| `TEMR` | |
| `TEMT` | |
| `TEXR` | |
| `TIND` | |
| `TNML` | |
| `TSPH` | |
| `UDLS` | |
| `UGFP` | |
| `VAV1` | |
| `VAV2` | |
| `VAV3` | |
| `VAV4` | |
| `VEL1` | |
| `VEL2` | |
| `VEL3` | |
| `VEL4` | |
| `VGD1` | |
| `VGD2` | |
| `VGD3` | |
| `VGD4` | |
| `VMD1` | |
| `VMD2` | |
| `VMD3` | |
| `VMD4` | |
| `VMPC` | |
| `VSPC` | |
| `WSTP` | |
| `XFMD` | |
| `XTAD` | |
| `ZBUF` | |
| `_END` | |

## Bool Element
Note: in some cases, only `CNST` is accepted.

| Class id | Description |
| --- | --- |
| `CNST` | [Constant](#cbeconstant-cnst) |
| `EQUL` | [Equality check](#cberealequal-equl) |
| `LTHN` | [Less than check](#cbereallessthan-lthn) |
| `MIRR` | [Is mirrored](#cbemirrored-mirr) |
| `NEXT` | |
| `NORM` | [Is vector normalizable](#cbenormalizeable-norm) |
| `P50H` | [Are we 50 Hz PAL](#cbearewepal50) |
| `PEXT` | |
| `VEXT` | |

### CBEConstant (`CNST`)
This element defines a constant.

| Type | Description |
| --- | --- |
| Bool | Value |

### CBERealEqual (`EQUL`)
This element performs an equality check.

| Type | Description |
| --- | --- |
| [Real element] | LHS |
| [Real element] | RHS |

### CBERealLessThan (`LTHN`)
This element performs a less-than check.

| Type | Description |
| --- | --- |
| [Real element] | LHS |
| [Real element] | RHS |

### CBEMirrored (`MIRR`)
The value of this element is true if the mirror is enabled.

### CBENormalizeable (`NORM`)
The value of this element is true if the given vector is normalizable.

| Type | Description |
| --- | --- |
| [Vector element] | Vector |

### CBEAreWePal50 (`P50H`)
The value of this element is true if 50 Hz PAL is enabled.

## Int Element
| Class id | Description |
| --- | --- |
| `ADD_` | Addition |
| `BNID` | |
| `CHAN` | |
| `CLMP` | Clamp |
| `CNST` | [Constant](#cieconstant-cnst) |
| `DETH` | |
| `DIVD` | |
| `GAPC` | |
| `GEMT` | |
| `GTCP` | |
| `ILPT` | |
| `IMPL` | |
| `IRND` | |
| `ISWT` | |
| `KEYE` | |
| `KEYF` | |
| `KEYP` | |
| `KPIN` | |
| `MODU` | |
| `MULT` | |
| `PAP0` | |
| `PAP1` | |
| `PAP2` | |
| `PAP3` | |
| `PCRT` | |
| `PDET` | |
| `PSA0` | |
| `PSA1` | |
| `PSI0` | |
| `PSI1` | |
| `PULS` | |
| `RAND` | |
| `RTOI` | |
| `SUB_` | |
| `TSCL` | |

### CIEConstant (`CNST`)
| Type | Description |
| --- | --- |
| Uint32 | Value |

## Real Element
| Class id | Description |
| --- | --- |
| `ADD_` | Addition |
| `CEQL` | |
| `CEXT` | |
| `CHAN` | |
| `CLMP` | |
| `CLTN` | |
| `CNST` | [Constant](#creconstant-cnst) |
| `CREL` | |
| `CRNG` | |
| `DIVD` | |
| `DOTP` | Dot product |
| `GTCA` | |
| `GTCB` | |
| `GTCG` | |
| `GTCP` | |
| `GTCR` | |
| `IRND` | |
| `ISWT` | |
| `ITRL` | |
| `KEYE` | |
| `KEYF` | |
| `KEYP` | |
| `KPIN` | |
| `LFTW` | |
| `MAXV` | |
| `MINV` | |
| `MULT` | Multiplication |
| `MULV` | |
| `NEXT` | |
| `OCSP` | |
| `PAP1` | |
| `PAP2` | |
| `PAP3` | |
| `PAP4` | |
| `PAP5` | |
| `PAP6` | |
| `PAP7` | |
| `PAP8` | |
| `PAP9` | |
| `PEXT` | |
| `PNO1` | |
| `PNO2` | |
| `PNO3` | |
| `PNO4` | |
| `PRLW` | |
| `PRN1` | |
| `PRN2` | |
| `PRN3` | |
| `PRN4` | |
| `PSA0` | |
| `PSA1` | |
| `PSA2` | |
| `PSLL` | |
| `PSSZ` | |
| `PULS` | |
| `RAND` | |
| `RECP` | |
| `RLPT` | |
| `SCAL` | |
| `SINE` | |
| `SUB_` | Subtraction |
| `TOCS` | |
| `VMAG` | |
| `VXTR` | |
| `VYTR` | |
| `VZTR` | |

### CREConstant (`CNST`)
| Type | Description |
| --- | --- |
| Float | Value |

## Vector Element
| Class id | Description |
| --- | --- |
| `ADD_` | |
| `AEXT` | |
| `ANGC` | |
| `BNPS` | |
| `BNSC` | |
| `CCLU` | |
| `CHAN` | |
| `CIRC` | |
| `CMPS` | |
| `CNST` | Constant |
| `CONE` | |
| `CRSS` | |
| `CTVC` | |
| `CVEC` | |
| `EXTS` | |
| `EXTT` | |
| `INTS` | |
| `INTT` | |
| `IRTV` | |
| `ISWT` | |
| `KEYE` | |
| `KEYF` | |
| `KEYP` | |
| `KPIN` | |
| `MULT` | |
| `NEXT` | |
| `NONE` | |
| `NORM` | |
| `ORDR` | |
| `PAP1` | |
| `PAP2` | |
| `PAP3` | |
| `PAP4` | |
| `PEXT` | |
| `PLCO` | |
| `PLOC` | |
| `PNCV` | |
| `PSA0` | |
| `PSA1` | |
| `PSA2` | |
| `PSA3` | |
| `PSA4` | |
| `PSOF` | |
| `PSOR` | |
| `PSOU` | |
| `PSTR` | |
| `PULS` | |
| `PVEL` | |
| `RNDV` | |
| `ROTV` | |
| `RTOV` | |
| `SCLE` | |
| `SLOC` | |
| `SPNT` | |
| `SPSS` | |
| `SUB_` | |
| `VEXT` | |

## NParticleFormat::SMetaData
| Type | Description |
| --- | --- |
| [List]&lt;[CObjectTag]&gt; | Texture references |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CAABox]: types.md#caabox
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CObjectTag]: types.md#cobjecttag
[CVector4i]: types.md#cvector4i
[CColor4f]: types.md#ccolor4f
[CString]: types.md#cstring
[String]: types.md#string
[List]: types.md#list
[Map]: types.md#map

[Bool element]: #bool-element
[Real element]: #real-element
[Vector element]: #vector-element