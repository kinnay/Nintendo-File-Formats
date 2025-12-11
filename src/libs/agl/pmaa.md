## [AGL](../../formats.md#agl) > Graphics Parameters (PMAA)

A PMAA file contains a parameter tree for various graphical effects. The PMAA file format has many different file extensions, such as `.baglenv`, `.bagldof` and `.bagllmap`.

There are two versions of this file format and because these are quite different the documentation has been split up into two separate pages:

* [V1](pmaa/v1.md)
* [V2](pmaa/v2.md)

The remainder of this page explains common concepts of the PMAA format:

* [Overview](#overview)
* [Effect types](#effect-types)
* [Value types](#value-types)

## Overview
Every parameter tree starts with a parameter list whose name is `param_root`. Its children depend on the effect type and version that are specified in the header.

* Every parameter list has a name and may contain other parameter lists and parameter objects.
* Every parameter object has a name and type and contains a specific set of parameter values.
* Every parameter value has a name, [type](#value-types) and value.

While every parameter list, object and value has a name, the PMAA file unfortunately contains only contains their CRC32 hashes. The only way to recover the actual names is by reverse engineering or guessing.

## Effect Types
This section lists the effect types that are currently known. Although the agl library already implements various different types, games may also implement types of their own.

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

## Value Types
The following value types are found in PMAA file:

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
| 20 | | stringRef | sead::SafeStringBase&lt;char&gt; |

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

## Notes
A PMAA file contains null-terminated strings with a fixed size. It is possible that the size is larger than the length of the string. In newer games, the remaining space is simply filled with null bytes. However, in old games, it is filled with `0xCD` bytes, except for the last byte, which is set to 0. This is probably uninitialized memory in the tool that generated the PMAA files.
