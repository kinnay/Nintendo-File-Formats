## [AGL](/formats.md#agl) > Graphics Parameters (PMAA)

A PMAA file contain a parameter tree for various graphical effects. This page describes version 1 of the file format.

* [Header](#header)
* [Parameter tree](#parameter-tree)
* [Known effect types](#known-effect-types)
* [Notes](#notes)

## Header
In little endian mode, the whole header is swapped (even the magic number).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number (`PMAA`) |
| 0x4 | 4 | Version number |
| 0x8 | 4 | Endianness (0=big, 1=little) |
| 0xC | 4 | Filesize |
| 0x10 | 4 | Effect type version |
| 0x14 | 4 | Length of effect type (including null terminator) |
| 0x18 | | Null terminated effect type |

In some games, the parameter tree comes directly after the effect type, even if the effect type causes it to be misaligned. In other games, the length of the effect type is always a multiple of 4.

## Parameter Tree
The parameter tree starts with a [list](#parameter-list) whose name is `param_root`. Its children depend on the effect type and version that are specified in the [header](#header).

### Parameter List
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (including child lists and objects) |
| 0x4 | 4 | Name hash |
| 0x8 | 4 | Number of child lists |
| 0xC | 4 | Number of child objects |
| 0x10 | | Child lists |
| | | Child objects |

### Parameter Object
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size (including entries) |
| 0x4 | 4 | Number of parameters |
| 0x8 | 4 | Name hash |
| 0xC | 4 | Type name hash |
| 0x10 | | Parameters |

### Parameter
The size includes both the header and data, so it is the size of the data plus 12.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size |
| 0x4 | 4 | Type |
| 0x8 | 4 | Name hash |
| 0xC | | Data |

#### Parameter Types
| ID | Size | Name | Description |
| --- | --- | --- | --- |
| 0 | 1 | bool | bool |
| 1 | 4 | f32 | float |
| 2 | 4 | int | int |
| 3 | 8 | vec2 | sead::Vector2&lt;float&gt; |
| 4 | 12 | vec3 | sead::Vector3&lt;float&gt; |
| 5 | 16 | vec4 | sead::Vector4&lt;float&gt; |
| 6 | 16 | color | sead::Color4f |
| 7 | | [string32](#string-types) | sead::FixedSafeString&lt;32&gt; |
| 8 | | [string64](#string-types) | sead::FixedSafeString&lt;64&gt; |
| 9 | 128 | [curve1](#curve-types) | |
| 10 | 256 | [curve2](#curve-types) | |
| 11 | 384 | [curve3](#curve-types) | |
| 12 | 512 | [curve4](#curve-types) | |
| 13 | | buffer_int | |
| 14 | | buffer_float | |
| 15 | | [string256](#string-types) | sead::FixedSafeString&lt;256&gt; |
| 16 | 16 | quat | sead::Quat&lt;float&gt; |
| 17 | 4 | u32 | unsigned int |
| 18 | | buffer_u32 |
| 19 | | buffer_binary |
| 20 | | stringRef | sead::SafeStringBase<char> |

#### String Types
These are null-terminated strings with a given maximum length. In some games, all strings use the maximum number of bytes (see [notes](#notes)). In other games, the strings use only the necessary number of bytes, even if this causes the rest of the file to be misaligned.

#### Curve Types
A curve contains two 32-bit integers, followed by 30 floats. The first integer specifies the number of data points of the curve (at most 30). The second integer specifies the curve type (see below).

The types curve2, curve3 and curve4 are the same as curve1, except that they store multiple independent curves behind each other.

| ID | Type |
| --- | --- |
| 0 | Linear |
| 1 | Hermit |
| 2 | Step |
| 3 | Sin |
| 4 | Cos |
| 5 | SinPow2 |
| 6 | Linear2D |
| 7 | Hermit2D |
| 8 | Step2D |
| 9 | NonuniformSpline |
| 10 | Hermit2DSmooth |

## Known Effect Types
Most effect types are defined by the agl library itself, but games and libraries can also define custom effect types.

The following effect types are defined by the agl library:

| Type | Class |
| --- | --- |
| aglNmdw | `agl::fx::NormalDrawer` |
| aglatex | `agl::pfx::AutoExposure` |
| aglblm | `agl::pfx::Bloom` |
| aglcam | `Camera` |
| aglccr | `agl::pfx::ColorCorrection` |
| aglclwd | `agl::fx::Cloud` |
| aglcube | `agl::env::CubeMapMgr` |
| agldecd | `agl::fx::DecalDrawer` |
| agldof | `agl::env::DepthOfField` |
| aglenv | `agl::env::EnvObMgr` |
| aglenvset | `agl::env::EnvObjSetMgr` |
| aglfila | `agl::pfx::FilterAA` |
| aglflr | `agl::pfx::FlareFilter` |
| aglglr | `agl::pfx::GlareFilter` |
| agllmap | `agl::lght::LightMapMgr` |
| agllref | `agl::lght::LocalReflection` |
| aglmf | `agl::utl::MultiFilter` |
| aglofx | `agl::fx::OccludedEffectMgr` |
| aglprojsdw | `agl::sdw::ProjectionShadow` |
| aglsdw | `agl::sdw::DepthShadow` |
| aglshpp | `agl::sdw::ShadowPrePass` |
| aglssao | `agl::sdw::SSAO` |
| aglvolm | `agl::fx::VolumeMask` |
| ksky | `agl::pfx::Sky` |
| pref | `agl::lght::PlanarReflection` |

The following effect types are defined by the gsys library:

| Type | Class |
| --- | --- |
| gapkginfo | `gsys::ApplicationPackageInfo` |
| genv | `gsys::ModelSceneEnv` |
| glght | `gsys::ModelSceneGI` |
| glpbd | `gsys::LightProbeMgr::ProbeVolumeMgr` |
| glpbm | `gsys::LightProbeMgr` |
| gmsconf | `gsys::ModelSceneConfigList` |
| gsdw | `gsys::ModelSceneShadow` |
| gsysdclao | `gsys::ModelDecalAoObject` |
| ptclconf | `gsys::ParticleConfig` |

The following effect types are defined by the LunchPack framework:

| Type | Class |
| --- | --- |
| lpdcam | `Lp::Sys::DbgCamera` |

The following effect types are defined by Splatoon 2:

| Type | Class |
| --- | --- |
| sms | `Cmn::SealShadow` |

## Notes
A PMAA file contains null-terminated strings with a fixed size. It is possible that the size is larger than the length of the string. In newer games, the remaining space is simply filled with null bytes. However, in old games, it is filled with `0xCD` bytes, except for the last byte, which is set to 0. This is presumably uninitialized memory in the tool that generated the PMAA files.