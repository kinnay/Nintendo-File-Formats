## [DKC:TF](/formats.md#dkctf) > Structs

Many structs have a name that starts with SLdr. The code that parses these structs was probably automatically generated from a C++ header or data definition language. Unfortunately, only the CRC32 hash of each field name is stored in the file, and it's hard to infer the name of a field from its hash. Not all fields of a struct must be stored in the file: if a field is not present a default value is used.

Every struct is stored as follows:

| Type | Description |
| --- | --- |
| Uint16 | Number of fields |
| ... | Fields |

Every field is stored as follows:

| Type | Description |
| --- | --- |
| Uint32 | Name hash |
| Uint16 | Data size |
| ... | Data |

The remainder of this page documents the fields that are found in each structure.

### SLdrAABoxShapeData
| Field | Type | Description |
| --- | --- | --- |
| `A268A4F4` | [CVector3f] | field_0 |
| `A8692FA4` | [CVector3f] | field_C |
| `6C0A4979` | Bool | field_18 |

### SLdrAchievement
| Field | Type | Description |
| --- | --- | --- |
| `E7AE6548` | [enum_100625f8](#enum_100625f8) | field_0 |

### SLdrAcousticBounds
| Field | Type | Description |
| --- | --- | --- |
| `18B98B84` | [enum_100980c4](#enum_100980c4) | field_0 |
| `2B030735` | [CVector3f] | field_4 |

### SLdrActionDetector
| Field | Type | Description |
| --- | --- | --- |
| `BE157541` | [CObjectId] | field_0 |
| `509E34B7` | Bool | field_10 |
| `88B3E972` | [List]&lt;[SLdrActionDetectorBehavior](#sldractiondetectorbehavior)&gt; | field_14 |
| `B190E9B8` | [List]&lt;[Property]&gt; | field_20 |

### SLdrActionDetectorBehavior
| Field | Type | Description |
| --- | --- | --- |
| `736FC383` | [enum_10062788](#enum_10062788) | field_0 |
| `434D6190` | Bool | field_4 |
| `C864FF7F` | Bool | field_5 |
| `1407A535` | Bool | field_6 |
| `DE538529` | [String] | field_8 |
| `84C69EF1` | Bool | field_14 |
| `B61689FF` | Float | field_18 |
| `0F692AA0` | Float | field_1C |
| `DE9F3A30` | [CVector3f] | field_20 |
| `A14E71BF` | Bool | field_2C |
| `5AAA0533` | [CVector3f] | field_30 |
| `45A54BBE` | Float | field_3C |
| `0ADB4557` | Bool | field_40 |

### SLdrActorActionConditionalData
| Field | Type | Description |
| --- | --- | --- |
| `F5EFEA01` | Uint32 | field_0 |
| `C7781BBC` | Uint32 | field_4 |

### SLdrActorActionPlaylistConditional
| Field | Type | Description |
| --- | --- | --- |
| `69D9E1E7` | [List]&lt;[SLdrActorActionConditionalData](#sldractoractionconditionaldata)&gt; | field_0 |

### SLdrActorActionPlaylistSequential
| Field | Type | Description |
| --- | --- | --- |
| `C25E1A9F` | [List]&lt;Int32&gt; | field_0 |

### SLdrActorCollision
| Field | Type | Description |
| --- | --- | --- |
| `0BE9C304` | Bool | field_0 |
| `CD4203BE` | Bool | field_1 |
| `688CEE18` | Bool | field_2 |
| `EF21A029` | Bool | field_3 |
| `FB4FCB5B` | [CObjectId] | field_4 |
| `53378048` | [SLdrMaterialType](#sldrmaterialtype) | field_14 |
| `E1795FAA` | [CVector3f] | field_18 |
| `B59D9A19` | [CVector3f] | field_24 |
| `EFC31F5B` | [SLdrPlatformRiderPhysicsOptions](#sldrplatformriderphysicsoptions) | field_30 |

### SLdrActorInteraction
This struct does not have any fields

### SLdrActorKeyframe
| Field | Type | Description |
| --- | --- | --- |
| `03F651C0` | [CObjectId] | field_0 |
| `9EC52472` | Bool | field_10 |
| `8C00FE45` | Bool | field_11 |
| `984E7394` | Bool | field_12 |
| `7D5C2739` | [List]&lt;[SLdrActorKeyframeAnimationInfo](#sldractorkeyframeanimationinfo)&gt; | field_14 |

### SLdrActorKeyframeAnimationInfo
| Field | Type | Description |
| --- | --- | --- |
| `F66B7BEC` | [String] | field_0 |
| `6A372CC2` | Bool | field_C |
| `7BD79555` | Bool | field_D |
| `2D308F36` | Float | field_10 |
| `AC2C4D26` | Bool | field_14 |
| `E5D4D058` | Bool | field_15 |
| `B5C91DF2` | Bool | field_16 |
| `9AD8FB1E` | Bool | field_17 |
| `3ED58A63` | Float | field_18 |
| `421BDFDD` | Float | field_1C |
| `69B4A262` | Bool | field_20 |

### SLdrAdapterManager
This struct does not have any fields

### SLdrAdoptCameraStateBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `F95641FD` | Bool | field_0 |
| `29385874` | Bool | field_1 |
| `662B4358` | Bool | field_2 |
| `42621CCA` | Bool | field_3 |

### SLdrAdoptSplineOrientationSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `9FF94E86` | [CMayaSpline] | field_0 |
| `B7F6CE9C` | [CMayaSpline] | field_30 |
| `CBB3FA18` | Bool | field_60 |
| `4391BCB2` | Bool | field_61 |
| `3ADC9E04` | [CVector3f] | field_64 |

### SLdrAiNonDamagingSCAHandler
| Field | Type | Description |
| --- | --- | --- |
| `0530F9E0` | [CColor4f] | field_0 |

### SLdrAlternateDamageInfoData
| Field | Type | Description |
| --- | --- | --- |
| `B968B0DA` | [List]&lt;[SLdrDamageInfo](#sldrdamageinfo)&gt; | field_0 |

### SLdrAnimGridAxisTrackingData
| Field | Type | Description |
| --- | --- | --- |
| `FDD124E2` | Float | field_0 |
| `1F88A835` | Float | field_4 |
| `956DA9F0` | Float | field_8 |
| `76380701` | Float | field_C |
| `CE60899C` | Float | field_10 |

### SLdrAnimGridDriverTrackObject
| Field | Type | Description |
| --- | --- | --- |
| `31CEFE78` | Uint32 | field_0 |
| `C210DE18` | Float | field_4 |
| `FFCDAAAA` | Float | field_8 |
| `62743B96` | [SLdrAnimGridAxisTrackingData](#sldranimgridaxistrackingdata) | field_C |
| `6E3C4CD9` | [SLdrAnimGridAxisTrackingData](#sldranimgridaxistrackingdata) | field_20 |
| `9A6F0399` | Uint32 | field_34 |
| `278C9867` | Bool | field_38 |
| `BB8789E6` | Bool | field_39 |
| `D9C80F4C` | [String] | field_3C |
| `DF369D65` | Bool | field_48 |
| `2C733283` | Uint32 | field_4C |
| `D25D62A5` | Uint32 | field_50 |

### SLdrAnimatedCameraBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `03EC2BE0` | [CObjectId] | field_0 |
| `8C8E6720` | [String] | field_10 |
| `2A569925` | Bool | field_1C |
| `915125F5` | Bool | field_1D |

### SLdrAnimationControllerData
| Field | Type | Description |
| --- | --- | --- |
| `7CD8C749` | [Property] | field_0 |
| `62049066` | [SLdrModelLightingData](#sldrmodellightingdata) | field_8 |
| `91C39B4A` | Bool | field_24 |

### SLdrAnimationGridController
| Field | Type | Description |
| --- | --- | --- |
| `CBEA308E` | [CObjectId] | field_0 |
| `1A600CB0` | [String] | field_10 |
| `1B20FFB6` | Bool | field_1C |
| `331BABB4` | [Property] | field_20 |

### SLdrAnimationGridDriverData
| Field | Type | Description |
| --- | --- | --- |
| `EA265D3B` | [List]&lt;[Property]&gt; | field_0 |

### SLdrAnimationGridDriverSeaLionToss
| Field | Type | Description |
| --- | --- | --- |
| `B8A2A825` | Float | field_0 |
| `D8B571BF` | Float | field_4 |

### SLdrAnimationMovementConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `E0BB302E` | Bool | field_0 |
| `09584FC3` | [enum_1007e0d8](#enum_1007e0d8) | field_4 |
| `9E7CA63E` | [enum_1007e0f8](#enum_1007e0f8) | field_8 |
| `EDEFB97F` | [enum_1007e110](#enum_1007e110) | field_C |
| `4DCD5219` | [enum_1007e130](#enum_1007e130) | field_10 |
| `1A03F30B` | Bool | field_14 |

### SLdrApplyDamage
| Field | Type | Description |
| --- | --- | --- |
| `DDCFA33B` | [SLdrDamageInfo](#sldrdamageinfo) | field_0 |
| `94C17883` | Bool | field_24 |
| `74C0543D` | Bool | field_25 |

### SLdrAudioBusController
| Field | Type | Description |
| --- | --- | --- |
| `79AE3474` | [List]&lt;Uint8&gt; | field_0 |
| `798B5308` | [enum_10063184](#enum_10063184) | field_C |
| `E8DDBDEE` | Float | field_10 |
| `0901EE84` | Float | field_14 |
| `A37EA8DF` | Float | field_18 |
| `728858C4` | Uint32 | field_1C |
| `8087F769` | [String] | field_20 |
| `F746A6F5` | Float | field_2C |
| `5480135E` | Uint32 | field_30 |
| `86A30415` | Bool | field_34 |
| `7630AA60` | Bool | field_35 |
| `844FB9D7` | Bool | field_36 |
| `8137979B` | Bool | field_37 |

### SLdrAudioBusIdSettingsPair
| Field | Type | Description |
| --- | --- | --- |
| `CA1CEE3F` | Uint8 | field_0 |
| `6C63D494` | [SLdrAudioBusSettings](#sldraudiobussettings) | field_4 |

### SLdrAudioBusMixer
| Field | Type | Description |
| --- | --- | --- |
| `84976565` | Float | field_0 |
| `EE2532C0` | Float | field_4 |
| `29584BE3` | Bool | field_8 |
| `44E56DCB` | [List]&lt;[SLdrAudioBusIdSettingsPair](#sldraudiobusidsettingspair)&gt; | field_C |

### SLdrAudioBusSettings
| Field | Type | Description |
| --- | --- | --- |
| `5B66FCC2` | Float | field_0 |
| `0F92A6EF` | Uint32 | field_4 |
| `3C20A5AA` | [String] | field_8 |
| `F235B7AE` | Float | field_14 |
| `5454789D` | Uint32 | field_18 |
| `A1C86E48` | Bool | field_1C |
| `28BD989B` | Bool | field_1D |

### SLdrAudioEffect
| Field | Type | Description |
| --- | --- | --- |
| `0BC37C6F` | [SLdrAcousticBounds](#sldracousticbounds) | field_0 |
| `508300A7` | Bool | field_10 |
| `E9E8953D` | Bool | field_11 |
| `05D247A6` | Bool | field_12 |
| `51DA4F57` | [enum_1006349c](#enum_1006349c) | field_14 |
| `EE6CC99D` | [List]&lt;[SLdrAudioEffectSettings](#sldraudioeffectsettings)&gt; | field_18 |
| `BB5C2BC0` | Float | field_24 |
| `8923E96C` | Bool | field_28 |
| `86F6CF69` | [enum_100634b4](#enum_100634b4) | field_2C |
| `640E46C8` | [CMayaSpline] | field_30 |

### SLdrAudioEffectSettings
| Field | Type | Description |
| --- | --- | --- |
| `535F330F` | Uint32 | field_0 |
| `B438130D` | [String] | field_4 |
| `9EAE228D` | Float | field_10 |

### SLdrAutoDestructTypeLandCounter
| Field | Type | Description |
| --- | --- | --- |
| `C727FFBC` | Uint32 | field_0 |

### SLdrAutoDestructTypeTimer
| Field | Type | Description |
| --- | --- | --- |
| `4B5FD486` | Float | field_0 |

### SLdrBaboon
| Field | Type | Description |
| --- | --- | --- |
| `ED6485C0` | [List]&lt;[Property]&gt; | field_0 |

### SLdrBaboonActionPhase
| Field | Type | Description |
| --- | --- | --- |
| `8BF437B0` | [List]&lt;[Property]&gt; | field_0 |
| `6615BF2D` | [Property] | field_C |

### SLdrBaboonBombSwing
| Field | Type | Description |
| --- | --- | --- |
| `9ACD677E` | Uint32 | field_0 |
| `EA88200C` | Float | field_4 |
| `5E98F1FC` | Float | field_8 |
| `CB1C328F` | Float | field_C |
| `666905A4` | Float | field_10 |
| `584A6CB3` | Uint32 | field_14 |

### SLdrBaboonBombToss
| Field | Type | Description |
| --- | --- | --- |
| `6D15A4DC` | Uint32 | field_0 |
| `7F761B76` | Float | field_4 |
| `A0117D8A` | Float | field_8 |
| `3F451BE8` | Float | field_C |
| `96D387DE` | Float | field_10 |
| `5A45640C` | Float | field_14 |
| `4B0E6438` | Float | field_18 |
| `898C6277` | Uint32 | field_1C |
| `050BB9E4` | Float | field_20 |
| `8479E214` | Float | field_24 |
| `A9FCACAA` | Float | field_28 |

### SLdrBaboonControllerData
| Field | Type | Description |
| --- | --- | --- |
| `34D648A3` | String | field_0 |

### SLdrBaboonDropJump
| Field | Type | Description |
| --- | --- | --- |
| `4265288F` | Uint32 | field_0 |
| `9C2F07B3` | Float | field_4 |
| `2E9DF437` | Float | field_8 |
| `B11FCF6A` | Float | field_C |
| `92D355EF` | Float | field_10 |
| `B527903D` | Float | field_14 |
| `FD86F6E4` | Float | field_18 |
| `4E513E76` | Float | field_1C |
| `4108914A` | Float | field_20 |
| `81B4F4A7` | Float | field_24 |
| `EA106226` | Float | field_28 |
| `9BEBE60F` | Float | field_2C |
| `719EAF8E` | Float | field_30 |
| `27D115E9` | Float | field_34 |
| `38D61421` | Float | field_38 |
| `F883437E` | Float | field_3C |
| `D485F203` | Float | field_40 |
| `98B0B8F5` | Float | field_44 |
| `972EBBE7` | Float | field_48 |
| `0792C071` | Float | field_4C |
| `C26E45D8` | Float | field_50 |

### SLdrBaboonManager
| Field | Type | Description |
| --- | --- | --- |
| `B50E0138` | Uint32 | field_0 |
| `A6516A71` | Float | field_4 |
| `34AADE29` | Float | field_8 |
| `07F655CB` | Float | field_C |
| `1B02B663` | [List]&lt;[SLdrBaboonActionPhase](#sldrbaboonactionphase)&gt; | field_10 |

### SLdrBaboonMultiRoll
| Field | Type | Description |
| --- | --- | --- |
| `D0A48681` | Uint32 | field_0 |
| `37611FFA` | Float | field_4 |
| `CE5B131B` | Float | field_8 |
| `175A8CA9` | Float | field_C |
| `63C70E0F` | Float | field_10 |
| `869EBE3C` | Float | field_14 |
| `D36BE024` | Float | field_18 |
| `4435BAA6` | Float | field_1C |
| `6584E79F` | Float | field_20 |
| `478A8183` | Float | field_24 |
| `5FB5A0C0` | Float | field_28 |
| `16EAD253` | Uint32 | field_2C |
| `1F4E1FB1` | Float | field_30 |

### SLdrBaboonMultiSwing
| Field | Type | Description |
| --- | --- | --- |
| `E30B4497` | Float | field_0 |
| `C8959C4D` | [List]&lt;[SLdrMultiSwingAttackData](#sldrmultiswingattackdata)&gt; | field_4 |
| `3537D35D` | [List]&lt;Int32&gt; | field_10 |

### SLdrBaboonRollJump
| Field | Type | Description |
| --- | --- | --- |
| `E7BC9FC4` | Uint32 | field_0 |
| `D96694E6` | Float | field_4 |
| `CFCE2129` | Float | field_8 |
| `CFC513BE` | Float | field_C |
| `3FF53CC0` | Float | field_10 |
| `6FC646A0` | Float | field_14 |
| `6B373317` | Float | field_18 |
| `634A7C0B` | Float | field_1C |
| `BFC1D685` | Float | field_20 |
| `E0B1E983` | Float | field_24 |
| `CBB0EF31` | Float | field_28 |
| `078FA5DF` | Float | field_2C |
| `F4BD8D99` | Float | field_30 |
| `5213E4F5` | Float | field_34 |
| `5F617C43` | Float | field_38 |
| `CD43F0BC` | Float | field_3C |
| `9B8A7F47` | Float | field_40 |
| `3A200F1D` | Float | field_44 |
| `BD7E168E` | Float | field_48 |
| `FDF1E052` | Float | field_4C |
| `D255AF76` | Float | field_50 |
| `91A4B538` | Float | field_54 |
| `361A1E26` | Float | field_58 |
| `05063CC9` | Float | field_5C |
| `FD3A25AC` | Float | field_60 |
| `4DDCBD50` | Float | field_64 |

### SLdrBaboonVineSwing
| Field | Type | Description |
| --- | --- | --- |
| `41EA01BD` | Uint32 | field_0 |
| `21447DF2` | Uint32 | field_4 |
| `D3846FBE` | Float | field_8 |
| `D902E1D3` | Float | field_C |
| `FA9701A4` | Float | field_10 |
| `5CADCD93` | Uint32 | field_14 |
| `A91AEA78` | Float | field_18 |
| `0F8745A6` | Float | field_1C |

### SLdrBarrelBalloon
| Field | Type | Description |
| --- | --- | --- |
| `A43CFB07` | [String] | field_0 |
| `0604CC58` | [String] | field_C |
| `F8BA8056` | Float | field_18 |
| `D081EB2A` | Float | field_1C |
| `D5B9F31A` | Float | field_20 |
| `D472AA4F` | Float | field_24 |
| `2A258AA4` | Float | field_28 |
| `A1002AA3` | Float | field_2C |
| `E34F9817` | Float | field_30 |
| `62D15048` | Float | field_34 |
| `F99ECF8B` | Float | field_38 |
| `D2B2BB74` | Float | field_3C |
| `42A0797A` | Float | field_40 |
| `B3753030` | Float | field_44 |
| `940823F4` | Float | field_48 |
| `71970D53` | [CMayaSpline] | field_4C |
| `FBC8DED8` | Float | field_7C |
| `D479D62F` | Float | field_80 |
| `05A5AD48` | Float | field_84 |
| `F5D19AF3` | Float | field_88 |
| `9119D2E5` | Float | field_8C |
| `8F55A803` | Uint32 | field_90 |
| `98F524F4` | [SLdrExplosionData](#sldrexplosiondata) | field_94 |
| `E0BE8DEA` | [CObjectId] | field_C8 |
| `A1DCAFE7` | [CObjectId] | field_D8 |

### SLdrBarrelCannon
| Field | Type | Description |
| --- | --- | --- |
| `CB8507CA` | Float | field_0 |
| `C7C52867` | Float | field_4 |
| `BBE93231` | Bool | field_8 |
| `54C39211` | [enum_10014400](#enum_10014400) | field_C |
| `8C338827` | Float | field_10 |
| `5BF3DAEB` | Float | field_14 |
| `B4197DD8` | Float | field_18 |
| `F7F62E78` | Float | field_1C |
| `712FF473` | Float | field_20 |
| `159A7F15` | [enum_10014440](#enum_10014440) | field_24 |
| `3E9A325A` | Float | field_28 |
| `B066C201` | Uint32 | field_2C |
| `50D5409B` | Bool | field_30 |
| `DD1588DD` | Bool | field_31 |
| `DC58425C` | Bool | field_32 |
| `F1B06581` | Bool | field_33 |
| `FCD2865F` | Bool | field_34 |
| `C729703E` | Bool | field_35 |
| `4C6F8EC7` | Bool | field_36 |
| `02FCFAC1` | Bool | field_37 |
| `C4FF7845` | Bool | field_38 |
| `6B860417` | Bool | field_39 |
| `8709D978` | Bool | field_3A |
| `11E5B03B` | [enum_10014460](#enum_10014460) | field_3C |
| `A2DCA9FA` | [enum_10014460](#enum_10014460) | field_40 |
| `0A60FD8C` | [CObjectId] | field_44 |
| `0A203DA3` | Bool | field_54 |
| `431B04AB` | Bool | field_55 |

### SLdrBarrelCannonOrientationControl
| Field | Type | Description |
| --- | --- | --- |
| `FB2971A9` | Float | field_0 |

### SLdrBeatUpHandler
| Field | Type | Description |
| --- | --- | --- |
| `C8C8DA2C` | [SLdrControlCommand](#sldrcontrolcommand) | field_0 |
| `D26394A5` | [SLdrControlCommand](#sldrcontrolcommand) | field_4 |
| `1E9686FC` | Float | field_8 |
| `0050AA6B` | Float | field_C |
| `2139F7BF` | Float | field_10 |
| `7DBAE6A6` | Bool | field_14 |
| `09893535` | Bool | field_15 |
| `F3F6A41B` | Bool | field_16 |
| `D6F20714` | Float | field_18 |
| `7421F1AA` | Uint32 | field_1C |
| `C551A7BF` | [SLdrBeatUpPrize](#sldrbeatupprize) | field_20 |
| `9554363B` | [SLdrBeatUpPrize](#sldrbeatupprize) | field_2C |
| `882A254F` | [SLdrBeatUpPrize](#sldrbeatupprize) | field_38 |
| `57D40557` | [CObjectId] | field_44 |
| `73786916` | Bool | field_54 |
| `4408CCCA` | [enum_10063dd4](#enum_10063dd4) | field_58 |
| `2604675E` | Float | field_5C |

### SLdrBeatUpPrize
| Field | Type | Description |
| --- | --- | --- |
| `263E0A34` | [SLdrPlayerItem](#sldrplayeritem) | field_0 |
| `53342155` | Uint32 | field_4 |
| `536D4233` | Float | field_8 |

### SLdrBehaviorAutoDestructData
| Field | Type | Description |
| --- | --- | --- |
| `96F08BC2` | [Property] | field_0 |

### SLdrBehaviorBopJumpData
| Field | Type | Description |
| --- | --- | --- |
| `2140F849` | Bool | field_0 |
| `1BF72D35` | [Property] | field_4 |
| `B972DBCE` | [Property] | field_C |
| `343906B6` | [List]&lt;[SLdrBopJumpJumpData](#sldrbopjumpjumpdata)&gt; | field_14 |

### SLdrBehaviorBopJumpProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `ABDF6D40` | Bool | field_0 |
| `98FC5ABB` | [Property] | field_4 |
| `4B89B35C` | [Property] | field_C |
| `FD14D001` | [Property] | field_14 |

### SLdrBehaviorBreachJumpData
| Field | Type | Description |
| --- | --- | --- |
| `50723B4D` | [enum_10077078](#enum_10077078) | field_0 |

### SLdrBehaviorChangePostureData
| Field | Type | Description |
| --- | --- | --- |
| `3AACC116` | Bool | field_0 |
| `CE043697` | Bool | field_1 |

### SLdrBehaviorContactReactionData
This struct does not have any fields

### SLdrBehaviorDespawnData
| Field | Type | Description |
| --- | --- | --- |
| `AA82B577` | Bool | field_0 |

### SLdrBehaviorExplodeReactionData
This struct does not have any fields

### SLdrBehaviorFallData
| Field | Type | Description |
| --- | --- | --- |
| `6119CA3D` | Float | field_0 |

### SLdrBehaviorFlipData
| Field | Type | Description |
| --- | --- | --- |
| `43A887D6` | Uint32 | field_0 |

### SLdrBehaviorFollowDynamicPathData
| Field | Type | Description |
| --- | --- | --- |
| `58368BD5` | [Property] | field_0 |
| `5AE5A9A8` | [List]&lt;[Property]&gt; | field_8 |

### SLdrBehaviorFollowPathData
| Field | Type | Description |
| --- | --- | --- |
| `3FD67273` | Bool | field_0 |
| `FB34BD73` | Float | field_4 |
| `06E20225` | Float | field_8 |
| `4FEA554A` | Float | field_C |
| `D75F7E1A` | Float | field_10 |
| `22727BCB` | [enum_10079b9c](#enum_10079b9c) | field_14 |
| `78DCFB00` | Bool | field_18 |

### SLdrBehaviorFollowPathProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `604805F4` | Bool | field_0 |
| `13E26807` | [CMayaSpline] | field_4 |
| `E5530E02` | Float | field_34 |
| `C18B705B` | Float | field_38 |
| `55F9208D` | Float | field_3C |
| `CE2967C8` | Float | field_40 |
| `8AF5E184` | Float | field_44 |
| `DD8D9800` | [enum_10077550](#enum_10077550) | field_48 |
| `A892C9C3` | [Property] | field_4C |
| `0EC7167D` | Bool | field_54 |
| `031F05FB` | Float | field_58 |
| `D4216536` | Bool | field_5C |
| `33D2D823` | Float | field_60 |
| `677FE98D` | [enum_10079b9c](#enum_10079b9c) | field_64 |

### SLdrBehaviorFollowSurfaceData
| Field | Type | Description |
| --- | --- | --- |
| `12E9634B` | Float | field_0 |
| `AA1AD8FC` | Float | field_4 |
| `9B4E3EAD` | Float | field_8 |
| `0CC0DD6D` | Float | field_C |
| `594D4E75` | Float | field_10 |
| `218D2755` | Float | field_14 |
| `B00036DB` | Bool | field_18 |

### SLdrBehaviorGlideJumpData
| Field | Type | Description |
| --- | --- | --- |
| `804AF655` | Float | field_0 |
| `8A8C2462` | Float | field_4 |
| `DFAD8705` | Float | field_8 |
| `73FFD481` | Float | field_C |

### SLdrBehaviorGrabbedData
| Field | Type | Description |
| --- | --- | --- |
| `3DCB2CB2` | [Property] | field_0 |
| `EDFB2AFA` | [Property] | field_8 |
| `4FADB711` | Bool | field_10 |
| `B4FF6589` | [SLdrDamageInfo](#sldrdamageinfo) | field_14 |
| `196C36A1` | Bool | field_38 |
| `AF428BD7` | [SLdrDamageInfo](#sldrdamageinfo) | field_3C |

### SLdrBehaviorGridAttackData
| Field | Type | Description |
| --- | --- | --- |
| `C9912C94` | Float | field_0 |
| `62E484B4` | Float | field_4 |
| `F5BD7504` | Float | field_8 |
| `5629F4BE` | Float | field_C |
| `F7142E7F` | [Property] | field_10 |
| `CB136E04` | [Property] | field_18 |

### SLdrBehaviorHitReactionData
This struct does not have any fields

### SLdrBehaviorHurlReactionData
| Field | Type | Description |
| --- | --- | --- |
| `2DFC839E` | [CVector3f] | field_0 |
| `DB8E5C33` | [CVector3f] | field_C |
| `ECA9855C` | [CVector3f] | field_18 |
| `ECF2A27C` | [CVector3f] | field_24 |
| `04C4CEEB` | [enum_10079b9c](#enum_10079b9c) | field_30 |
| `0AA16441` | [enum_10079b9c](#enum_10079b9c) | field_34 |
| `A1F06271` | [CObjectId] | field_38 |

### SLdrBehaviorIceCubeData
| Field | Type | Description |
| --- | --- | --- |
| `CF3F64B8` | Uint32 | field_0 |
| `60A779EC` | Uint32 | field_4 |
| `B45334EC` | Uint32 | field_8 |
| `D45FAA70` | Uint32 | field_C |
| `A635833B` | [String] | field_10 |
| `3A331686` | Uint32 | field_1C |
| `55D475C6` | Uint32 | field_20 |

### SLdrBehaviorKnockbackProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `A308ED98` | [SLdrKnockbackProceduralData](#sldrknockbackproceduraldata) | field_0 |
| `CC4DDDE4` | [SLdrKnockbackProceduralData](#sldrknockbackproceduraldata) | field_C |

### SLdrBehaviorKnockbackReactionData
This struct does not have any fields

### SLdrBehaviorKnockbackStunReactionData
This struct does not have any fields

### SLdrBehaviorLinearProjectileData
| Field | Type | Description |
| --- | --- | --- |
| `0D1E5847` | Float | field_0 |
| `969F06CF` | Float | field_4 |
| `110E338A` | [List]&lt;Float&gt; | field_8 |
| `5E263DBB` | Float | field_14 |
| `1E60F2E1` | Bool | field_18 |
| `35E7EA9C` | Float | field_1C |
| `CC53070B` | Float | field_20 |

### SLdrBehaviorMeleeAttackData
| Field | Type | Description |
| --- | --- | --- |
| `54AB3CE7` | Uint32 | field_0 |
| `5D0D25A5` | [Property] | field_4 |
| `B7AC4D3A` | [Property] | field_C |
| `63F45E98` | Float | field_14 |
| `F2BDE017` | Float | field_18 |

### SLdrBehaviorPolarBearCubeSlingData
| Field | Type | Description |
| --- | --- | --- |
| `0001E1A3` | [List]&lt;[SLdrIceCubeSlingSequence](#sldricecubeslingsequence)&gt; | field_0 |

### SLdrBehaviorPolarBearDelayedSlamData
| Field | Type | Description |
| --- | --- | --- |
| `989D4FC9` | Float | field_0 |
| `464544DF` | Uint32 | field_4 |
| `8B5C53D9` | Uint32 | field_8 |
| `95E374E8` | Float | field_C |
| `CF7531E2` | Float | field_10 |
| `EBF964A9` | Float | field_14 |
| `FDEA5A1E` | Float | field_18 |
| `22490422` | Float | field_1C |
| `7DD1DC84` | Float | field_20 |
| `1DDF90B3` | Float | field_24 |
| `9FDECE3A` | Float | field_28 |

### SLdrBehaviorPolarBearIcyChargeData
| Field | Type | Description |
| --- | --- | --- |
| `F0442164` | Bool | field_0 |

### SLdrBehaviorPolarBearIcyRoarData
| Field | Type | Description |
| --- | --- | --- |
| `6B2EF66D` | Float | field_0 |
| `C5565ABE` | Bool | field_4 |

### SLdrBehaviorPolarBearMegaLeapData
| Field | Type | Description |
| --- | --- | --- |
| `97D292DE` | Float | field_0 |
| `A432D01B` | Float | field_4 |
| `5CE31BA9` | Uint32 | field_8 |
| `F13CA761` | Uint32 | field_C |
| `565D20E9` | [List]&lt;[SLdrHurlParameters](#sldrhurlparameters)&gt; | field_10 |
| `3A5BA87B` | Bool | field_1C |
| `DC3C8078` | Bool | field_1D |
| `2D2D654D` | Bool | field_1E |
| `5D2575EA` | Float | field_20 |
| `C30F8D9C` | Float | field_24 |
| `5E42BAC5` | [enum_100781b8](#enum_100781b8) | field_28 |

### SLdrBehaviorPolarBearMegaSlamData
| Field | Type | Description |
| --- | --- | --- |
| `E211CD7F` | Float | field_0 |
| `70CDF860` | Float | field_4 |
| `069295CD` | [SLdrHurlParameters](#sldrhurlparameters) | field_8 |
| `16030162` | Float | field_10 |
| `0E4506AE` | Float | field_14 |

### SLdrBehaviorPolarBearSummersaultSlamData
| Field | Type | Description |
| --- | --- | --- |
| `A29379EB` | [List]&lt;[SLdrSummersaultSlamAttackSequence](#sldrsummersaultslamattacksequence)&gt; | field_0 |

### SLdrBehaviorProjectileAttackData
| Field | Type | Description |
| --- | --- | --- |
| `DBAADFC5` | Bool | field_0 |
| `A72DDDED` | Float | field_4 |
| `D95900D5` | Float | field_8 |
| `E9EBDC5F` | Float | field_C |
| `14D22D79` | Float | field_10 |
| `DF5F0A70` | Uint32 | field_14 |
| `56F67C88` | Uint32 | field_18 |
| `97124881` | Bool | field_1C |
| `E6CD9055` | [Property] | field_20 |
| `BE14E194` | Bool | field_28 |

### SLdrBehaviorScriptedOneShotAnimationData
This struct does not have any fields

### SLdrBehaviorSeaLionPainguinData
| Field | Type | Description |
| --- | --- | --- |
| `DE4B7C2A` | Float | field_0 |
| `391FAB48` | Float | field_4 |

### SLdrBehaviorSeaLionRingData
| Field | Type | Description |
| --- | --- | --- |
| `E427E8C7` | Float | field_0 |
| `1199D9FA` | Bool | field_4 |

### SLdrBehaviorSecondaryProjectileAttackData
| Field | Type | Description |
| --- | --- | --- |
| `5C243F27` | Float | field_0 |
| `855EC51B` | Float | field_4 |
| `35F9D625` | Float | field_8 |
| `76C4A79F` | Float | field_C |
| `1BE40DFE` | Bool | field_10 |

### SLdrBehaviorSeekerData
| Field | Type | Description |
| --- | --- | --- |
| `47B912C0` | Float | field_0 |
| `F03B0CD2` | Float | field_4 |
| `8C088B72` | Float | field_8 |
| `97576840` | Float | field_C |
| `DC44146F` | Float | field_10 |
| `CFB06BEB` | Float | field_14 |
| `9913EA66` | Float | field_18 |
| `5F4F48F7` | Float | field_1C |
| `C96D2CE4` | Float | field_20 |
| `F16A9FCB` | [enum_10079b9c](#enum_10079b9c) | field_24 |
| `DBC94DAC` | [enum_1007e130](#enum_1007e130) | field_28 |
| `D97B19A8` | Float | field_2C |
| `56F74BC1` | Bool | field_30 |
| `0D33371D` | [Property] | field_34 |

### SLdrBehaviorSlaveControllerData
| Field | Type | Description |
| --- | --- | --- |
| `6DDE0E00` | Float | field_0 |
| `F736393E` | Float | field_4 |
| `8A450198` | Float | field_8 |
| `B744789E` | Float | field_C |

### SLdrBehaviorSpawnData
| Field | Type | Description |
| --- | --- | --- |
| `5C3D8AC1` | [Property] | field_0 |
| `C9F7FA71` | Bool | field_8 |
| `D2B5D8F1` | Bool | field_9 |
| `B0D01055` | Uint32 | field_C |
| `58A70F92` | Float | field_10 |

### SLdrBehaviorStationaryData
| Field | Type | Description |
| --- | --- | --- |
| `C797DEB0` | Bool | field_0 |
| `9FFFF930` | Bool | field_1 |
| `B5B1EA1C` | Float | field_4 |
| `8A2A2F11` | [enum_10079b9c](#enum_10079b9c) | field_8 |
| `5FA7AF4D` | Bool | field_C |

### SLdrBehaviorStunReactionData
| Field | Type | Description |
| --- | --- | --- |
| `5AF3342E` | Uint32 | field_0 |

### SLdrBehaviorSwimPathProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `4A0DE692` | Bool | field_0 |
| `135745A4` | Float | field_4 |
| `51D3C01B` | Float | field_8 |
| `E4376D39` | [enum_10077550](#enum_10077550) | field_C |
| `97185B4D` | Float | field_10 |
| `59BB12B4` | Bool | field_14 |
| `3A2E6DA8` | Float | field_18 |
| `B19A6C55` | Float | field_1C |
| `ED3AE6D0` | Float | field_20 |
| `5A68FFBC` | [enum_10079b9c](#enum_10079b9c) | field_24 |
| `5F9347A1` | Bool | field_28 |
| `1FE8E23C` | Float | field_2C |
| `71ED488D` | Float | field_30 |
| `79B6BA28` | Float | field_34 |
| `C0A35913` | Bool | field_38 |
| `01FFAAB6` | Bool | field_39 |
| `08EE8A79` | Bool | field_3A |
| `BE3794E6` | Float | field_3C |
| `657044A1` | Bool | field_40 |

### SLdrBehaviorSwimSurfaceData
| Field | Type | Description |
| --- | --- | --- |
| `34BA79BF` | Float | field_0 |
| `7E80E610` | Float | field_4 |
| `86CEE9FB` | Float | field_8 |
| `0F1B26C7` | Bool | field_C |
| `3A68F257` | [String] | field_10 |
| `C3F0B8B9` | Float | field_1C |

### SLdrBehaviorSwoopAttackData
| Field | Type | Description |
| --- | --- | --- |
| `17AE70F9` | Uint32 | field_0 |
| `438B5381` | Float | field_4 |
| `CBFA6093` | [Property] | field_8 |

### SLdrBehaviorTargetedWanderData
| Field | Type | Description |
| --- | --- | --- |
| `1A50AA03` | Float | field_0 |
| `53DE3313` | Float | field_4 |
| `5B597B61` | [Property] | field_8 |
| `544E3196` | [enum_10079b9c](#enum_10079b9c) | field_10 |
| `3FD13099` | [enum_10079b9c](#enum_10079b9c) | field_14 |
| `0E139E7C` | [enum_1007e130](#enum_1007e130) | field_18 |

### SLdrBehaviorTeleportData
| Field | Type | Description |
| --- | --- | --- |
| `5A44401E` | Float | field_0 |
| `1DBCA449` | Float | field_4 |

### SLdrBehaviorVolumeTargetingData
| Field | Type | Description |
| --- | --- | --- |
| `88958798` | [List]&lt;[Property]&gt; | field_0 |

### SLdrBehaviorWanderData
| Field | Type | Description |
| --- | --- | --- |
| `96EB094F` | Float | field_0 |
| `87185018` | [enum_10079b9c](#enum_10079b9c) | field_4 |
| `BC3372F6` | [enum_1007e130](#enum_1007e130) | field_8 |

### SLdrBehaviorWanderProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `7DA57D75` | Float | field_0 |
| `BD460DE9` | Float | field_4 |
| `B50916EA` | Float | field_8 |

### SLdrBlinkAnimationData
| Field | Type | Description |
| --- | --- | --- |
| `39D4D358` | Float | field_0 |
| `62854F33` | Float | field_4 |

### SLdrBloomBlurValues
| Field | Type | Description |
| --- | --- | --- |
| `90D4AEDC` | Float | field_0 |
| `7A3449BC` | Float | field_4 |
| `ADAE6F6A` | Float | field_8 |
| `3ECA9258` | Float | field_C |
| `50A028D3` | Float | field_10 |
| `F602D634` | Float | field_14 |
| `A3921A54` | Float | field_18 |

### SLdrBloomEffect
| Field | Type | Description |
| --- | --- | --- |
| `82416B7E` | Float | field_0 |
| `E89DB183` | Float | field_4 |
| `E4AB5C2C` | Uint32 | field_8 |
| `E3369F0E` | [SLdrBloomBlurValues](#sldrbloomblurvalues) | field_C |

### SLdrBonusRoom
| Field | Type | Description |
| --- | --- | --- |
| `C92F65CD` | Bool | field_0 |
| `CF5345C5` | Bool | field_1 |
| `B64A5473` | Float | field_4 |
| `78FDE8C1` | Float | field_8 |
| `0486CE3B` | Uint32 | field_C |
| `92735D2B` | [SLdrPlayerItem](#sldrplayeritem) | field_10 |
| `0BF1EBB8` | Uint32 | field_14 |
| `1520F7DE` | [SLdrPlayerItem](#sldrplayeritem) | field_18 |
| `786AC4CF` | Uint32 | field_1C |
| `EEEF41D1` | [List]&lt;[SLdrPlayerItem](#sldrplayeritem)&gt; | field_20 |

### SLdrBopJumpDirectionControlData
| Field | Type | Description |
| --- | --- | --- |
| `4135BF32` | Uint32 | field_0 |
| `AC6C9214` | Float | field_4 |
| `98E151D4` | Float | field_8 |
| `FDE00079` | Float | field_C |
| `791ED50D` | Float | field_10 |

### SLdrBopJumpJumpData
| Field | Type | Description |
| --- | --- | --- |
| `F431AF51` | Uint32 | field_0 |
| `B13CF89F` | Float | field_4 |
| `7525A34E` | Uint32 | field_8 |
| `C5A2E796` | Uint32 | field_C |

### SLdrBopJumpNormalDirectionalControlData
This struct does not have any fields

### SLdrBopJumpNormalJumpTypeData
This struct does not have any fields

### SLdrBopJumpOnPlayerJumpedJumpTypeData
| Field | Type | Description |
| --- | --- | --- |
| `994C8AF1` | Float | field_0 |
| `22C33431` | Float | field_4 |

### SLdrBopJumpPeriodicJumpTypeData
| Field | Type | Description |
| --- | --- | --- |
| `BE9CF5AA` | Float | field_0 |

### SLdrBopJumpPingPongDirectionalControlData
This struct does not have any fields

### SLdrBopJumpProceduralJumpData
| Field | Type | Description |
| --- | --- | --- |
| `0BB709AA` | Uint32 | field_0 |
| `1E25757E` | Float | field_4 |
| `64615940` | Float | field_8 |
| `B990C9A9` | Uint32 | field_C |

### SLdrBopJumpProceduralJumpTargetData
| Field | Type | Description |
| --- | --- | --- |
| `4F13F462` | Uint32 | field_0 |
| `CB7CA2A1` | Float | field_4 |
| `BBE79499` | Uint32 | field_8 |

### SLdrBopJumpRandomDirectionalControlData
| Field | Type | Description |
| --- | --- | --- |
| `5F9469CE` | Float | field_0 |
| `9C608E95` | Float | field_4 |
| `AA77DC93` | Uint32 | field_8 |
| `B1B83F3A` | Bool | field_C |

### SLdrBopJumpReactiveJumpTypeData
| Field | Type | Description |
| --- | --- | --- |
| `FBB9E736` | Bool | field_0 |
| `A7A69B68` | Bool | field_1 |

### SLdrBopJumpSeekPlayerDirectionalControlData
| Field | Type | Description |
| --- | --- | --- |
| `A6C4B203` | Float | field_0 |
| `05F2A260` | Float | field_4 |
| `45E57F4B` | Uint32 | field_8 |
| `A40FFF69` | Bool | field_C |

### SLdrBopJumpSequenceTargetPlayer
| Field | Type | Description |
| --- | --- | --- |
| `99DD7C50` | [List]&lt;[SLdrBopJumpTargetPlayerJumpData](#sldrbopjumptargetplayerjumpdata)&gt; | field_0 |

### SLdrBopJumpTargetPlayerJumpData
| Field | Type | Description |
| --- | --- | --- |
| `363E62D2` | Uint32 | field_0 |
| `4C4E6443` | Float | field_4 |
| `4EF7509E` | Uint32 | field_8 |

### SLdrBopJumpTypeData
| Field | Type | Description |
| --- | --- | --- |
| `958A3114` | Uint32 | field_0 |
| `B340EDB9` | Float | field_4 |
| `05CAF1FF` | Bool | field_8 |
| `FC8E5823` | Bool | field_9 |

### SLdrBounceeData
| Field | Type | Description |
| --- | --- | --- |
| `A6698BBF` | Float | field_0 |
| `B208A9D4` | Float | field_4 |
| `D24584BF` | [SLdrBouncerJumpHeights](#sldrbouncerjumpheights) | field_8 |
| `972D93BE` | Float | field_10 |
| `B28AE010` | [CObjectId] | field_14 |
| `2B5BDEF4` | [CObjectId] | field_24 |
| `3CB3CA2B` | Bool | field_34 |
| `F7A8027F` | Float | field_38 |
| `EFD02A78` | Float | field_3C |
| `25E8B436` | Float | field_40 |
| `DB5DBB3A` | Float | field_44 |

### SLdrBouncer
| Field | Type | Description |
| --- | --- | --- |
| `0A3A0848` | [SLdrBounceeData](#sldrbounceedata) | field_0 |
| `1AB1DB8B` | Float | field_48 |
| `A538048D` | [CObjectId] | field_4C |

### SLdrBouncerJumpHeights
| Field | Type | Description |
| --- | --- | --- |
| `BDEE28B4` | Float | field_0 |
| `B5376139` | Float | field_4 |

### SLdrBreathMonitor
| Field | Type | Description |
| --- | --- | --- |
| `5D28D144` | [CMayaSpline] | field_0 |

### SLdrBurningBranch
| Field | Type | Description |
| --- | --- | --- |
| `B33D56DB` | Bool | field_0 |
| `262C26EC` | Bool | field_1 |
| `70DA5C24` | Bool | field_2 |
| `9F540DDB` | Float | field_4 |
| `4759480B` | Float | field_8 |
| `032C43BB` | Float | field_C |
| `4D694588` | [SLdrModelLightingData](#sldrmodellightingdata) | field_10 |
| `2447B26B` | [List]&lt;[SLdrBurningBranchSegment](#sldrburningbranchsegment)&gt; | field_2C |

### SLdrBurningBranchSegment
| Field | Type | Description |
| --- | --- | --- |
| `9299A9F6` | [CObjectId] | field_0 |

### SLdrCameraFlags
| Field | Type | Description |
| --- | --- | --- |
| `D4610ACE` | Bool | field_0 |
| `C02BECCD` | Bool | field_1 |
| `50B24946` | Bool | field_2 |

### SLdrCameraHint
| Field | Type | Description |
| --- | --- | --- |
| `ACEA3A85` | Bool | field_0 |
| `7ECC452A` | [SLdrGameHintData](#sldrgamehintdata) | field_4 |
| `7199A963` | Bool | field_8 |
| `0415103F` | Bool | field_9 |
| `CB91ED48` | Bool | field_A |
| `6E8BD962` | Float | field_C |
| `BCD0513D` | Float | field_10 |
| `90198BE3` | Float | field_14 |
| `714A49D6` | Float | field_18 |
| `002EC111` | [SLdrCameraFlags](#sldrcameraflags) | field_1C |
| `16D11D72` | [SLdrCinematicCameraSettings](#sldrcinematiccamerasettings) | field_20 |
| `50405E85` | [List]&lt;[Property]&gt; | field_30 |
| `868412A2` | [SLdrCameraInterpolation](#sldrcamerainterpolation) | field_3C |
| `0691B5A8` | [SLdrCameraInterpolation](#sldrcamerainterpolation) | field_11C |
| `8C31724D` | [enum_10064500](#enum_10064500) | field_1FC |

### SLdrCameraInterpolation
| Field | Type | Description |
| --- | --- | --- |
| `CE268E09` | [SLdrInterpolationOptions](#sldrinterpolationoptions) | field_0 |
| `559FD504` | [SLdrMotionInterpolationMethod](#sldrmotioninterpolationmethod) | field_10 |
| `C49C17B1` | [SLdrOrientationInterpolationMethod](#sldrorientationinterpolationmethod) | field_58 |
| `44DD36C9` | [SLdrFOVInterpolationMethod](#sldrfovinterpolationmethod) | field_9C |

### SLdrCameraManager
| Field | Type | Description |
| --- | --- | --- |
| `11DF9F4B` | Bool | field_0 |

### SLdrCameraShaker
| Field | Type | Description |
| --- | --- | --- |
| `8A783CCA` | [SLdrCameraShakerData](#sldrcamerashakerdata) | field_0 |

### SLdrCameraShakerData
| Field | Type | Description |
| --- | --- | --- |
| `B0509263` | [SLdrCameraShakerFlags](#sldrcamerashakerflags) | field_0 |
| `550FEF0E` | Float | field_C |
| `2C48DEBA` | Float | field_10 |
| `A5CC074F` | [SLdrCameraShakerEnvelope](#sldrcamerashakerenvelope) | field_14 |
| `BED681B0` | [SLdrCameraShakerEnvelope](#sldrcamerashakerenvelope) | field_78 |
| `D00004ED` | [SLdrCameraShakerEnvelope](#sldrcamerashakerenvelope) | field_DC |
| `AF806C3A` | [CObjectId] | field_140 |

### SLdrCameraShakerEnvelope
| Field | Type | Description |
| --- | --- | --- |
| `56128DB7` | [enum_1005bae8](#enum_1005bae8) | field_0 |
| `1C88ABB2` | [CMayaSpline] | field_4 |
| `74DFE6D6` | [CMayaSpline] | field_34 |

### SLdrCameraShakerFlags
| Field | Type | Description |
| --- | --- | --- |
| `74A1AE35` | Bool | field_0 |
| `BD128E24` | Bool | field_1 |
| `9DB281EB` | Bool | field_2 |
| `36B83D6D` | Bool | field_3 |
| `15AA25AC` | Bool | field_4 |
| `CE7DAB72` | Bool | field_5 |
| `2B1EB2D7` | Bool | field_6 |
| `74AE6F3C` | Bool | field_7 |
| `671E4B73` | Bool | field_8 |
| `2B5E2C73` | Bool | field_9 |
| `5DD338FB` | Bool | field_A |

### SLdrCameraTarget
| Field | Type | Description |
| --- | --- | --- |
| `577D9B50` | Bool | field_0 |
| `19DAA432` | [enum_100647b4](#enum_100647b4) | field_4 |
| `C006A4AE` | [String] | field_8 |

### SLdrCameraTargetOrientationBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `12F82EB1` | [SLdrLookAtOrientation](#sldrlookatorientation) | field_0 |

### SLdrCameraTargetPlayer
This struct does not have any fields

### SLdrCausticVolume
| Field | Type | Description |
| --- | --- | --- |
| `DCBD9E01` | [CColor4f] | field_0 |
| `008B5704` | [CObjectId] | field_10 |
| `B12455D2` | [SLdrCausticVolumeAttenuation](#sldrcausticvolumeattenuation) | field_20 |
| `234E49AA` | Float | field_38 |
| `906729AE` | Float | field_3C |
| `71DF6A2E` | [SLdrWaterDirection](#sldrwaterdirection) | field_40 |
| `AAF86AA3` | [CVector3f] | field_48 |

### SLdrCausticVolumeAttenuation
| Field | Type | Description |
| --- | --- | --- |
| `22B46295` | Float | field_0 |
| `939658E9` | Float | field_4 |
| `64E91476` | Float | field_8 |
| `E7D80195` | Float | field_C |
| `FD0DAEAF` | Float | field_10 |
| `1B475D04` | Float | field_14 |

### SLdrChannelContributionModifiers
| Field | Type | Description |
| --- | --- | --- |
| `6BEC431D` | Float | field_0 |
| `A674C6EF` | Float | field_4 |
| `E993F798` | Float | field_8 |
| `181852D0` | Float | field_C |

### SLdrCharacterAnimationSet
| Field | Type | Description |
| --- | --- | --- |
| `1610B65C` | [CObjectId] | field_0 |
| `C1A93B75` | [String] | field_10 |

### SLdrCharacterPrimitive
| Field | Type | Description |
| --- | --- | --- |
| `89B7E671` | [String] | field_0 |
| `5D5BA542` | Bool | field_C |
| `08048ECB` | [SLdrRuleSetData](#sldrrulesetdata) | field_10 |
| `2E3B2553` | Uint32 | field_1C |
| `0D9080CD` | Bool | field_20 |
| `63D54306` | Bool | field_21 |
| `A3E6A4E0` | Bool | field_22 |
| `A8B40AB5` | Bool | field_23 |
| `2664BE54` | Bool | field_24 |
| `1E396C5E` | [enum_10079200](#enum_10079200) | field_28 |
| `0FD0AEAD` | Float | field_2C |
| `3CC25EA5` | [String] | field_30 |
| `AFB7BD0C` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_3C |
| `AFBA5F81` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_49 |
| `EDD4D424` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_56 |
| `EB60A266` | [SLdrCollisionBehaviors](#sldrcollisionbehaviors) | field_63 |
| `CF650990` | [SLdrCollisionBehaviors](#sldrcollisionbehaviors) | field_6C |
| `791211F9` | Bool | field_75 |
| `01E4B0EE` | [enum_10079210](#enum_10079210) | field_78 |

### SLdrCharacterPrimitivesCollision
This struct does not have any fields

### SLdrCharacterPrimitivesData
| Field | Type | Description |
| --- | --- | --- |
| `1612CE3C` | [List]&lt;[SLdrCharacterPrimitive](#sldrcharacterprimitive)&gt; | field_0 |

### SLdrCheckpoint
| Field | Type | Description |
| --- | --- | --- |
| `52C7E134` | Bool | field_0 |
| `93180427` | Bool | field_1 |
| `C7C6EC2E` | Uint32 | field_4 |
| `39DF067F` | Float | field_8 |
| `C10A7C56` | Bool | field_C |
| `9E9B5C19` | Bool | field_D |
| `D4E336FC` | [List]&lt;[CGuid]&gt; | field_10 |

### SLdrChorusSettings
| Field | Type | Description |
| --- | --- | --- |
| `6E117FA7` | Float | field_0 |
| `84C76FC3` | [CMayaSpline] | field_4 |
| `3F67129F` | Float | field_34 |
| `80E7E009` | [CMayaSpline] | field_38 |
| `9371FA9B` | Float | field_68 |
| `4A47A853` | [CMayaSpline] | field_6C |
| `AEFAA2B7` | Float | field_9C |
| `CB39B71F` | [CMayaSpline] | field_A0 |

### SLdrCinematicCameraSettings
| Field | Type | Description |
| --- | --- | --- |
| `2B9F834D` | Bool | field_0 |
| `E0F823FC` | Bool | field_1 |
| `40B1A1D5` | Bool | field_2 |
| `16BDE173` | Bool | field_3 |
| `B066904C` | Bool | field_4 |
| `628BD43B` | Bool | field_5 |
| `ACBF019C` | Bool | field_6 |
| `69D6E80B` | Bool | field_7 |
| `618A4427` | Bool | field_8 |
| `509A6312` | Bool | field_9 |
| `13818A9F` | Bool | field_A |
| `03FF9143` | Bool | field_B |
| `6005CCCD` | Float | field_C |

### SLdrCinematicCameraShot
| Field | Type | Description |
| --- | --- | --- |
| `509ABD8C` | Bool | field_0 |
| `2E79E0E2` | Bool | field_1 |

### SLdrCinematicSkipHandler
| Field | Type | Description |
| --- | --- | --- |
| `429C881F` | Float | field_0 |
| `0AA781CC` | Bool | field_4 |
| `F88668D1` | Bool | field_5 |
| `ADD6FF88` | Float | field_8 |

### SLdrCircle
| Field | Type | Description |
| --- | --- | --- |
| `E25FF5C0` | Float | field_0 |

### SLdrClingPathControl
| Field | Type | Description |
| --- | --- | --- |
| `2B07921A` | [SLdrMaterialType](#sldrmaterialtype) | field_0 |
| `F71E794D` | [SLdrWorldType](#sldrworldtype) | field_4 |
| `25E2D3AF` | Bool | field_8 |
| `EB921831` | Float | field_C |
| `FFF1806C` | [enum_10014b3c](#enum_10014b3c) | field_10 |

### SLdrCollisionBehaviors
| Field | Type | Description |
| --- | --- | --- |
| `E0A3D9F4` | Bool | field_0 |
| `12F2F087` | Bool | field_1 |
| `E6AF4ACD` | Bool | field_2 |
| `598E940D` | Bool | field_3 |
| `FE1F5084` | Bool | field_4 |
| `E0F3A477` | Bool | field_5 |
| `E8221478` | Bool | field_6 |
| `45B1518B` | Bool | field_7 |
| `A988603C` | Bool | field_8 |

### SLdrCollisionData
| Field | Type | Description |
| --- | --- | --- |
| `E4057C0C` | Bool | field_0 |
| `3EC9DA96` | Bool | field_1 |
| `6E1F1C51` | Bool | field_2 |
| `FF10D21A` | Bool | field_3 |
| `7483BD3A` | Bool | field_4 |
| `9CB017D3` | Bool | field_5 |
| `F82DED58` | [enum_1007a31c](#enum_1007a31c) | field_8 |
| `6B4EF1DB` | [enum_10079200](#enum_10079200) | field_C |
| `E420CE69` | Float | field_10 |
| `02F59075` | [SLdrRuleSetData](#sldrrulesetdata) | field_14 |
| `C8808402` | [SLdrRuleSetData](#sldrrulesetdata) | field_20 |
| `4FBD2EAD` | Float | field_2C |
| `574B11B6` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_30 |
| `4C3CE4AC` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_3D |
| `AA86A065` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_4A |
| `B417A6B3` | [SLdrCollisionBehaviors](#sldrcollisionbehaviors) | field_57 |
| `EA5536F5` | [SLdrCollisionBehaviors](#sldrcollisionbehaviors) | field_60 |
| `5D6DEFE1` | Bool | field_69 |
| `10ECECAF` | [String] | field_6C |
| `78D2E9A7` | Bool | field_78 |
| `0272C37A` | Bool | field_79 |
| `7503E879` | Bool | field_7A |
| `EDC18221` | Bool | field_7B |
| `B18F2072` | [SLdrMaterialType](#sldrmaterialtype) | field_7C |
| `4346710D` | [SLdrWorldType](#sldrworldtype) | field_80 |

### SLdrCollisionFilters
| Field | Type | Description |
| --- | --- | --- |
| `C655987F` | Bool | field_0 |
| `EE5EAADD` | Bool | field_1 |
| `843169FF` | Bool | field_2 |
| `D8A62B62` | Bool | field_3 |
| `D96C0A19` | Bool | field_4 |
| `0F506F07` | Bool | field_5 |
| `B9280E86` | Bool | field_6 |
| `4ED1D399` | Bool | field_7 |
| `F9BD58C9` | Bool | field_8 |
| `17B07E16` | Bool | field_9 |
| `09CB4984` | Bool | field_A |
| `6B51C902` | Bool | field_B |
| `0A0BA1A3` | Bool | field_C |

### SLdrColorModifier
| Field | Type | Description |
| --- | --- | --- |
| `A3FBF12B` | [enum_10065094](#enum_10065094) | field_0 |
| `8133A24B` | [CColor4f] | field_4 |
| `D968BD8E` | [CColor4f] | field_14 |
| `34D88FEF` | [CMayaSpline] | field_24 |
| `B7BF28FD` | [SLdrColorModifierOptions](#sldrcolormodifieroptions) | field_54 |

### SLdrColorModifierOptions
| Field | Type | Description |
| --- | --- | --- |
| `E4C9CD3E` | Bool | field_0 |
| `47A9B8F4` | Bool | field_1 |
| `E000181C` | Bool | field_2 |
| `CB494ABC` | Bool | field_3 |

### SLdrCommandControls
| Field | Type | Description |
| --- | --- | --- |
| `D972289E` | [enum_100071d8](#enum_100071d8) | field_0 |
| `62407650` | [SLdrPhysicalControl](#sldrphysicalcontrol) | field_4 |
| `FB3C8032` | [enum_10007218](#enum_10007218) | field_38 |
| `A901D9E5` | [SLdrPhysicalControl](#sldrphysicalcontrol) | field_3C |
| `887DB63E` | [enum_100072c0](#enum_100072c0) | field_70 |
| `3AD4D322` | [enum_100072c0](#enum_100072c0) | field_74 |
| `870FD4AD` | [enum_10007350](#enum_10007350) | field_78 |
| `DFBD4E2F` | [List]&lt;[SLdrPhysicalControl](#sldrphysicalcontrol)&gt; | field_7C |

### SLdrConstantSpeedSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `EADCFE44` | Float | field_0 |

### SLdrControlCommand
| Field | Type | Description |
| --- | --- | --- |
| `A4489958` | [enum_10013ca8](#enum_10013ca8) | field_0 |

### SLdrControllerAction
| Field | Type | Description |
| --- | --- | --- |
| `160C63CD` | Uint32 | field_0 |
| `7BA8A161` | [SLdrControlCommand](#sldrcontrolcommand) | field_4 |
| `8F3BA3DD` | Bool | field_8 |
| `E98D8918` | Bool | field_9 |
| `6E078710` | Float | field_C |

### SLdrControllerCameraDataInput
| Field | Type | Description |
| --- | --- | --- |
| `E95D6ABD` | Float | field_0 |
| `069CCA3D` | Float | field_4 |
| `3156A179` | [SLdrControlCommand](#sldrcontrolcommand) | field_8 |
| `C2620806` | [SLdrControlCommand](#sldrcontrolcommand) | field_C |
| `C3F607B7` | Bool | field_10 |
| `08A7BA95` | [CObjectId] | field_14 |
| `06462085` | [CObjectId] | field_24 |

### SLdrConvergence
| Field | Type | Description |
| --- | --- | --- |
| `9888F01B` | [Property] | field_0 |
| `B81E8DAC` | [SLdrConvergenceTuner](#sldrconvergencetuner) | field_8 |

### SLdrConvergenceTuner
| Field | Type | Description |
| --- | --- | --- |
| `D5DC8112` | Bool | field_0 |
| `0BB4B38A` | [String] | field_4 |
| `3713029E` | Float | field_10 |

### SLdrConveyorModifier
| Field | Type | Description |
| --- | --- | --- |
| `85842DE8` | Float | field_0 |
| `BB31FDEB` | [CVector3f] | field_4 |
| `99C4D2C0` | Bool | field_10 |
| `6382B867` | Bool | field_11 |
| `4D99B459` | Float | field_14 |
| `6D3F1759` | [CMayaSpline] | field_18 |
| `F4A7202C` | Float | field_48 |
| `A4B0B2D2` | [CMayaSpline] | field_4C |
| `5F77E979` | String | field_7C |
| `B946AE62` | String | field_88 |
| `E8E06BB1` | Float | field_94 |

### SLdrCounter
| Field | Type | Description |
| --- | --- | --- |
| `C44C38AD` | Uint32 | field_0 |
| `CE73C1A7` | Uint32 | field_4 |
| `9335598B` | [enum_10065560](#enum_10065560) | field_8 |
| `6F56317C` | [List]&lt;Int32&gt; | field_C |

### SLdrCreature
| Field | Type | Description |
| --- | --- | --- |
| `EA11A0B7` | [List]&lt;[Property]&gt; | field_0 |
| `20ACF7A5` | Bool | field_C |

### SLdrCreatureRuleSetData
This struct does not have any fields

### SLdrCreatureSCAHandler
| Field | Type | Description |
| --- | --- | --- |
| `6B200F5A` | Bool | field_0 |
| `3E54BF05` | Bool | field_1 |
| `50B093CC` | [CVector3f] | field_4 |
| `8EAFE958` | Float | field_10 |

### SLdrCredits
| Field | Type | Description |
| --- | --- | --- |
| `0AC2F4B9` | Float | field_0 |
| `1F152FBA` | Uint32 | field_4 |
| `55886D2C` | Float | field_8 |
| `835E93F6` | Float | field_C |
| `EC90CA34` | Float | field_10 |
| `181A84F0` | Float | field_14 |
| `34BFCF70` | Float | field_18 |
| `B06DBC71` | Float | field_1C |
| `B3BE8DFC` | [CObjectId] | field_20 |
| `CF15B4EB` | Float | field_30 |
| `0C329596` | Float | field_34 |

### SLdrCustomInterpolation
| Field | Type | Description |
| --- | --- | --- |
| `4469C7F0` | [SLdrCameraInterpolation](#sldrcamerainterpolation) | field_0 |

### SLdrCylinderBoxShape
| Field | Type | Description |
| --- | --- | --- |
| `576DE278` | Float | field_0 |
| `B27D1DE1` | Float | field_4 |
| `6A2A4B01` | [CVector3f] | field_8 |

### SLdrDSP
| Field | Type | Description |
| --- | --- | --- |
| `1B860315` | [SLdrAcousticBounds](#sldracousticbounds) | field_0 |
| `254A6ECD` | [enum_10066324](#enum_10066324) | field_10 |
| `5CE893CD` | Bool | field_14 |
| `5B4D28F0` | Bool | field_15 |
| `066E63E6` | Bool | field_16 |
| `66B463F1` | Float | field_18 |
| `FA1B6C24` | [enum_1006349c](#enum_1006349c) | field_1C |
| `1C33F167` | [SLdrChannelContributionModifiers](#sldrchannelcontributionmodifiers) | field_20 |
| `E7DBF3EE` | [enum_10066354](#enum_10066354) | field_30 |
| `78E88DD4` | [SLdrReverbSettings](#sldrreverbsettings) | field_34 |
| `EE0E5BAB` | [SLdrChorusSettings](#sldrchorussettings) | field_170 |
| `DB9679C1` | [SLdrDelaySettings](#sldrdelaysettings) | field_240 |

### SLdrDamageInfo
| Field | Type | Description |
| --- | --- | --- |
| `C23E4F88` | [enum_10095418](#enum_10095418) | field_0 |
| `D6B16D45` | Float | field_4 |
| `408D70C8` | Float | field_8 |
| `339DBEB2` | Float | field_C |
| `1DFE676E` | Float | field_10 |
| `21D90D2F` | Float | field_14 |
| `0E2CB7DC` | Uint32 | field_18 |
| `4AF8CB81` | [enum_100953f8](#enum_100953f8) | field_1C |
| `109EF7FF` | Bool | field_20 |
| `FBC0DB3E` | Bool | field_21 |

### SLdrDamageTypeFlags
| Field | Type | Description |
| --- | --- | --- |
| `7A3FF726` | Bool | field_0 |
| `301B50E3` | Bool | field_1 |
| `FBCF6EFA` | Bool | field_2 |
| `2869D58A` | Bool | field_3 |
| `EBFADC6C` | Bool | field_4 |
| `FF6F2B58` | Bool | field_5 |
| `8FCA823B` | Bool | field_6 |
| `3E15C0AB` | Bool | field_7 |
| `355F5BA0` | Bool | field_8 |
| `29C22A52` | Bool | field_9 |
| `12982448` | Bool | field_A |
| `2122D737` | Bool | field_B |
| `6D43A1F0` | Bool | field_C |
| `33B7E7D6` | Bool | field_D |
| `2A8CBDAD` | Bool | field_E |
| `A79DDDEF` | Bool | field_F |
| `622E2F83` | Bool | field_10 |
| `048DF4BA` | Bool | field_11 |
| `145D747A` | Bool | field_12 |
| `EE4811FE` | Bool | field_13 |
| `B2463726` | Bool | field_14 |
| `9F044225` | Bool | field_15 |
| `66058338` | Bool | field_16 |
| `06A8DCD0` | Bool | field_17 |
| `DA1F0F5D` | Bool | field_18 |
| `03C32D52` | Bool | field_19 |
| `FA43D040` | Bool | field_1A |
| `B643196B` | Bool | field_1B |

### SLdrDamageTypeRuleSetData
This struct does not have any fields

### SLdrDamageVulnerability
| Field | Type | Description |
| --- | --- | --- |
| `33710195` | [SLdrDamageTypeFlags](#sldrdamagetypeflags) | field_0 |
| `1DAA20FA` | [SLdrDamageTypeFlags](#sldrdamagetypeflags) | field_1C |

### SLdrDebugCameraControls
| Field | Type | Description |
| --- | --- | --- |
| `69653C1F` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `DF95895C` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `C1097882` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `297D5F0B` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `85F51745` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |
| `5715BECC` | [SLdrCommandControls](#sldrcommandcontrols) | field_2A8 |
| `B7A3B508` | [SLdrCommandControls](#sldrcommandcontrols) | field_330 |
| `8A4B64C7` | [SLdrCommandControls](#sldrcommandcontrols) | field_3B8 |
| `A333CAAE` | [SLdrCommandControls](#sldrcommandcontrols) | field_440 |
| `7C01CE2E` | [SLdrCommandControls](#sldrcommandcontrols) | field_4C8 |
| `B8F66426` | [SLdrCommandControls](#sldrcommandcontrols) | field_550 |
| `5B066D07` | [SLdrCommandControls](#sldrcommandcontrols) | field_5D8 |
| `29879B11` | [SLdrCommandControls](#sldrcommandcontrols) | field_660 |
| `683E1CD4` | [SLdrCommandControls](#sldrcommandcontrols) | field_6E8 |

### SLdrDebugControls
| Field | Type | Description |
| --- | --- | --- |
| `72B8B52F` | [SLdrDebugMenuControls](#sldrdebugmenucontrols) | field_0 |
| `2AC5565D` | [SLdrDebugCameraControls](#sldrdebugcameracontrols) | field_880 |
| `E45684D6` | [SLdrDebugMiscControls](#sldrdebugmisccontrols) | field_FF0 |

### SLdrDebugMenuControls
| Field | Type | Description |
| --- | --- | --- |
| `FA608873` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `5C4551EA` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `811FBEF6` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `18628AD5` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `3B99E623` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |
| `AB38C0A3` | [SLdrCommandControls](#sldrcommandcontrols) | field_2A8 |
| `9F380DFA` | [SLdrCommandControls](#sldrcommandcontrols) | field_330 |
| `6ABD1DFA` | [SLdrCommandControls](#sldrcommandcontrols) | field_3B8 |
| `8156C06A` | [SLdrCommandControls](#sldrcommandcontrols) | field_440 |
| `F1D38EA6` | [SLdrCommandControls](#sldrcommandcontrols) | field_4C8 |
| `0EE5F525` | [SLdrCommandControls](#sldrcommandcontrols) | field_550 |
| `D93AAFAF` | [SLdrCommandControls](#sldrcommandcontrols) | field_5D8 |
| `FA79FDBF` | [SLdrCommandControls](#sldrcommandcontrols) | field_660 |
| `4D4BE72F` | [SLdrCommandControls](#sldrcommandcontrols) | field_6E8 |
| `C232EBEE` | [SLdrCommandControls](#sldrcommandcontrols) | field_770 |
| `A3914E55` | [SLdrCommandControls](#sldrcommandcontrols) | field_7F8 |

### SLdrDebugMiscControls
| Field | Type | Description |
| --- | --- | --- |
| `FBB9AB39` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `B1890CA3` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `C810C502` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `9F87CF8E` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `2CB158A3` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |

### SLdrDelayDecreaseCameraDataInput
| Field | Type | Description |
| --- | --- | --- |
| `DD9598F7` | [Property] | field_0 |
| `1C1E645E` | Float | field_8 |
| `C61F6C3B` | [SLdrConvergence](#sldrconvergence) | field_C |

### SLdrDelaySettings
| Field | Type | Description |
| --- | --- | --- |
| `79989168` | Float | field_0 |
| `07732279` | [CMayaSpline] | field_4 |
| `3D2A2144` | Float | field_34 |
| `DC26D4C0` | [CMayaSpline] | field_38 |
| `C5ACF95B` | Float | field_68 |
| `C9CD34C4` | [CMayaSpline] | field_6C |
| `7DC20FE7` | Float | field_9C |
| `EC60C370` | [CMayaSpline] | field_A0 |

### SLdrDepthBiasOverride
| Field | Type | Description |
| --- | --- | --- |
| `BE93E7C3` | Float | field_0 |

### SLdrDialogPanel
| Field | Type | Description |
| --- | --- | --- |
| `9B698F8A` | [CObjectId] | field_0 |
| `0DAEFB48` | Bool | field_10 |
| `0CD37259` | [String] | field_14 |
| `E0B4E884` | [CMayaSpline] | field_20 |
| `48C7A124` | [enum_10065b90](#enum_10065b90) | field_50 |
| `764669BA` | [enum_10065bb8](#enum_10065bb8) | field_54 |
| `38D48823` | [enum_10065bd8](#enum_10065bd8) | field_58 |
| `971EB4D2` | [enum_10065c58](#enum_10065c58) | field_5C |
| `6553C290` | [enum_10065c08](#enum_10065c08) | field_60 |
| `726CCA3D` | [enum_10065c40](#enum_10065c40) | field_64 |
| `94124F45` | [CVector3f] | field_68 |

### SLdrDirectionalForceField
| Field | Type | Description |
| --- | --- | --- |
| `A999806E` | [CVector3f] | field_0 |
| `DAC18E54` | Bool | field_C |

### SLdrDirectionalIrradianceMap
| Field | Type | Description |
| --- | --- | --- |
| `7F2165F1` | [List]&lt;[CObjectId]&gt; | field_0 |
| `132FEDEC` | [List]&lt;[CVector3f]&gt; | field_C |

### SLdrDirectionalIrradianceProbes
| Field | Type | Description |
| --- | --- | --- |
| `6D5224FA` | Float | field_0 |
| `43DA9610` | [CObjectId] | field_4 |

### SLdrDisplacementFromCameraDataInput
| Field | Type | Description |
| --- | --- | --- |
| `E9558211` | [enum_1007d040](#enum_1007d040) | field_0 |
| `A651B3EA` | [enum_1007d040](#enum_1007d040) | field_4 |
| `9C961A62` | [enum_1007d080](#enum_1007d080) | field_8 |

### SLdrDynamicActorCollision
| Field | Type | Description |
| --- | --- | --- |
| `0B72D536` | Bool | field_0 |
| `24365EE9` | [SLdrGroundColliderParameters](#sldrgroundcolliderparameters) | field_4 |
| `E373159F` | Bool | field_C |
| `E89E1955` | Bool | field_D |
| `E064F139` | Float | field_10 |
| `2595C731` | Float | field_14 |
| `C0321D7C` | [enum_10014c94](#enum_10014c94) | field_18 |
| `050FD461` | [SLdrCylinderBoxShape](#sldrcylinderboxshape) | field_1C |
| `B2D9C843` | [SLdrSphereShape](#sldrsphereshape) | field_30 |
| `26553FC5` | Float | field_40 |
| `ECE87973` | Float | field_44 |
| `BC879BC8` | Bool | field_48 |
| `EDE5CCD2` | Bool | field_49 |

### SLdrDynamicActorControl
This struct does not have any fields

### SLdrDynamicLoadManager
This struct does not have any fields

### SLdrDynamicPullbackBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `A271E4C7` | Float | field_0 |
| `5E00F197` | Float | field_4 |
| `3B4AF9EA` | Float | field_8 |
| `EE452923` | Float | field_C |
| `27F64DEB` | Bool | field_10 |
| `837C62BD` | Bool | field_11 |
| `AC63907C` | Float | field_14 |

### SLdrEditorProperties
| Field | Type | Description |
| --- | --- | --- |
| `0C6657D8` | Bool | field_0 |
| `FEDFB637` | [SLdrTransform](#sldrtransform) | field_4 |

### SLdrEffect
| Field | Type | Description |
| --- | --- | --- |
| `AF601872` | [CObjectId] | field_0 |
| `91FBD957` | Bool | field_10 |
| `5FB19AEA` | Bool | field_11 |
| `05B34082` | Bool | field_12 |
| `40A4AE1F` | Bool | field_13 |
| `E5614E35` | Bool | field_14 |
| `EA5CADCD` | Uint32 | field_18 |
| `EFDB6D35` | Float | field_1C |
| `D24C340F` | [SLdrModelLightingData](#sldrmodellightingdata) | field_20 |

### SLdrEndGame
This struct does not have any fields

### SLdrEndLevel
| Field | Type | Description |
| --- | --- | --- |
| `EAE34C4C` | [enum_10066998](#enum_10066998) | field_0 |
| `A9D57A7D` | [enum_100669b8](#enum_100669b8) | field_4 |
| `B40FEB9C` | Bool | field_8 |

### SLdrEulerOrientationSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `EE769E36` | [CMayaSpline] | field_0 |
| `04A40B73` | [CMayaSpline] | field_30 |
| `038AEEFF` | [CMayaSpline] | field_60 |
| `F795D588` | [enum_1007e7f0](#enum_1007e7f0) | field_90 |

### SLdrExplosion
| Field | Type | Description |
| --- | --- | --- |
| `1745C038` | [SLdrExplosionData](#sldrexplosiondata) | field_0 |

### SLdrExplosionData
| Field | Type | Description |
| --- | --- | --- |
| `BF7DA848` | [CObjectId] | field_0 |
| `91AE3A03` | [CObjectId] | field_10 |
| `543B17AB` | [CColor4f] | field_20 |
| `8A5B3E91` | Bool | field_30 |
| `F4DF8009` | Bool | field_31 |
| `5C91AC83` | Bool | field_32 |

### SLdrExtras
This struct does not have any fields

### SLdrExtrasCategory
This struct does not have any fields

### SLdrExtrasType
This struct does not have any fields

### SLdrFOVInputBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `BC29D2F3` | [Property] | field_0 |
| `DB4DAC25` | [CMayaSpline] | field_8 |

### SLdrFOVInterpolationMethod
| Field | Type | Description |
| --- | --- | --- |
| `482167B4` | [enum_1005b0c0](#enum_1005b0c0) | field_0 |
| `4D172D8C` | [SLdrInterpolationMethod](#sldrinterpolationmethod) | field_4 |

### SLdrFSMData
| Field | Type | Description |
| --- | --- | --- |
| `05AE682F` | [CObjectId] | field_0 |

### SLdrFakePlayerControls
| Field | Type | Description |
| --- | --- | --- |
| `0720D40B` | Float | field_0 |
| `E1AC6A58` | Float | field_4 |
| `C81BBD2A` | Float | field_8 |
| `286170B3` | Float | field_C |

### SLdrFiniteStateMachine
| Field | Type | Description |
| --- | --- | --- |
| `EA36F631` | [CObjectId] | field_0 |

### SLdrFlashTextureSwapper
| Field | Type | Description |
| --- | --- | --- |
| `97F2B847` | [List]&lt;[CObjectId]&gt; | field_0 |

### SLdrFlyerMovementConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `DD9BE763` | [enum_1007e0d8](#enum_1007e0d8) | field_0 |
| `9C88FBDF` | [enum_1007e0f8](#enum_1007e0f8) | field_4 |
| `E6391FCE` | Bool | field_8 |

### SLdrFlyingPickupData
| Field | Type | Description |
| --- | --- | --- |
| `4C71EB90` | Float | field_0 |
| `2029E5C4` | Float | field_4 |
| `1010C94F` | Float | field_8 |
| `18DF7169` | [CObjectId] | field_C |
| `B39A197E` | [CObjectId] | field_1C |
| `66E0C950` | [CObjectId] | field_2C |
| `3C79EC22` | [String] | field_3C |

### SLdrFlyingPickupEffect
| Field | Type | Description |
| --- | --- | --- |
| `4652B506` | [SLdrFlyingPickupData](#sldrflyingpickupdata) | field_0 |
| `B2078E8A` | [CMayaSpline] | field_48 |
| `AA99F560` | [CObjectId] | field_78 |

### SLdrFogVolume
| Field | Type | Description |
| --- | --- | --- |
| `A221FEDB` | [CObjectId] | field_0 |
| `BE6878BB` | [CMayaSpline] | field_10 |
| `D3686786` | [CColor4f] | field_40 |
| `D9538D41` | [SLdrFogVolumeTexture](#sldrfogvolumetexture) | field_50 |
| `5A6F13D5` | [SLdrFogVolumeFlags](#sldrfogvolumeflags) | field_7C |

### SLdrFogVolumeFlags
| Field | Type | Description |
| --- | --- | --- |
| `9D4EFEB3` | Bool | field_0 |
| `9EF644AE` | Bool | field_1 |

### SLdrFogVolumeTexture
| Field | Type | Description |
| --- | --- | --- |
| `5F969FD8` | [SLdrFogVolumeTileOptions](#sldrfogvolumetileoptions) | field_0 |
| `ED8A322F` | [CVector3f] | field_4 |
| `E94F91AD` | [CVector3f] | field_10 |
| `018A6145` | [CObjectId] | field_1C |

### SLdrFogVolumeTileOptions
| Field | Type | Description |
| --- | --- | --- |
| `5804E374` | Bool | field_0 |
| `C0DF204D` | Bool | field_1 |
| `0720EA98` | Bool | field_2 |

### SLdrFollowDynamicPathJump
| Field | Type | Description |
| --- | --- | --- |
| `E78FFFEB` | [List]&lt;Float&gt; | field_0 |
| `CF4A795B` | Float | field_C |
| `E0A72962` | Float | field_10 |
| `96F547A0` | Bool | field_14 |
| `8B425A48` | Bool | field_15 |
| `B1F77C65` | Uint32 | field_18 |

### SLdrFollowDynamicPathSpline
| Field | Type | Description |
| --- | --- | --- |
| `B79EF32E` | [CVector3f] | field_0 |
| `A24A04FD` | [CVector3f] | field_C |
| `3FC379D5` | Float | field_18 |
| `D03DF880` | Float | field_1C |
| `08D2EA02` | Float | field_20 |

### SLdrFollowerDriverData
This struct does not have any fields

### SLdrFrameGroundPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `3AA89B5C` | Float | field_0 |
| `E0594533` | Float | field_4 |
| `438C3CB2` | Bool | field_8 |
| `5C28C384` | [enum_1007c078](#enum_1007c078) | field_C |

### SLdrFrameTargetsData
| Field | Type | Description |
| --- | --- | --- |
| `35176679` | Float | field_0 |
| `CE12FD30` | Bool | field_4 |
| `7C06946A` | Float | field_8 |

### SLdrFrameTargetsPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `05D91B7A` | Bool | field_0 |
| `C4DB6454` | Bool | field_1 |
| `E695F0E1` | [SLdrFrameTargetsData](#sldrframetargetsdata) | field_4 |

### SLdrFramingEnforcementBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `CD3477E8` | Bool | field_0 |
| `8C80B83B` | Float | field_4 |
| `83C494EC` | Bool | field_8 |

### SLdrFuseBomb
| Field | Type | Description |
| --- | --- | --- |
| `F11CB344` | Bool | field_0 |
| `3F52FEB1` | Bool | field_1 |
| `D73D8CE0` | Bool | field_2 |
| `EE626945` | Float | field_4 |

### SLdrGameControls
| Field | Type | Description |
| --- | --- | --- |
| `0BB87142` | [SLdrPlayerMovementControls](#sldrplayermovementcontrols) | field_0 |
| `8BF97C46` | [SLdrMapControls](#sldrmapcontrols) | field_908 |
| `C7357581` | [SLdrMiscControls](#sldrmisccontrols) | field_1298 |
| `7742A311` | [SLdrDebugControls](#sldrdebugcontrols) | field_1870 |

### SLdrGameHintData
| Field | Type | Description |
| --- | --- | --- |
| `8AB8FD40` | Uint32 | field_0 |

### SLdrGameSurfacePlane
This struct does not have any fields

### SLdrGameSurfaceSphere
This struct does not have any fields

### SLdrGameSurfaceTrapezoid
| Field | Type | Description |
| --- | --- | --- |
| `5268F90A` | Float | field_0 |

### SLdrGenerateDeleterOptions
| Field | Type | Description |
| --- | --- | --- |
| `AC3723C4` | Bool | field_0 |
| `EF00552F` | Float | field_4 |
| `23983F16` | Bool | field_8 |
| `52ACE1F2` | Bool | field_9 |

### SLdrGeneratedCameraTarget
This struct does not have any fields

### SLdrGenerator
| Field | Type | Description |
| --- | --- | --- |
| `EFAD2E19` | Uint32 | field_0 |
| `4E4AAD5F` | Uint32 | field_4 |
| `30662030` | Bool | field_8 |
| `71AD7014` | Bool | field_9 |
| `C06E95CF` | Bool | field_A |
| `BFEE69C1` | Bool | field_B |
| `9B3A0746` | Bool | field_C |
| `7BAC0909` | Bool | field_D |
| `C6EFB40C` | [enum_10067738](#enum_10067738) | field_10 |
| `815433C9` | Bool | field_14 |
| `514A953A` | [CVector3f] | field_18 |
| `CF334EBA` | Float | field_24 |
| `5595D03A` | Float | field_28 |
| `C1B93338` | Bool | field_2C |
| `C2ED71DC` | Bool | field_2D |
| `83692111` | [SLdrGenerateDeleterOptions](#sldrgeneratedeleteroptions) | field_30 |

### SLdrGeneratorDeleter
| Field | Type | Description |
| --- | --- | --- |
| `EF66F870` | [SLdrGenerateDeleterOptions](#sldrgeneratedeleteroptions) | field_0 |

### SLdrGenericActorSCAHandler
| Field | Type | Description |
| --- | --- | --- |
| `1C980DD3` | Bool | field_0 |
| `1FFAC337` | Bool | field_1 |
| `73DE4C3F` | Bool | field_2 |
| `7145E239` | Bool | field_3 |
| `C9163C5C` | [CVector3f] | field_4 |
| `96C26A9D` | Float | field_10 |

### SLdrGrabThrow
| Field | Type | Description |
| --- | --- | --- |
| `7434B336` | Bool | field_0 |
| `B68A64F5` | Bool | field_1 |
| `C47FB49C` | Bool | field_2 |
| `F0FEE612` | Bool | field_3 |
| `9CC19F1C` | Bool | field_4 |
| `337A49F3` | [SLdrExplosionData](#sldrexplosiondata) | field_8 |
| `6072BBDE` | Bool | field_3C |
| `3A1768BA` | [enum_10067aac](#enum_10067aac) | field_40 |
| `B73A4A83` | Float | field_44 |
| `549FD8C6` | Float | field_48 |
| `68AB7837` | Float | field_4C |
| `775E7444` | Float | field_50 |
| `6B7EC2A2` | [SLdrExplosionData](#sldrexplosiondata) | field_54 |
| `5C726CD7` | [CObjectId] | field_88 |
| `C0F79DC7` | [SLdrHeldObjectSounds](#sldrheldobjectsounds) | field_98 |
| `14A8DC8B` | Float | field_E0 |
| `B571E1DF` | Bool | field_E4 |
| `70088494` | Bool | field_E5 |
| `922DBCC2` | Bool | field_E6 |
| `36C7B337` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_E7 |
| `5F2E75ED` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_F4 |
| `A2CDAA38` | [SLdrFlyingPickupData](#sldrflyingpickupdata) | field_104 |
| `D0F4C3E3` | Float | field_14C |
| `AA16996C` | [CObjectId] | field_150 |
| `D7CF01F3` | Bool | field_160 |

### SLdrGrabbable
| Field | Type | Description |
| --- | --- | --- |
| `AC63B691` | [SLdrGrabbableData](#sldrgrabbabledata) | field_0 |
| `E7532EF2` | Bool | field_38 |

### SLdrGrabbableData
| Field | Type | Description |
| --- | --- | --- |
| `EB91AA38` | Float | field_0 |
| `D9563501` | Float | field_4 |
| `0A6FB604` | Float | field_8 |
| `40F7EAFA` | Float | field_C |
| `D321EE11` | Bool | field_10 |
| `475A5DB4` | [CVector3f] | field_14 |
| `5CB6C921` | Bool | field_20 |
| `0B0B040A` | Bool | field_21 |
| `F0E4FFD6` | Bool | field_22 |
| `BD753D31` | [CObjectId] | field_24 |
| `0B1237CC` | Bool | field_34 |

### SLdrGrabbableGenerator
| Field | Type | Description |
| --- | --- | --- |
| `15BCBC9E` | Float | field_0 |
| `FF34579C` | Uint32 | field_4 |
| `AEB7B5AD` | Bool | field_8 |
| `8BC62578` | Bool | field_9 |
| `8AD60FB0` | Float | field_C |
| `FD8E356E` | [CObjectId] | field_10 |
| `ED55A7E4` | Bool | field_20 |
| `44B8D7D2` | Bool | field_21 |

### SLdrGraphicalTransition
| Field | Type | Description |
| --- | --- | --- |
| `53040B06` | [enum_10067f78](#enum_10067f78) | field_0 |
| `9AD0FDED` | Bool | field_4 |

### SLdrGroundColliderParameters
| Field | Type | Description |
| --- | --- | --- |
| `CD906B3D` | Float | field_0 |
| `1748A9CF` | Float | field_4 |

### SLdrGroupSpawn
| Field | Type | Description |
| --- | --- | --- |
| `63721B43` | Bool | field_0 |
| `3AA7B003` | [SLdrSpawnOverride](#sldrspawnoverride) | field_4 |

### SLdrHUDAnchor
| Field | Type | Description |
| --- | --- | --- |
| `F00F1370` | [CVector3f] | field_0 |
| `A272C8A4` | [enum_10068690](#enum_10068690) | field_C |
| `41874265` | [String] | field_10 |

### SLdrHUDFadeDetector
| Field | Type | Description |
| --- | --- | --- |
| `46E8DB56` | Bool | field_0 |
| `0F15E2AF` | Bool | field_1 |

### SLdrHealth
| Field | Type | Description |
| --- | --- | --- |
| `D0AEF6A4` | Bool | field_0 |
| `39CB61ED` | Float | field_4 |
| `1A7AC0B8` | [SLdrDamageVulnerability](#sldrdamagevulnerability) | field_8 |
| `680F7045` | Bool | field_40 |
| `BE064039` | Bool | field_41 |

### SLdrHealthData
| Field | Type | Description |
| --- | --- | --- |
| `D0D505E5` | Uint32 | field_0 |
| `A3EC1B86` | [SLdrDamageVulnerability](#sldrdamagevulnerability) | field_4 |
| `226A01F9` | Bool | field_3C |
| `B07AB6CC` | [List]&lt;[SLdrDamageVulnerability](#sldrdamagevulnerability)&gt; | field_40 |

### SLdrHeldObjectSounds
| Field | Type | Description |
| --- | --- | --- |
| `31E298BE` | [CObjectId] | field_0 |
| `DB8784C3` | [CObjectId] | field_10 |
| `EC4A1176` | [CObjectId] | field_20 |
| `B3E81FDA` | [CObjectId] | field_30 |
| `E7B09D6F` | Float | field_40 |
| `5229A663` | Float | field_44 |

### SLdrHorizontalLeadPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `23B7CBE5` | [CMayaSpline] | field_0 |
| `7070C435` | Bool | field_30 |
| `C990754B` | Float | field_34 |
| `7D59DB41` | Float | field_38 |
| `2683B8CF` | Bool | field_3C |

### SLdrHotCoals
| Field | Type | Description |
| --- | --- | --- |
| `120134A5` | [List]&lt;[CObjectId]&gt; | field_0 |
| `74318DE1` | [SLdrModelLightingData](#sldrmodellightingdata) | field_C |
| `B325FC59` | [CObjectId] | field_28 |
| `C500331A` | [CObjectId] | field_38 |
| `1425038D` | [CObjectId] | field_48 |
| `D62392D4` | Float | field_58 |
| `9FCFAF3E` | Float | field_5C |
| `81EBC74C` | Float | field_60 |
| `AE4CC299` | Float | field_64 |
| `1285FEED` | Float | field_68 |
| `C34666E4` | [CColor4f] | field_6C |
| `1873EB0F` | [CColor4f] | field_7C |
| `9F0C2450` | [CColor4f] | field_8C |
| `29DFB181` | [CMayaSpline] | field_9C |
| `25508EA0` | [CObjectId] | field_CC |
| `53A54841` | [CObjectId] | field_DC |
| `CC93DF0A` | Bool | field_EC |

### SLdrHurlParameters
| Field | Type | Description |
| --- | --- | --- |
| `03E3E558` | Float | field_0 |
| `EEAC5D4C` | Float | field_4 |

### SLdrHurlPlayerForceField
| Field | Type | Description |
| --- | --- | --- |
| `6BDE3AE1` | Float | field_0 |
| `0CE85E67` | [enum_1007da8c](#enum_1007da8c) | field_4 |
| `6C1CCB8F` | Bool | field_8 |
| `F4D66988` | Bool | field_9 |
| `B3D6D06B` | Bool | field_A |
| `0519DDA3` | Bool | field_B |

### SLdrIceCubeSlingParameters
| Field | Type | Description |
| --- | --- | --- |
| `095448FE` | Bool | field_0 |
| `E1F0D418` | Float | field_4 |
| `943CE085` | Float | field_8 |
| `2F51CCA1` | Float | field_C |
| `C22C7CEF` | Uint32 | field_10 |

### SLdrIceCubeSlingSequence
| Field | Type | Description |
| --- | --- | --- |
| `127985EC` | [List]&lt;[SLdrIceCubeSlingParameters](#sldricecubeslingparameters)&gt; | field_0 |

### SLdrImpostor
| Field | Type | Description |
| --- | --- | --- |
| `B07D4C5C` | Bool | field_0 |
| `3DB03554` | [enum_100689e8](#enum_100689e8) | field_4 |
| `752651D9` | [enum_100689a0](#enum_100689a0) | field_8 |
| `046B91C2` | Float | field_C |
| `FF72C03D` | Bool | field_10 |
| `8FDD9516` | Bool | field_11 |
| `A18EB191` | [String] | field_14 |
| `47A81ADF` | Uint32 | field_20 |
| `AA73418E` | Uint32 | field_24 |
| `1F780C1D` | [enum_100689c0](#enum_100689c0) | field_28 |
| `BD182D31` | Bool | field_2C |

### SLdrImpulseDriver
| Field | Type | Description |
| --- | --- | --- |
| `408486FC` | [SLdrImpulseDriverImpulseData](#sldrimpulsedriverimpulsedata) | field_0 |
| `A854119E` | [SLdrImpulseDriverImpulseData](#sldrimpulsedriverimpulsedata) | field_18 |
| `1F97EDBD` | Float | field_30 |
| `058E430E` | Float | field_34 |
| `2F50EEE0` | Float | field_38 |
| `62C95CD1` | Float | field_3C |
| `DF5A1627` | Float | field_40 |
| `6E977B11` | Float | field_44 |
| `068EB0B2` | Bool | field_48 |
| `EE5CB877` | Bool | field_49 |
| `78393680` | Bool | field_4A |
| `9954EC72` | Bool | field_4B |
| `6D2EE98B` | [SLdrImpulseDriverSoundData](#sldrimpulsedriversounddata) | field_4C |
| `4775E0D3` | [SLdrImpulseDriverSoundData](#sldrimpulsedriversounddata) | field_54 |
| `B45958F0` | [SLdrImpulseDriverSoundData](#sldrimpulsedriversounddata) | field_5C |

### SLdrImpulseDriverImpulseData
| Field | Type | Description |
| --- | --- | --- |
| `9D46859F` | Float | field_0 |
| `2E09F168` | Float | field_4 |
| `12DE618F` | Float | field_8 |
| `C4D6AC6E` | Float | field_C |
| `F69D34CF` | Float | field_10 |
| `FF8A263C` | Float | field_14 |

### SLdrImpulseDriverSoundData
| Field | Type | Description |
| --- | --- | --- |
| `438E6319` | Uint32 | field_0 |
| `26121E34` | Float | field_4 |

### SLdrInterpolationMethod
| Field | Type | Description |
| --- | --- | --- |
| `9101B475` | [enum_1005afd8](#enum_1005afd8) | field_0 |
| `F3B980BD` | [CMayaSpline] | field_4 |
| `03DD8D35` | Float | field_34 |
| `FBF39366` | Float | field_38 |
| `716734A4` | Float | field_3C |

### SLdrInterpolationOptions
| Field | Type | Description |
| --- | --- | --- |
| `1BDAC22E` | Bool | field_0 |
| `9757C8F5` | Bool | field_1 |
| `C6023D4F` | Bool | field_2 |
| `BF385824` | Bool | field_3 |
| `E63FD530` | Bool | field_4 |
| `40DA8304` | Bool | field_5 |
| `C743A088` | Float | field_8 |
| `3A563699` | Float | field_C |

### SLdrInventoryItem
| Field | Type | Description |
| --- | --- | --- |
| `7567F41F` | [SLdrPlayerItem](#sldrplayeritem) | field_0 |
| `ED712BB0` | Uint32 | field_4 |

### SLdrKnockbackProceduralData
| Field | Type | Description |
| --- | --- | --- |
| `7E8375A7` | Float | field_0 |
| `97191814` | Float | field_4 |
| `8B78A67A` | Float | field_8 |

### SLdrLevelDarkener
| Field | Type | Description |
| --- | --- | --- |
| `9942DE35` | [CColor4f] | field_0 |
| `5B667B13` | Float | field_10 |
| `65C4EDA5` | Bool | field_14 |

### SLdrLightAngleAttenuation
| Field | Type | Description |
| --- | --- | --- |
| `635DFCC7` | Float | field_0 |
| `B0A71764` | Float | field_4 |

### SLdrLightAngleAttenuationDynamic
| Field | Type | Description |
| --- | --- | --- |
| `A306F8B6` | [CMayaSpline] | field_0 |
| `CA7E1D6F` | [CMayaSpline] | field_30 |

### SLdrLightColors
| Field | Type | Description |
| --- | --- | --- |
| `8F421907` | [CColor4f] | field_0 |
| `C3B735B9` | [CColor4f] | field_10 |
| `E8C8699C` | [CColor4f] | field_20 |

### SLdrLightDistanceAttenuation
| Field | Type | Description |
| --- | --- | --- |
| `174C8ABC` | Uint32 | field_0 |
| `E5CEAF7C` | Float | field_4 |
| `68AC20B3` | Float | field_8 |

### SLdrLightDistanceAttenuationDynamic
| Field | Type | Description |
| --- | --- | --- |
| `B234567C` | Uint32 | field_0 |
| `E15A6749` | [CMayaSpline] | field_4 |
| `BA147368` | [CMayaSpline] | field_34 |

### SLdrLightDynamic
| Field | Type | Description |
| --- | --- | --- |
| `932DD7D8` | Uint32 | field_0 |
| `31F63C93` | [SLdrLightDynamicAttributes](#sldrlightdynamicattributes) | field_4 |
| `76DF827D` | [SLdrLightDistanceAttenuation](#sldrlightdistanceattenuation) | field_C |
| `A327083F` | [SLdrLightDistanceAttenuationDynamic](#sldrlightdistanceattenuationdynamic) | field_18 |
| `F5125ED1` | [SLdrLightAngleAttenuation](#sldrlightangleattenuation) | field_7C |
| `E2FE5508` | [SLdrLightAngleAttenuationDynamic](#sldrlightangleattenuationdynamic) | field_84 |
| `C3EABCBF` | [SLdrLightIntensity](#sldrlightintensity) | field_E4 |
| `E8A62A55` | [SLdrLightIntensityDynamic](#sldrlightintensitydynamic) | field_E8 |
| `B73ED9C3` | [SLdrLightColors](#sldrlightcolors) | field_118 |
| `2C66744C` | Bool | field_148 |
| `35B27754` | [SLdrLightFlags](#sldrlightflags) | field_149 |
| `5873555D` | [SLdrLightingSetFlags](#sldrlightingsetflags) | field_14A |

### SLdrLightDynamicAttributes
| Field | Type | Description |
| --- | --- | --- |
| `4440E44C` | Bool | field_0 |
| `C5E97577` | Bool | field_1 |
| `319A91C2` | Bool | field_2 |
| `DD24B4B2` | Float | field_4 |

### SLdrLightFlags
| Field | Type | Description |
| --- | --- | --- |
| `EEB94AF2` | Bool | field_0 |

### SLdrLightGroupProxy
| Field | Type | Description |
| --- | --- | --- |
| `A0993D37` | [String] | field_0 |

### SLdrLightIntensity
| Field | Type | Description |
| --- | --- | --- |
| `BDFC8A9E` | Float | field_0 |

### SLdrLightIntensityDynamic
| Field | Type | Description |
| --- | --- | --- |
| `EF7256B5` | [CMayaSpline] | field_0 |

### SLdrLightStatic
| Field | Type | Description |
| --- | --- | --- |
| `52D4C579` | Uint32 | field_0 |
| `EBAE52B2` | [SLdrLightDistanceAttenuation](#sldrlightdistanceattenuation) | field_4 |
| `664B1A7C` | [SLdrLightAngleAttenuation](#sldrlightangleattenuation) | field_10 |
| `8B76D48E` | [SLdrLightColors](#sldrlightcolors) | field_18 |
| `006201D3` | [SLdrLightIntensity](#sldrlightintensity) | field_48 |
| `F10EA1B7` | Bool | field_4C |
| `F939C307` | [SLdrLightFlags](#sldrlightflags) | field_4D |
| `3A6A74AF` | [SLdrLightingSetFlags](#sldrlightingsetflags) | field_4E |

### SLdrLightingSetFlags
| Field | Type | Description |
| --- | --- | --- |
| `CF609098` | Bool | field_0 |
| `C3CF8F5D` | Bool | field_1 |
| `726EBE43` | Bool | field_2 |
| `98EDF42B` | Bool | field_3 |
| `5D40CC5D` | Bool | field_4 |
| `76868523` | Bool | field_5 |
| `00A5FF49` | Bool | field_6 |
| `F77C3860` | Bool | field_7 |
| `C81F7AEF` | Bool | field_8 |
| `A7652231` | Bool | field_9 |
| `722B4657` | Bool | field_A |
| `1F9691CB` | Bool | field_B |

### SLdrLoadUnitController
| Field | Type | Description |
| --- | --- | --- |
| `090907A2` | [List]&lt;[CGuid]&gt; | field_0 |
| `5344B780` | [String] | field_C |

### SLdrLookAtOrientation
| Field | Type | Description |
| --- | --- | --- |
| `49279612` | [enum_1007be40](#enum_1007be40) | field_0 |

### SLdrLoopedMotionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `FA9602A9` | [CMayaSpline] | field_0 |
| `67B69D1C` | [CMayaSpline] | field_30 |
| `9BB47604` | [CMayaSpline] | field_60 |
| `147CDA2F` | [CMayaSpline] | field_90 |

### SLdrMapControls
| Field | Type | Description |
| --- | --- | --- |
| `3A701947` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `C39420DA` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `4472154A` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `73EABA60` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `E6D76853` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |
| `0A09FBCC` | [SLdrCommandControls](#sldrcommandcontrols) | field_2A8 |
| `3BC7354C` | [SLdrCommandControls](#sldrcommandcontrols) | field_330 |
| `36F3E6AC` | [SLdrCommandControls](#sldrcommandcontrols) | field_3B8 |
| `BC3CAB3C` | [SLdrCommandControls](#sldrcommandcontrols) | field_440 |
| `969F645E` | [SLdrCommandControls](#sldrcommandcontrols) | field_4C8 |
| `71C63118` | [SLdrCommandControls](#sldrcommandcontrols) | field_550 |
| `67F8D32A` | [SLdrCommandControls](#sldrcommandcontrols) | field_5D8 |
| `CBA13AA3` | [SLdrCommandControls](#sldrcommandcontrols) | field_660 |
| `916FD077` | [SLdrCommandControls](#sldrcommandcontrols) | field_6E8 |
| `0B9BDA7A` | [SLdrCommandControls](#sldrcommandcontrols) | field_770 |
| `6EBF88A0` | [SLdrCommandControls](#sldrcommandcontrols) | field_7F8 |
| `D3F69ED4` | [SLdrCommandControls](#sldrcommandcontrols) | field_880 |
| `2D16FDC4` | [SLdrCommandControls](#sldrcommandcontrols) | field_908 |

### SLdrMapManagerProxy
| Field | Type | Description |
| --- | --- | --- |
| `B390EECC` | [CVector3f] | field_0 |

### SLdrMapNode
| Field | Type | Description |
| --- | --- | --- |
| `EC019860` | [enum_10069720](#enum_10069720) | field_0 |
| `CB3AE460` | [CObjectId] | field_4 |
| `AC4CFED5` | [SLdrMapNodePathTypes](#sldrmapnodepathtypes) | field_14 |
| `AAEA5203` | [SLdrMapNodePathTypes](#sldrmapnodepathtypes) | field_18 |
| `7C892778` | [SLdrMapNodePathTypes](#sldrmapnodepathtypes) | field_1C |
| `7E5CACD9` | [SLdrMapNodePathTypes](#sldrmapnodepathtypes) | field_20 |
| `01708C20` | [CObjectId] | field_24 |
| `4F103AE1` | [String] | field_34 |
| `09316B11` | [enum_10069760](#enum_10069760) | field_40 |
| `82431F8B` | [enum_100697a0](#enum_100697a0) | field_44 |
| `2AFD34F7` | [CVector3f] | field_48 |
| `C8480FC8` | Bool | field_54 |

### SLdrMapNodePathTypes
| Field | Type | Description |
| --- | --- | --- |
| `271C0E1E` | Bool | field_0 |
| `B4D30D2C` | Bool | field_1 |
| `499C44BC` | Bool | field_2 |
| `FC01A93B` | Bool | field_3 |

### SLdrMapPathControl
| Field | Type | Description |
| --- | --- | --- |
| `5CAB5BBB` | [enum_10069dc4](#enum_10069dc4) | field_0 |
| `24655440` | Float | field_4 |
| `DD0C994D` | Bool | field_8 |
| `E139447B` | [CMayaSpline] | field_C |
| `30821AFC` | Float | field_3C |
| `2915F9E5` | [enum_10069d84](#enum_10069d84) | field_40 |
| `23417FEF` | Bool | field_44 |
| `29B7FA43` | Bool | field_45 |
| `DC149D65` | [enum_100697a0](#enum_100697a0) | field_48 |
| `2F5C7A41` | Float | field_4C |

### SLdrMapPlayer
| Field | Type | Description |
| --- | --- | --- |
| `370A3412` | [CObjectId] | field_0 |
| `84E45CF4` | [enum_10069efc](#enum_10069efc) | field_10 |
| `B2AA9C4E` | Float | field_14 |
| `6464F512` | Float | field_18 |
| `FE95CEEA` | [enum_100697a0](#enum_100697a0) | field_1C |
| `29182AA6` | Float | field_20 |
| `F49F6140` | [CObjectId] | field_24 |
| `951D8F01` | [CObjectId] | field_34 |
| `A6E3DEF9` | [CObjectId] | field_44 |
| `A8867038` | [CObjectId] | field_54 |
| `9E472DA9` | [CObjectId] | field_64 |
| `006FA071` | [CObjectId] | field_74 |
| `71DD424C` | [CObjectId] | field_84 |
| `D7250C02` | [CObjectId] | field_94 |
| `F4734883` | [CObjectId] | field_A4 |

### SLdrMasterSlave
This struct does not have any fields

### SLdrMaterialDataOverride
| Field | Type | Description |
| --- | --- | --- |
| `E121CDEF` | [enum_1001a864](#enum_1001a864) | field_0 |
| `D08135EF` | [enum_1001a87c](#enum_1001a87c) | field_4 |
| `9DC78224` | [CObjectId] | field_8 |
| `CC1F256E` | Uint32 | field_18 |
| `6440477E` | [enum_1001a854](#enum_1001a854) | field_1C |
| `A68B9B68` | [CColor4f] | field_20 |
| `370915E1` | [enum_1001a85c](#enum_1001a85c) | field_30 |
| `A7BB1BBA` | [CObjectId] | field_34 |

### SLdrMaterialSoundPair
| Field | Type | Description |
| --- | --- | --- |
| `5459EE4B` | [SLdrMaterialType](#sldrmaterialtype) | field_0 |
| `395081F5` | [CObjectId] | field_4 |

### SLdrMaterialType
| Field | Type | Description |
| --- | --- | --- |
| `F088536E` | [enum_10079210](#enum_10079210) | field_0 |

### SLdrMineCartData
| Field | Type | Description |
| --- | --- | --- |
| `F71FAED5` | Float | field_0 |
| `CD21B14B` | Float | field_4 |
| `6F559F9E` | Float | field_8 |
| `F1455F2C` | Float | field_C |
| `168DE5F7` | Float | field_10 |
| `FDA6292D` | Float | field_14 |
| `A850010D` | Float | field_18 |
| `63E52235` | Float | field_1C |
| `4FC5882A` | Float | field_20 |
| `53F135D5` | Float | field_24 |
| `4F3F3CD2` | Float | field_28 |
| `44DA24EE` | Bool | field_2C |
| `3310E08D` | Bool | field_2D |
| `C54CF1D9` | Bool | field_2E |
| `588A6051` | Bool | field_2F |
| `A9115490` | Bool | field_30 |
| `5E758709` | Bool | field_31 |
| `55D26112` | Bool | field_32 |
| `85E5CEC8` | Bool | field_33 |
| `CA364A36` | Float | field_34 |
| `5544A0D5` | Float | field_38 |
| `A324C830` | Float | field_3C |
| `6958B3A4` | Bool | field_40 |
| `5AC176D0` | Float | field_44 |
| `A0E7C775` | Float | field_48 |
| `C891AC7E` | Float | field_4C |
| `AAA749BC` | Float | field_50 |
| `6139AB41` | Float | field_54 |
| `03888C29` | Float | field_58 |
| `4F778159` | Float | field_5C |
| `C48F4F7E` | Float | field_60 |
| `3FC60F82` | [CVector3f] | field_64 |
| `657C045D` | Float | field_70 |
| `3389F75D` | Bool | field_74 |
| `40DA502E` | Float | field_78 |
| `96F1FC5D` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_7C |
| `CDDD4593` | Float | field_84 |

### SLdrMineCartMaterialSoundData
| Field | Type | Description |
| --- | --- | --- |
| `6D754931` | [enum_10079210](#enum_10079210) | field_0 |
| `FCF0FC93` | [CObjectId] | field_4 |
| `8DE5BC59` | [CObjectId] | field_14 |
| `130A83FD` | [CObjectId] | field_24 |
| `A7D16BF0` | [CObjectId] | field_34 |

### SLdrMineCartProxy
| Field | Type | Description |
| --- | --- | --- |
| `2795E5ED` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_0 |
| `A256F967` | Float | field_8 |
| `60FA4176` | Float | field_C |
| `304ACA15` | Float | field_10 |
| `AFE672F9` | Float | field_14 |
| `7D8C0632` | Float | field_18 |
| `9FFEF483` | Float | field_1C |
| `40E4C1C4` | Bool | field_20 |

### SLdrMineCartSoundData
| Field | Type | Description |
| --- | --- | --- |
| `2FA151A7` | [CObjectId] | field_0 |
| `E69B9D17` | [CObjectId] | field_10 |
| `DE764766` | [CMayaSpline] | field_20 |
| `F84EB8E6` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_50 |
| `747FE26F` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_F0 |
| `0FF7DAAF` | [List]&lt;[SLdrMineCartMaterialSoundData](#sldrminecartmaterialsounddata)&gt; | field_190 |

### SLdrMinecartPathManager
This struct does not have any fields

### SLdrMiscControls
| Field | Type | Description |
| --- | --- | --- |
| `CED4F2AE` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `19AACDEC` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `249032A1` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `A3838D78` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `A86287B6` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |
| `5C774025` | [SLdrCommandControls](#sldrcommandcontrols) | field_2A8 |
| `F705F27F` | [SLdrCommandControls](#sldrcommandcontrols) | field_330 |
| `5C060891` | [SLdrCommandControls](#sldrcommandcontrols) | field_3B8 |
| `D831AD3C` | [SLdrCommandControls](#sldrcommandcontrols) | field_440 |
| `0DACD2BB` | [SLdrCommandControls](#sldrcommandcontrols) | field_4C8 |
| `DF79C134` | [SLdrCommandControls](#sldrcommandcontrols) | field_550 |

### SLdrMixStateData
| Field | Type | Description |
| --- | --- | --- |
| `1335CEF1` | [enum_1007215c](#enum_1007215c) | field_0 |
| `C274EC59` | [SLdrMusicTrackDataList](#sldrmusictrackdatalist) | field_4 |
| `57FCAF47` | [enum_10072144](#enum_10072144) | field_2C |
| `67B89AA0` | Float | field_30 |
| `B317BB48` | [CMayaSpline] | field_34 |
| `15EAAC59` | [CMayaSpline] | field_64 |

### SLdrMixStateTransitionData
| Field | Type | Description |
| --- | --- | --- |
| `8133794B` | [enum_1007215c](#enum_1007215c) | field_0 |
| `942AFE6E` | Bool | field_4 |
| `FA7474B1` | Bool | field_5 |
| `A11DFF95` | Bool | field_6 |
| `CC6D5D52` | [enum_10072144](#enum_10072144) | field_8 |
| `4E3216B4` | Float | field_C |
| `0C3DE911` | [enum_10072144](#enum_10072144) | field_10 |
| `FC8E1814` | [CMayaSpline] | field_14 |
| `22537CE3` | [enum_10072144](#enum_10072144) | field_44 |
| `03A87689` | [CMayaSpline] | field_48 |

### SLdrModelLightingData
| Field | Type | Description |
| --- | --- | --- |
| `A07D9FDB` | Bool | field_0 |
| `60372DAE` | Bool | field_1 |
| `D3B7E396` | Bool | field_2 |
| `1AC9C6F6` | [CColor4f] | field_4 |
| `662B60D1` | Uint32 | field_14 |
| `6BB9C38C` | Uint32 | field_18 |

### SLdrMotionInterpolationMethod
| Field | Type | Description |
| --- | --- | --- |
| `A1669880` | [enum_1005b020](#enum_1005b020) | field_0 |
| `55E71E73` | [enum_1005b060](#enum_1005b060) | field_4 |
| `0CD52A5D` | [SLdrInterpolationMethod](#sldrinterpolationmethod) | field_8 |

### SLdrMotionSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `01530049` | [CMayaSpline] | field_0 |
| `DCE1CFDF` | [CVector3f] | field_30 |
| `8350F3A1` | Bool | field_3C |

### SLdrMovementConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `74FBE8EA` | [enum_1007e0d8](#enum_1007e0d8) | field_0 |
| `837800EE` | [enum_1007e0f8](#enum_1007e0f8) | field_4 |

### SLdrMovementData
| Field | Type | Description |
| --- | --- | --- |
| `8F346EDD` | [enum_1007a590](#enum_1007a590) | field_0 |
| `25A9F61C` | [enum_1007a5b0](#enum_1007a5b0) | field_4 |
| `3F3A92F2` | Bool | field_8 |

### SLdrMultiSwingAttackData
| Field | Type | Description |
| --- | --- | --- |
| `E1BC4D1A` | [enum_10072edc](#enum_10072edc) | field_0 |
| `7F16B0F3` | NBaboon::EMultiSwingTargetPosition | field_4 |

### SLdrMusicData
| Field | Type | Description |
| --- | --- | --- |
| `2EB95C57` | [SLdrMusicDataTracks](#sldrmusicdatatracks) | field_0 |
| `CBC2CA0C` | [List]&lt;[SLdrMixStateData](#sldrmixstatedata)&gt; | field_A4 |

### SLdrMusicDataTracks
| Field | Type | Description |
| --- | --- | --- |
| `D3E1BA51` | [CObjectId] | field_0 |
| `577C42EC` | [CObjectId] | field_10 |
| `ED5BCC7E` | [CObjectId] | field_20 |
| `663AC3EA` | [CObjectId] | field_30 |
| `31944AB4` | [CObjectId] | field_40 |
| `35D0A6CE` | [CObjectId] | field_50 |
| `AAB7BA5F` | [CObjectId] | field_60 |
| `33A62237` | [CObjectId] | field_70 |
| `71B5953B` | [CObjectId] | field_80 |
| `9640DA3C` | [CObjectId] | field_90 |
| `32D6D5D3` | [enum_10072400](#enum_10072400) | field_A0 |

### SLdrMusicStateController
| Field | Type | Description |
| --- | --- | --- |
| `688AFBDB` | [enum_1007215c](#enum_1007215c) | field_0 |
| `078C13D9` | [enum_1006a908](#enum_1006a908) | field_4 |
| `6DCACC36` | Uint32 | field_8 |
| `55265C46` | [List]&lt;[SLdrMixStateTransitionData](#sldrmixstatetransitiondata)&gt; | field_C |

### SLdrMusicSystemTransport
| Field | Type | Description |
| --- | --- | --- |
| `32A3B877` | Bool | field_0 |
| `7B10A22E` | [CMayaSpline] | field_4 |
| `3BC456CA` | Bool | field_34 |
| `86F36711` | [CMayaSpline] | field_38 |

### SLdrMusicTrackDataList
| Field | Type | Description |
| --- | --- | --- |
| `10658967` | Float | field_0 |
| `F3D6F8B7` | Float | field_4 |
| `A6520203` | Float | field_8 |
| `BB28AEB2` | Float | field_C |
| `1454EC9F` | Float | field_10 |
| `143FDAD4` | Float | field_14 |
| `718F240F` | Float | field_18 |
| `C93A734B` | Float | field_1C |
| `57D98CBC` | Float | field_20 |
| `AD6956BD` | Float | field_24 |

### SLdrNearVisible
| Field | Type | Description |
| --- | --- | --- |
| `0CDB453B` | Bool | field_0 |
| `93097B37` | Float | field_4 |
| `F05753EE` | Float | field_8 |
| `D0B66AFF` | Bool | field_C |

### SLdrNormalBopJumpSequence
| Field | Type | Description |
| --- | --- | --- |
| `3E60D8F1` | [List]&lt;[SLdrBopJumpProceduralJumpData](#sldrbopjumpproceduraljumpdata)&gt; | field_0 |

### SLdrOBBoxShapeData
| Field | Type | Description |
| --- | --- | --- |
| `7199772E` | [CVector3f] | field_0 |
| `2A65C84B` | [CVector3f] | field_C |
| `D4FE58A9` | [CVector3f] | field_18 |
| `911C7A59` | Bool | field_24 |

### SLdrObjectFollow
| Field | Type | Description |
| --- | --- | --- |
| `37698A7C` | [enum_1006acd0](#enum_1006acd0) | field_0 |
| `9161614D` | [enum_1006ace8](#enum_1006ace8) | field_4 |
| `879EBA87` | [enum_1006ad08](#enum_1006ad08) | field_8 |
| `02571A08` | [CVector3f] | field_C |
| `22067D2D` | [String] | field_18 |
| `4A8BDE83` | [enum_1006ad20](#enum_1006ad20) | field_24 |
| `026A6F37` | [enum_1006ad40](#enum_1006ad40) | field_28 |
| `6CFA3487` | [CVector3f] | field_2C |
| `D57CE28F` | [enum_1006ad60](#enum_1006ad60) | field_38 |

### SLdrOffsetPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `147A053E` | [CVector3f] | field_0 |
| `53C6B0FC` | [enum_1007c3ec](#enum_1007c3ec) | field_C |

### SLdrOrientationInterpolationMethod
| Field | Type | Description |
| --- | --- | --- |
| `49F12777` | [enum_1005b088](#enum_1005b088) | field_0 |
| `83D0605C` | [SLdrInterpolationMethod](#sldrinterpolationmethod) | field_4 |

### SLdrOrientationPathBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `0153AE16` | [enum_1007c4b8](#enum_1007c4b8) | field_0 |
| `3BA44E4E` | [SLdrConvergence](#sldrconvergence) | field_4 |
| `8C8E4834` | [CMayaSpline] | field_20 |
| `20ED0E24` | [SLdrPathOffset](#sldrpathoffset) | field_50 |

### SLdrOwl
| Field | Type | Description |
| --- | --- | --- |
| `B9E68916` | [List]&lt;[Property]&gt; | field_0 |

### SLdrOwlActionPhase
| Field | Type | Description |
| --- | --- | --- |
| `9DA0AFD2` | [List]&lt;[Property]&gt; | field_0 |
| `BBA4BC84` | [Property] | field_C |

### SLdrOwlBarrelSmash
This struct does not have any fields

### SLdrOwlCommonData
| Field | Type | Description |
| --- | --- | --- |
| `2744C795` | Bool | field_0 |
| `FE0F867C` | Uint32 | field_4 |
| `B469B7A3` | Uint32 | field_8 |
| `8E5E2DE5` | Float | field_C |
| `B9544638` | Float | field_10 |

### SLdrOwlControllerData
| Field | Type | Description |
| --- | --- | --- |
| `98A7C8B5` | Uint32 | field_0 |
| `872ADE4D` | Bool | field_4 |
| `4E6D7B49` | Uint32 | field_8 |
| `FD4A040C` | Float | field_C |
| `C93036AD` | Float | field_10 |
| `8411F699` | Float | field_14 |
| `285486D2` | Float | field_18 |
| `4499C983` | [SLdrOwlSwoopVars](#sldrowlswoopvars) | field_1C |
| `1726E021` | String | field_2C |
| `B92F6D85` | Float | field_38 |
| `8E83D7C5` | Float | field_3C |
| `5B43516C` | Uint32 | field_40 |
| `FB30DFE9` | [CObjectId] | field_44 |
| `2783089B` | String | field_54 |
| `0FAAFF00` | String | field_60 |
| `5607F9F2` | String | field_6C |
| `4FB2242C` | [List]&lt;[SLdrOwlActionPhase](#sldrowlactionphase)&gt; | field_78 |
| `355235FC` | [List]&lt;[SLdrOwlFormationLine](#sldrowlformationline)&gt; | field_84 |
| `4DE8CB76` | [List]&lt;[SLdrOwlEggTossVolley](#sldrowleggtossvolley)&gt; | field_90 |
| `67FAD95B` | [List]&lt;[SLdrOwlWindStormData](#sldrowlwindstormdata)&gt; | field_9C |
| `8F4964FC` | [List]&lt;[SLdrOwlEggDropVolley](#sldrowleggdropvolley)&gt; | field_A8 |
| `BBB15BCB` | [SLdrOwlFanPatternDefinitions](#sldrowlfanpatterndefinitions) | field_B4 |
| `D0C5D1A9` | [List]&lt;[SLdrOwlRockVolley](#sldrowlrockvolley)&gt; | field_CC |
| `434CBF91` | [List]&lt;[SLdrOwlMegaEggDropVolley](#sldrowlmegaeggdropvolley)&gt; | field_D8 |

### SLdrOwlDoubleMegaEgg
| Field | Type | Description |
| --- | --- | --- |
| `03218716` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `3B8A9F0A` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_14 |
| `46490DB7` | [List]&lt;Int32&gt; | field_20 |

### SLdrOwlEggDrop
| Field | Type | Description |
| --- | --- | --- |
| `067994D4` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_0 |
| `A0444E9E` | [List]&lt;Int32&gt; | field_C |

### SLdrOwlEggDropSingle
| Field | Type | Description |
| --- | --- | --- |
| `9C09EBE5` | Uint32 | field_0 |
| `5DB01C71` | Float | field_4 |

### SLdrOwlEggDropVolley
| Field | Type | Description |
| --- | --- | --- |
| `D2C08E51` | [List]&lt;[SLdrOwlEggDropSingle](#sldrowleggdropsingle)&gt; | field_0 |

### SLdrOwlEggToss
| Field | Type | Description |
| --- | --- | --- |
| `119C196D` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `C42C3C92` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_14 |
| `42F0295D` | [List]&lt;Int32&gt; | field_20 |

### SLdrOwlEggTossData
| Field | Type | Description |
| --- | --- | --- |
| `28836682` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |

### SLdrOwlEggTossSingle
| Field | Type | Description |
| --- | --- | --- |
| `78F7CFBF` | Uint32 | field_0 |
| `8BC5741E` | Uint32 | field_4 |

### SLdrOwlEggTossVolley
| Field | Type | Description |
| --- | --- | --- |
| `861D41EC` | [List]&lt;[SLdrOwlEggTossSingle](#sldrowleggtosssingle)&gt; | field_0 |

### SLdrOwlFanPatternDefinitions
| Field | Type | Description |
| --- | --- | --- |
| `14F967F9` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_0 |
| `AED9262D` | [List]&lt;[SLdrOwlFeatherLayout](#sldrowlfeatherlayout)&gt; | field_C |

### SLdrOwlFeatherBlast
| Field | Type | Description |
| --- | --- | --- |
| `A530CC27` | [List]&lt;[SLdrOwlFeatherBlastData](#sldrowlfeatherblastdata)&gt; | field_0 |
| `FD70D7E6` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_C |
| `E2205755` | [List]&lt;Int32&gt; | field_18 |

### SLdrOwlFeatherBlastData
| Field | Type | Description |
| --- | --- | --- |
| `E39CAE98` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `53290CBE` | [List]&lt;[SLdrOwlFeatherBlastOnOff](#sldrowlfeatherblastonoff)&gt; | field_14 |

### SLdrOwlFeatherBlastOnOff
| Field | Type | Description |
| --- | --- | --- |
| `AB5D0FC4` | [List]&lt;Float&gt; | field_0 |

### SLdrOwlFeatherFan
| Field | Type | Description |
| --- | --- | --- |
| `B0707A5F` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `BFE926F6` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_14 |
| `E65DFAA5` | [List]&lt;Int32&gt; | field_20 |

### SLdrOwlFeatherFanData
| Field | Type | Description |
| --- | --- | --- |
| `CFD227C7` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `0A663C12` | [List]&lt;[SLdrOwlFeatherFanSequenceData](#sldrowlfeatherfansequencedata)&gt; | field_14 |

### SLdrOwlFeatherFanSequenceData
| Field | Type | Description |
| --- | --- | --- |
| `F9A5B836` | Uint32 | field_0 |
| `D966285D` | Uint32 | field_4 |
| `3F106F76` | Float | field_8 |

### SLdrOwlFeatherLayout
| Field | Type | Description |
| --- | --- | --- |
| `97989D44` | Uint32 | field_0 |
| `2FD5DC1E` | Float | field_4 |
| `62575B3A` | Float | field_8 |
| `560016C5` | Uint32 | field_C |
| `31925DC4` | Uint32 | field_10 |
| `6D6D0F6B` | Float | field_14 |
| `8A271124` | Bool | field_18 |
| `AD2E5B77` | Bool | field_19 |

### SLdrOwlFormation
| Field | Type | Description |
| --- | --- | --- |
| `D0368375` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `A0B51052` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_14 |
| `EC7AF1F0` | [List]&lt;Int32&gt; | field_20 |

### SLdrOwlFormationData
| Field | Type | Description |
| --- | --- | --- |
| `8D64A304` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |

### SLdrOwlFormationLine
| Field | Type | Description |
| --- | --- | --- |
| `FC7F56AF` | [List]&lt;[SLdrOwlFormationSingle](#sldrowlformationsingle)&gt; | field_0 |

### SLdrOwlFormationSingle
| Field | Type | Description |
| --- | --- | --- |
| `7EA2E896` | Uint32 | field_0 |
| `0CC08502` | Float | field_4 |

### SLdrOwlMegaEggDropSingle
| Field | Type | Description |
| --- | --- | --- |
| `1AA1C3DA` | Uint32 | field_0 |
| `D5CAFBDC` | Uint32 | field_4 |
| `7AA91F05` | Float | field_8 |

### SLdrOwlMegaEggDropVolley
| Field | Type | Description |
| --- | --- | --- |
| `6F51A74F` | [List]&lt;[SLdrOwlMegaEggDropSingle](#sldrowlmegaeggdropsingle)&gt; | field_0 |

### SLdrOwlMegaEggToss
| Field | Type | Description |
| --- | --- | --- |
| `F653DDD4` | Float | field_0 |

### SLdrOwlPatternChoiceData
| Field | Type | Description |
| --- | --- | --- |
| `BC151124` | [List]&lt;Int32&gt; | field_0 |

### SLdrOwlRockRoll
| Field | Type | Description |
| --- | --- | --- |
| `71FB339B` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `BDB419D5` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_14 |
| `BA3430E6` | [List]&lt;Int32&gt; | field_20 |

### SLdrOwlRockRollData
| Field | Type | Description |
| --- | --- | --- |
| `2433051C` | [SLdrOwlCommonData](#sldrowlcommondata) | field_0 |
| `D16091D2` | [List]&lt;[SLdrOwlRockRollSequenceData](#sldrowlrockrollsequencedata)&gt; | field_14 |

### SLdrOwlRockRollSequenceData
| Field | Type | Description |
| --- | --- | --- |
| `E79AC79B` | Uint32 | field_0 |
| `B6B7C8ED` | Float | field_4 |

### SLdrOwlRockSingle
| Field | Type | Description |
| --- | --- | --- |
| `38BF7FF2` | Uint32 | field_0 |
| `21CB1A19` | Float | field_4 |

### SLdrOwlRockVolley
| Field | Type | Description |
| --- | --- | --- |
| `E97C2981` | [List]&lt;[SLdrOwlRockSingle](#sldrowlrocksingle)&gt; | field_0 |

### SLdrOwlSwoop
| Field | Type | Description |
| --- | --- | --- |
| `987809C6` | Uint32 | field_0 |
| `2BD1A76C` | Uint32 | field_4 |
| `833DC02A` | Float | field_8 |
| `4D4B616C` | Float | field_C |

### SLdrOwlSwoopVars
| Field | Type | Description |
| --- | --- | --- |
| `F001DACB` | Float | field_0 |
| `494DB0A7` | Float | field_4 |
| `C3280DDB` | Float | field_8 |
| `D0AB5ACF` | Float | field_C |

### SLdrOwlWindStorm
| Field | Type | Description |
| --- | --- | --- |
| `0C472F91` | [List]&lt;[SLdrOwlPatternChoiceData](#sldrowlpatternchoicedata)&gt; | field_0 |
| `1957C562` | [List]&lt;Int32&gt; | field_C |

### SLdrOwlWindStormData
| Field | Type | Description |
| --- | --- | --- |
| `5BB70A79` | [List]&lt;[SLdrOwlWindStormSpawnData](#sldrowlwindstormspawndata)&gt; | field_0 |

### SLdrOwlWindStormSpawnData
| Field | Type | Description |
| --- | --- | --- |
| `ABE9E818` | Float | field_0 |
| `46288DC7` | Uint32 | field_4 |
| `DC0D53DC` | Uint32 | field_8 |

### SLdrPIDConvergenceData
| Field | Type | Description |
| --- | --- | --- |
| `548B2A96` | [enum_1007d3b4](#enum_1007d3b4) | field_0 |
| `AF962EC8` | Float | field_4 |
| `F85035AA` | Float | field_8 |
| `FD35A7A8` | Float | field_C |
| `7FF32405` | Float | field_10 |

### SLdrPathControl
| Field | Type | Description |
| --- | --- | --- |
| `313745E7` | Bool | field_0 |
| `147F7523` | Bool | field_1 |
| `BD7546EB` | [enum_1005b060](#enum_1005b060) | field_4 |
| `5144C7E5` | [CColor4f] | field_8 |

### SLdrPathControlZipline
| Field | Type | Description |
| --- | --- | --- |
| `3ACBA082` | [SLdrMaterialType](#sldrmaterialtype) | field_0 |
| `63FEFA5D` | Float | field_4 |

### SLdrPathOffset
| Field | Type | Description |
| --- | --- | --- |
| `EE178E0B` | [enum_100942e8](#enum_100942e8) | field_0 |
| `D951F5EE` | [CMayaSpline] | field_4 |
| `20847098` | Bool | field_34 |

### SLdrPathPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `08307A51` | [enum_1007c4b8](#enum_1007c4b8) | field_0 |
| `955695C9` | [SLdrConvergence](#sldrconvergence) | field_4 |
| `29D290FE` | [CMayaSpline] | field_20 |
| `DF66D88C` | [SLdrPathOffset](#sldrpathoffset) | field_50 |

### SLdrPendulumJumpMomentumOverride
| Field | Type | Description |
| --- | --- | --- |
| `0B030FC5` | [CMayaSpline] | field_0 |
| `CFAF27B4` | [CMayaSpline] | field_30 |

### SLdrPerformanceGroupController
| Field | Type | Description |
| --- | --- | --- |
| `0987A376` | [List]&lt;[CGuid]&gt; | field_0 |

### SLdrPhysicalControl
| Field | Type | Description |
| --- | --- | --- |
| `AAD7E315` | [enum_10006c68](#enum_10006c68) | field_0 |
| `0F8712F3` | [CMayaSpline] | field_4 |

### SLdrPickup
| Field | Type | Description |
| --- | --- | --- |
| `A66BEA89` | [SLdrPickupData](#sldrpickupdata) | field_0 |
| `5D131AB9` | Bool | field_1F8 |
| `7F0E00CD` | [SLdrPickupDamageData](#sldrpickupdamagedata) | field_1FC |
| `4B86C1C2` | [CVector3f] | field_240 |
| `AE378090` | [CVector3f] | field_24C |
| `9F82BB6C` | [CVector3f] | field_258 |

### SLdrPickupDamageData
| Field | Type | Description |
| --- | --- | --- |
| `79EBF3C4` | Bool | field_0 |
| `2FDFB59C` | [SLdrDamageInfo](#sldrdamageinfo) | field_4 |
| `7F633506` | Float | field_28 |
| `90004611` | [String] | field_2C |
| `8C81BA73` | [String] | field_38 |

### SLdrPickupData
| Field | Type | Description |
| --- | --- | --- |
| `5E92BDA4` | [SLdrPlayerItem](#sldrplayeritem) | field_0 |
| `50F5E550` | Uint32 | field_4 |
| `3721E29F` | Uint32 | field_8 |
| `94183C92` | Uint32 | field_C |
| `729E0C96` | Uint32 | field_10 |
| `6C220ACD` | Float | field_14 |
| `1B9A0AE9` | Float | field_18 |
| `786EAF71` | Float | field_1C |
| `EA48D94E` | Float | field_20 |
| `4B726A1E` | Float | field_24 |
| `ED5F6939` | [SLdrExplosionData](#sldrexplosiondata) | field_28 |
| `B0A5A868` | [CObjectId] | field_5C |
| `3E9A51EF` | [CObjectId] | field_6C |
| `889A036E` | [CObjectId] | field_7C |
| `F5BF3B48` | [CObjectId] | field_8C |
| `A65CB4EC` | [CObjectId] | field_9C |
| `A86FD367` | [CObjectId] | field_AC |
| `7F3AF146` | [CObjectId] | field_BC |
| `0CAB9607` | [CObjectId] | field_CC |
| `FAE2E3E6` | [CObjectId] | field_DC |
| `6C915E36` | [CObjectId] | field_EC |
| `C74E3210` | Uint32 | field_FC |
| `C0E52D4B` | Bool | field_100 |
| `C574F6AD` | Bool | field_101 |
| `C70E7BD4` | Bool | field_102 |
| `A8591EFF` | Bool | field_103 |
| `E756A85B` | Bool | field_104 |
| `35FB2E6A` | Bool | field_105 |
| `41A5DAAE` | Float | field_108 |
| `B13A3B27` | Bool | field_10C |
| `1C61EC5F` | Bool | field_10D |
| `53F86BC5` | Bool | field_10E |
| `BAB95890` | [CObjectId] | field_110 |
| `A07A3382` | [CObjectId] | field_120 |
| `86E542A3` | [SLdrFlyingPickupData](#sldrflyingpickupdata) | field_130 |
| `66BBCED4` | Bool | field_178 |
| `95BB5AA2` | [SLdrFlyingPickupData](#sldrflyingpickupdata) | field_17C |
| `3844D610` | [SLdrExplosionData](#sldrexplosiondata) | field_1C4 |

### SLdrPlatformRiderPhysicsOptions
| Field | Type | Description |
| --- | --- | --- |
| `247210E4` | Bool | field_0 |
| `28EF14FD` | Bool | field_1 |
| `7F34FDB9` | Bool | field_2 |
| `8B5008E4` | Bool | field_3 |
| `F09C3773` | [Property] | field_4 |

### SLdrPlayer
| Field | Type | Description |
| --- | --- | --- |
| `7ABE1F4E` | [SLdrPlayerConstructionData](#sldrplayerconstructiondata) | field_0 |
| `D09B5298` | [SLdrPlayerCommonData](#sldrplayercommondata) | field_10 |
| `3DF78DED` | [List]&lt;[Property]&gt; | field_C4 |

### SLdrPlayerActionDetector
| Field | Type | Description |
| --- | --- | --- |
| `03006563` | [List]&lt;[Property]&gt; | field_0 |
| `58276864` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_C |
| `2244AC5F` | [CVector3f] | field_14 |
| `BFD897F7` | Float | field_20 |
| `6DC4FDA8` | Bool | field_24 |
| `5CEC7917` | Bool | field_25 |

### SLdrPlayerActionHint
| Field | Type | Description |
| --- | --- | --- |
| `2B2B29B1` | [SLdrPlayerActionHintData](#sldrplayeractionhintdata) | field_0 |

### SLdrPlayerActionHintData
| Field | Type | Description |
| --- | --- | --- |
| `A30C91E4` | [enum_1009599c](#enum_1009599c) | field_0 |
| `92E98C24` | Float | field_4 |
| `0D20DD06` | [SLdrPlayerActionHintFlags](#sldrplayeractionhintflags) | field_8 |

### SLdrPlayerActionHintFlags
| Field | Type | Description |
| --- | --- | --- |
| `C535C4C3` | Bool | field_0 |
| `92997CAC` | Bool | field_1 |
| `A7F77F0C` | Bool | field_2 |
| `11AD8378` | Bool | field_3 |
| `582806C5` | Bool | field_4 |
| `03B4E782` | Bool | field_5 |
| `CA923C98` | Bool | field_6 |
| `23629AFD` | Bool | field_7 |
| `AC18D761` | Bool | field_8 |
| `A9905954` | Bool | field_9 |
| `9DAA20C6` | Bool | field_A |
| `9B8A07D2` | Bool | field_B |
| `BA7FF227` | Bool | field_C |
| `91A598E8` | Bool | field_D |
| `5BA0238C` | Bool | field_E |
| `A3EECEA4` | Bool | field_F |
| `CA0CAA8F` | Bool | field_10 |
| `A362B7D9` | Bool | field_11 |

### SLdrPlayerActor
| Field | Type | Description |
| --- | --- | --- |
| `F922A089` | [enum_10069efc](#enum_10069efc) | field_0 |
| `A1DF5371` | Bool | field_4 |
| `75DB43DE` | Bool | field_5 |
| `666E4C00` | Bool | field_6 |
| `D4E9D725` | Bool | field_7 |
| `AFBE8FDC` | Bool | field_8 |
| `D6FB8840` | Bool | field_9 |

### SLdrPlayerAlternateSkinData
| Field | Type | Description |
| --- | --- | --- |
| `79926567` | [String] | field_0 |
| `10A3AF57` | [String] | field_C |
| `D686854B` | [String] | field_18 |
| `F611DFBB` | [String] | field_24 |

### SLdrPlayerAnimationData
| Field | Type | Description |
| --- | --- | --- |
| `6DD3F9CB` | [SLdrModelLightingData](#sldrmodellightingdata) | field_0 |
| `DE127A04` | [Property] | field_1C |
| `7EB4CA2F` | [CObjectId] | field_24 |
| `C74B0886` | Float | field_34 |

### SLdrPlayerAttackBounceData
| Field | Type | Description |
| --- | --- | --- |
| `E84A9C99` | Float | field_0 |
| `194AC3C9` | Float | field_4 |
| `B632BB8E` | [CObjectId] | field_8 |
| `DF7D6B20` | [CObjectId] | field_18 |
| `B719D2D5` | [CObjectId] | field_28 |
| `85B02554` | [CObjectId] | field_38 |
| `AD1D914C` | [CObjectId] | field_48 |

### SLdrPlayerBarrelCannonData
| Field | Type | Description |
| --- | --- | --- |
| `9432A709` | [String] | field_0 |
| `2B8E4DAD` | Float | field_C |
| `ACE46DA5` | Float | field_10 |
| `9D96CACF` | [CObjectId] | field_14 |
| `86EC1C91` | [CObjectId] | field_24 |
| `EEE7EA49` | [CObjectId] | field_34 |
| `8EDCD303` | [CObjectId] | field_44 |
| `8D0E4D02` | Float | field_54 |
| `F01FA843` | Float | field_58 |
| `6D883E40` | [CVector3f] | field_5C |
| `CF6B5500` | [SLdrPlayerAttackBounceData](#sldrplayerattackbouncedata) | field_68 |
| `F688CA33` | [SLdrExplosionData](#sldrexplosiondata) | field_C0 |

### SLdrPlayerBasicMovementData
| Field | Type | Description |
| --- | --- | --- |
| `77E4F858` | Bool | field_0 |
| `150B2086` | Float | field_4 |
| `4F7DEDF2` | Float | field_8 |
| `184D4D7C` | Bool | field_C |
| `FCD40528` | Float | field_10 |
| `6F7A7998` | Float | field_14 |
| `0853F6AD` | Float | field_18 |
| `E5536796` | Float | field_1C |
| `007ED5F1` | Float | field_20 |
| `435A0DDD` | Float | field_24 |
| `79AD46B4` | Float | field_28 |
| `C79DD1E1` | Float | field_2C |
| `259EC93A` | Float | field_30 |
| `E79E9527` | Float | field_34 |
| `55AB9323` | Float | field_38 |
| `54D12135` | Float | field_3C |
| `E4DF5BE2` | Float | field_40 |
| `E58E3BDD` | Float | field_44 |
| `3AF92953` | [SLdrExplosionData](#sldrexplosiondata) | field_48 |
| `57B986FC` | [SLdrExplosionData](#sldrexplosiondata) | field_7C |
| `451FAD6E` | [SLdrExplosionData](#sldrexplosiondata) | field_B0 |

### SLdrPlayerBopAnimThresholds
| Field | Type | Description |
| --- | --- | --- |
| `4A64C29B` | Uint32 | field_0 |

### SLdrPlayerCharactersBitField
| Field | Type | Description |
| --- | --- | --- |
| `9FFCEC57` | Bool | field_0 |
| `210D3D3A` | Bool | field_1 |
| `DD7A5061` | Bool | field_2 |
| `7B2E7CAA` | Bool | field_3 |
| `3554117A` | Bool | field_4 |
| `79A846BA` | Bool | field_5 |
| `97BB876A` | Bool | field_6 |

### SLdrPlayerClingData
| Field | Type | Description |
| --- | --- | --- |
| `17FF747A` | Float | field_0 |
| `0DE7D8EC` | [CMayaSpline] | field_4 |
| `0609EA6D` | [CMayaSpline] | field_34 |
| `593C6818` | [CMayaSpline] | field_64 |
| `B0E14293` | Float | field_94 |
| `900115DF` | Float | field_98 |
| `5D738B0F` | Float | field_9C |
| `90EF4331` | Float | field_A0 |
| `95077D7B` | Float | field_A4 |
| `0141C248` | Float | field_A8 |
| `E0182A94` | Float | field_AC |
| `783E4921` | Float | field_B0 |
| `2C9FF7A8` | Float | field_B4 |
| `C0611B38` | Float | field_B8 |
| `699314FF` | Float | field_BC |
| `DF37B7EB` | Float | field_C0 |
| `84EFDE66` | [SLdrExplosionData](#sldrexplosiondata) | field_C4 |
| `1E7C9E9B` | [CVector3f] | field_F8 |
| `773BD682` | [SLdrExplosionData](#sldrexplosiondata) | field_104 |
| `39590F4D` | [CVector3f] | field_138 |
| `691145EA` | [CObjectId] | field_144 |
| `692BF0D6` | Float | field_154 |

### SLdrPlayerCommonData
| Field | Type | Description |
| --- | --- | --- |
| `42C5FFF1` | Float | field_0 |
| `D8EDCB94` | [SLdrPlayerType](#sldrplayertype) | field_4 |
| `46C6EC14` | Float | field_8 |
| `F4517CDC` | Float | field_C |
| `45334EED` | Float | field_10 |
| `A8DDFD2F` | Float | field_14 |
| `03730ADF` | Bool | field_18 |
| `1E83BF24` | Bool | field_19 |
| `B2781E64` | [SLdrExplosionData](#sldrexplosiondata) | field_1C |
| `85DD6D00` | [SLdrExplosionData](#sldrexplosiondata) | field_50 |
| `87F71167` | [SLdrPlayerAlternateSkinData](#sldrplayeralternateskindata) | field_84 |

### SLdrPlayerConstructionData
| Field | Type | Description |
| --- | --- | --- |
| `731D9C2E` | [CObjectId] | field_0 |

### SLdrPlayerCrouchData
| Field | Type | Description |
| --- | --- | --- |
| `2B8B047B` | Float | field_0 |
| `0B0552AF` | Float | field_4 |
| `DF5CB657` | Float | field_8 |
| `C2D5D21E` | Float | field_C |

### SLdrPlayerFlutterJumpData
| Field | Type | Description |
| --- | --- | --- |
| `56347502` | Float | field_0 |
| `FACF7AB3` | [CMayaSpline] | field_4 |
| `E238120F` | [CMayaSpline] | field_34 |
| `29A7E770` | [CMayaSpline] | field_64 |
| `E73EAA64` | Float | field_94 |
| `186B5281` | Float | field_98 |
| `0E793B55` | Float | field_9C |
| `C6FBBE91` | Float | field_A0 |
| `04976896` | Float | field_A4 |

### SLdrPlayerGameoverData
| Field | Type | Description |
| --- | --- | --- |
| `68721502` | Bool | field_0 |
| `E1B48DB9` | Float | field_4 |
| `7D7DFCBD` | Bool | field_8 |
| `90F9B7C8` | Bool | field_9 |
| `35690B74` | Float | field_C |
| `E2639A98` | Float | field_10 |
| `B346FE77` | Float | field_14 |

### SLdrPlayerGrabData
| Field | Type | Description |
| --- | --- | --- |
| `140BBE58` | [CVector3f] | field_0 |
| `7844CE7E` | [CVector3f] | field_C |
| `FB10B191` | Float | field_18 |
| `F4F0F896` | [CVector3f] | field_1C |
| `019257F0` | Float | field_28 |
| `36E57579` | Float | field_2C |
| `F56C9894` | [CVector3f] | field_30 |
| `70B6CF4F` | [CVector3f] | field_3C |
| `2FA19622` | [String] | field_48 |
| `3ECB9383` | Bool | field_54 |
| `DBCD683D` | Float | field_58 |

### SLdrPlayerGreenBalloonData
| Field | Type | Description |
| --- | --- | --- |
| `5DAC0ABA` | Float | field_0 |
| `196556EA` | Float | field_4 |
| `20166FB6` | Float | field_8 |
| `7C64B331` | Float | field_C |
| `C3311A1E` | Float | field_10 |
| `583146AA` | Float | field_14 |
| `0990564C` | Float | field_18 |
| `BFA47E1F` | [SLdrExplosionData](#sldrexplosiondata) | field_1C |

### SLdrPlayerGroundPoundData
| Field | Type | Description |
| --- | --- | --- |
| `F0353907` | [CVector3f] | field_0 |
| `FA795E36` | Float | field_C |
| `FF2C64D3` | Float | field_10 |
| `F45D9BF6` | Float | field_14 |
| `C659FE64` | Float | field_18 |
| `B0827234` | Float | field_1C |
| `2373E873` | Float | field_20 |
| `478B696A` | [SLdrWindWakerImpulseData](#sldrwindwakerimpulsedata) | field_24 |

### SLdrPlayerHealthData
| Field | Type | Description |
| --- | --- | --- |
| `1058D7D2` | Float | field_0 |
| `FD3A6072` | Float | field_4 |
| `ABE5C6A0` | [SLdrDamageVulnerability](#sldrdamagevulnerability) | field_8 |
| `27A9C332` | [CObjectId] | field_40 |

### SLdrPlayerIndexBitField
| Field | Type | Description |
| --- | --- | --- |
| `1CB96677` | Bool | field_0 |
| `D49720FE` | Bool | field_1 |

### SLdrPlayerItem
| Field | Type | Description |
| --- | --- | --- |
| `0FD61638` | [enum_1001326c](#enum_1001326c) | field_0 |

### SLdrPlayerJumpAnimWeights
| Field | Type | Description |
| --- | --- | --- |
| `96791D25` | Uint32 | field_0 |
| `F264F500` | Float | field_4 |
| `BAA79CF0` | Float | field_8 |
| `435F1C1E` | Float | field_C |
| `2E83DA78` | Float | field_10 |
| `68BA424B` | Float | field_14 |
| `62AE003D` | Float | field_18 |
| `C1BBEA18` | Float | field_1C |
| `77210556` | Float | field_20 |
| `DFEB4191` | Float | field_24 |
| `37422511` | Float | field_28 |

### SLdrPlayerJumpData
| Field | Type | Description |
| --- | --- | --- |
| `6E64CF41` | [SLdrPlayerJumpHeights](#sldrplayerjumpheights) | field_0 |
| `E5FC9360` | Float | field_60 |
| `7E167180` | Float | field_64 |
| `DF17CEBA` | Float | field_68 |
| `575D7CC8` | Float | field_6C |
| `863BAB71` | Float | field_70 |
| `C5869256` | Float | field_74 |
| `493B0A6B` | Float | field_78 |
| `CF839871` | Float | field_7C |
| `516959B5` | Float | field_80 |
| `FB8ED84E` | Bool | field_84 |

### SLdrPlayerJumpHeights
| Field | Type | Description |
| --- | --- | --- |
| `9830E488` | Float | field_0 |
| `F467F53C` | Float | field_4 |
| `EA0A2882` | [SLdrPlayerAttackBounceData](#sldrplayerattackbouncedata) | field_8 |

### SLdrPlayerKeyframe
| Field | Type | Description |
| --- | --- | --- |
| `4F8A0870` | Bool | field_0 |
| `73255ADF` | Bool | field_1 |
| `ECC32E91` | Bool | field_2 |
| `2A791EB7` | Bool | field_3 |
| `2A23A734` | Bool | field_4 |
| `521999C3` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_8 |
| `03DA1AC2` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_34 |
| `AD78DD76` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_60 |
| `8F5F033A` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_8C |
| `E24ABD90` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_B8 |
| `BE259D7B` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_E4 |
| `A2924A95` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_110 |
| `7CC000A3` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_13C |
| `6CEC03C2` | [SLdrPlayerKeyframeAnimationInfo](#sldrplayerkeyframeanimationinfo) | field_168 |

### SLdrPlayerKeyframeAnimationInfo
| Field | Type | Description |
| --- | --- | --- |
| `E1A409A9` | [CObjectId] | field_0 |
| `3BA6420F` | [String] | field_10 |
| `9D2E3236` | Bool | field_1C |
| `9C8C32F1` | Bool | field_1D |
| `42F19A29` | Float | field_20 |
| `A5D0D2AC` | Bool | field_24 |
| `AD6CE67F` | Float | field_28 |

### SLdrPlayerLedgeAvoidanceForce
| Field | Type | Description |
| --- | --- | --- |
| `1018F01A` | Float | field_0 |
| `87A90404` | Float | field_4 |
| `9C826B60` | Float | field_8 |
| `F3F6ECFF` | Float | field_C |

### SLdrPlayerMeleeData
| Field | Type | Description |
| --- | --- | --- |
| `6E1F69BA` | Bool | field_0 |
| `4CC29320` | Bool | field_1 |
| `A0D4C6E4` | [CObjectId] | field_4 |
| `6C0B41D8` | [CObjectId] | field_14 |
| `551A124A` | [CObjectId] | field_24 |

### SLdrPlayerModuleActionHintData
This struct does not have any fields

### SLdrPlayerModuleAnimationData
| Field | Type | Description |
| --- | --- | --- |
| `70694610` | [SLdrPlayerAnimationData](#sldrplayeranimationdata) | field_0 |

### SLdrPlayerModuleBarrelCannonData
| Field | Type | Description |
| --- | --- | --- |
| `962E7D4C` | [SLdrPlayerBarrelCannonData](#sldrplayerbarrelcannondata) | field_0 |

### SLdrPlayerModuleBasicMovementData
This struct does not have any fields

### SLdrPlayerModuleCharacterMovementData
| Field | Type | Description |
| --- | --- | --- |
| `B4FD1195` | [SLdrPlayerBasicMovementData](#sldrplayerbasicmovementdata) | field_0 |

### SLdrPlayerModuleClingData
| Field | Type | Description |
| --- | --- | --- |
| `161A1900` | [SLdrPlayerClingData](#sldrplayerclingdata) | field_0 |

### SLdrPlayerModuleControllerData
| Field | Type | Description |
| --- | --- | --- |
| `E2A8B759` | Uint32 | field_0 |

### SLdrPlayerModuleCrouchData
| Field | Type | Description |
| --- | --- | --- |
| `FE260E4B` | [SLdrPlayerCrouchData](#sldrplayercrouchdata) | field_0 |

### SLdrPlayerModuleFlutterJumpData
| Field | Type | Description |
| --- | --- | --- |
| `F63BE403` | [SLdrPlayerFlutterJumpData](#sldrplayerflutterjumpdata) | field_0 |

### SLdrPlayerModuleGrabData
| Field | Type | Description |
| --- | --- | --- |
| `50009833` | [SLdrPlayerGrabData](#sldrplayergrabdata) | field_0 |

### SLdrPlayerModuleGreenBalloonData
| Field | Type | Description |
| --- | --- | --- |
| `A4643032` | [SLdrPlayerGreenBalloonData](#sldrplayergreenballoondata) | field_0 |

### SLdrPlayerModuleGroundPoundData
| Field | Type | Description |
| --- | --- | --- |
| `AD9C10C5` | [SLdrPlayerGroundPoundData](#sldrplayergroundpounddata) | field_0 |
| `5D08589E` | [SLdrPlayerGroundPoundData](#sldrplayergroundpounddata) | field_94 |

### SLdrPlayerModuleHeadTrackingData
| Field | Type | Description |
| --- | --- | --- |
| `9E86AD76` | [String] | field_0 |

### SLdrPlayerModuleHealthData
| Field | Type | Description |
| --- | --- | --- |
| `A67F449A` | [SLdrPlayerHealthData](#sldrplayerhealthdata) | field_0 |

### SLdrPlayerModuleJumpData
| Field | Type | Description |
| --- | --- | --- |
| `7338B603` | [SLdrPlayerJumpData](#sldrplayerjumpdata) | field_0 |
| `9E415AE6` | [SLdrPlayerJumpAnimWeights](#sldrplayerjumpanimweights) | field_88 |
| `9E42AC17` | [SLdrPlayerBopAnimThresholds](#sldrplayerbopanimthresholds) | field_B4 |

### SLdrPlayerModuleJumpUpLedgeData
This struct does not have any fields

### SLdrPlayerModuleKnockbackData
This struct does not have any fields

### SLdrPlayerModuleMeleeData
| Field | Type | Description |
| --- | --- | --- |
| `5DEF0303` | [SLdrPlayerMeleeData](#sldrplayermeleedata) | field_0 |

### SLdrPlayerModuleMineCartData
| Field | Type | Description |
| --- | --- | --- |
| `05F07C5C` | [SLdrMineCartData](#sldrminecartdata) | field_0 |
| `469D814A` | [SLdrMineCartSoundData](#sldrminecartsounddata) | field_88 |

### SLdrPlayerModuleMountData
| Field | Type | Description |
| --- | --- | --- |
| `2C17341B` | [SLdrPlayerMountData](#sldrplayermountdata) | field_0 |
| `961AC7D3` | [SLdrPlayerMountRiderList](#sldrplayermountriderlist) | field_28 |

### SLdrPlayerModuleMultiKillRewardData
| Field | Type | Description |
| --- | --- | --- |
| `75A75CC5` | [SLdrPlayerMultiKillRewardData](#sldrplayermultikillrewarddata) | field_0 |

### SLdrPlayerModuleOffscreenIndicatorData
| Field | Type | Description |
| --- | --- | --- |
| `FA737F93` | [SLdrPlayerOffscreenData](#sldrplayeroffscreendata) | field_0 |

### SLdrPlayerModulePeanutGunData
| Field | Type | Description |
| --- | --- | --- |
| `F5602BA9` | [SLdrPlayerPeanutGunData](#sldrplayerpeanutgundata) | field_0 |

### SLdrPlayerModulePeriodicAdditiveAnimationData
| Field | Type | Description |
| --- | --- | --- |
| `F9B344FB` | [SLdrPlayerPeriodicAdditiveAnimationData](#sldrplayerperiodicadditiveanimationdata) | field_0 |

### SLdrPlayerModulePogoStickData
| Field | Type | Description |
| --- | --- | --- |
| `8F5DDF91` | [SLdrPlayerPogoStickData](#sldrplayerpogostickdata) | field_0 |

### SLdrPlayerModuleRambiControllerData
| Field | Type | Description |
| --- | --- | --- |
| `F3A41967` | [SLdrRambiControllerData](#sldrrambicontrollerdata) | field_0 |

### SLdrPlayerModuleRiseFromTheGraveData
| Field | Type | Description |
| --- | --- | --- |
| `058D7780` | [CObjectId] | field_0 |
| `3A608D50` | [CObjectId] | field_10 |
| `E4EFCE80` | Float | field_20 |

### SLdrPlayerModuleRocketBarrelData
| Field | Type | Description |
| --- | --- | --- |
| `6CF91EA3` | [SLdrRocketBarrelThrustData](#sldrrocketbarrelthrustdata) | field_0 |
| `58475B03` | [SLdrRocketBarrelWakeData](#sldrrocketbarrelwakedata) | field_1A8 |
| `579F772B` | Float | field_258 |

### SLdrPlayerModuleRollData
| Field | Type | Description |
| --- | --- | --- |
| `80469737` | [SLdrPlayerRollData](#sldrplayerrolldata) | field_0 |

### SLdrPlayerModuleShieldData
| Field | Type | Description |
| --- | --- | --- |
| `FEABC015` | [SLdrPlayerShieldData](#sldrplayershielddata) | field_0 |

### SLdrPlayerModuleSlaveData
| Field | Type | Description |
| --- | --- | --- |
| `EDEB4CB7` | [SLdrPlayerSlaveData](#sldrplayerslavedata) | field_0 |

### SLdrPlayerModuleSlideData
| Field | Type | Description |
| --- | --- | --- |
| `233227FA` | [SLdrPlayerSlideData](#sldrplayerslidedata) | field_0 |

### SLdrPlayerModuleSpecialContactDamageData
This struct does not have any fields

### SLdrPlayerModuleSplineAdvancementData
| Field | Type | Description |
| --- | --- | --- |
| `0EDDE5D9` | [SLdrPlayerSplineAdvancementData](#sldrplayersplineadvancementdata) | field_0 |

### SLdrPlayerModuleStalledDescentData
| Field | Type | Description |
| --- | --- | --- |
| `003B3A34` | [SLdrPlayerStalledDescentData](#sldrplayerstalleddescentdata) | field_0 |

### SLdrPlayerModuleSuperCombinedAbilityData
| Field | Type | Description |
| --- | --- | --- |
| `B379DD3D` | [SLdrSuperCombinedAbilityData](#sldrsupercombinedabilitydata) | field_0 |

### SLdrPlayerModuleSwimmingBreastStrokeData
| Field | Type | Description |
| --- | --- | --- |
| `E79D29A3` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_0 |

### SLdrPlayerModuleSwimmingData
| Field | Type | Description |
| --- | --- | --- |
| `8573AB20` | Float | field_0 |
| `12EC9DEF` | [String] | field_4 |
| `7F30F782` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_10 |
| `7292AA35` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_B0 |
| `DA9574AB` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_150 |
| `90ACBECC` | [SLdrPlayerSwimCollisionData](#sldrplayerswimcollisiondata) | field_1B4 |
| `BA9F32E4` | [SLdrExplosionData](#sldrexplosiondata) | field_1C0 |
| `B81C714A` | [CVector3f] | field_1F4 |
| `149E977B` | [SLdrExplosionData](#sldrexplosiondata) | field_200 |
| `C3803BB0` | [CVector3f] | field_234 |
| `719AEE46` | [CObjectId] | field_240 |
| `BF78AB9B` | [CObjectId] | field_250 |

### SLdrPlayerModuleSwimmingJetBoostData
| Field | Type | Description |
| --- | --- | --- |
| `F7ED2FD2` | Bool | field_0 |
| `1BFDD0C7` | [enum_10017488](#enum_10017488) | field_4 |
| `D0DB765F` | [CMayaSpline] | field_8 |
| `81147656` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_38 |

### SLdrPlayerModuleSwimmingPropellerData
| Field | Type | Description |
| --- | --- | --- |
| `F884A9B7` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_0 |

### SLdrPlayerModuleSwimmingSpinData
| Field | Type | Description |
| --- | --- | --- |
| `6BBADB85` | [CVector3f] | field_0 |
| `7EE194D5` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_C |
| `9AD455F9` | [CObjectId] | field_70 |
| `E69B6568` | [CObjectId] | field_80 |

### SLdrPlayerModuleSwimmingStaticSpinData
| Field | Type | Description |
| --- | --- | --- |
| `BA0255F9` | [CVector3f] | field_0 |
| `670C02F8` | [SLdrPlayerSwimMovementData](#sldrplayerswimmovementdata) | field_C |
| `2E90A6E7` | [CObjectId] | field_70 |
| `6AD75600` | [CObjectId] | field_80 |

### SLdrPlayerModuleSwingData
| Field | Type | Description |
| --- | --- | --- |
| `9225A242` | [SLdrPlayerSwingData](#sldrplayerswingdata) | field_0 |

### SLdrPlayerModuleTeleportData
| Field | Type | Description |
| --- | --- | --- |
| `7D025BD4` | [SLdrPlayerTeleportData](#sldrplayerteleportdata) | field_0 |

### SLdrPlayerModuleTerrainAlignmentData
| Field | Type | Description |
| --- | --- | --- |
| `9D73310F` | [SLdrPlayerTerrainAlignmentData](#sldrplayerterrainalignmentdata) | field_0 |

### SLdrPlayerModuleTireData
| Field | Type | Description |
| --- | --- | --- |
| `4B1CC855` | [SLdrPlayerTireInteractionData](#sldrplayertireinteractiondata) | field_0 |

### SLdrPlayerModuleZiplineData
| Field | Type | Description |
| --- | --- | --- |
| `9F5C3398` | [SLdrPlayerZiplineData](#sldrplayerziplinedata) | field_0 |

### SLdrPlayerMountData
| Field | Type | Description |
| --- | --- | --- |
| `5B18CD55` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_0 |
| `604BD764` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_7 |
| `928831C2` | Bool | field_E |
| `24EBBFCD` | Bool | field_F |
| `AA970020` | Bool | field_10 |
| `C3212C64` | Bool | field_11 |
| `2B46A128` | Bool | field_12 |
| `35E1E509` | Float | field_14 |
| `25241944` | Float | field_18 |
| `0D72C3B4` | Float | field_1C |
| `3C0A22CC` | Bool | field_20 |
| `FDF785C5` | Bool | field_21 |
| `C3FD4FDC` | Bool | field_22 |
| `CE0CA7AA` | Bool | field_23 |
| `814E21DD` | Bool | field_24 |

### SLdrPlayerMountRiderData
| Field | Type | Description |
| --- | --- | --- |
| `C8B5CDCB` | [SLdrPlayerType](#sldrplayertype) | field_0 |
| `16EFC895` | [String] | field_4 |
| `E8D779EC` | [String] | field_10 |
| `99B56A9A` | Bool | field_1C |
| `2F7067A7` | Bool | field_1D |
| `78207CD5` | Bool | field_1E |
| `25A5AC22` | Bool | field_1F |
| `549A8247` | Uint32 | field_20 |
| `5C901BA9` | Float | field_24 |

### SLdrPlayerMountRiderList
| Field | Type | Description |
| --- | --- | --- |
| `B3BF0942` | Uint32 | field_0 |
| `CC0B5B0F` | Uint32 | field_4 |
| `D7EEFFCC` | [SLdrPlayerMountRiderData](#sldrplayermountriderdata) | field_8 |
| `37FDF041` | [SLdrPlayerMountRiderData](#sldrplayermountriderdata) | field_30 |
| `63B9E0AD` | [SLdrPlayerMountRiderData](#sldrplayermountriderdata) | field_58 |
| `02CA6E43` | [SLdrPlayerMountRiderData](#sldrplayermountriderdata) | field_80 |

### SLdrPlayerMovementControls
| Field | Type | Description |
| --- | --- | --- |
| `E721B25B` | [SLdrCommandControls](#sldrcommandcontrols) | field_0 |
| `12BE0902` | [SLdrCommandControls](#sldrcommandcontrols) | field_88 |
| `5E79D10C` | [SLdrCommandControls](#sldrcommandcontrols) | field_110 |
| `97843DE5` | [SLdrCommandControls](#sldrcommandcontrols) | field_198 |
| `908F1F66` | [SLdrCommandControls](#sldrcommandcontrols) | field_220 |
| `599DFF3D` | [SLdrCommandControls](#sldrcommandcontrols) | field_2A8 |
| `C6255474` | [SLdrCommandControls](#sldrcommandcontrols) | field_330 |
| `1EB28FF3` | [SLdrCommandControls](#sldrcommandcontrols) | field_3B8 |
| `108D9918` | [SLdrCommandControls](#sldrcommandcontrols) | field_440 |
| `61580041` | [SLdrCommandControls](#sldrcommandcontrols) | field_4C8 |
| `A18F50F2` | [SLdrCommandControls](#sldrcommandcontrols) | field_550 |
| `2FEA08B0` | [SLdrCommandControls](#sldrcommandcontrols) | field_5D8 |
| `941B3777` | [SLdrCommandControls](#sldrcommandcontrols) | field_660 |
| `72C748DD` | [SLdrCommandControls](#sldrcommandcontrols) | field_6E8 |
| `AF956B73` | [SLdrCommandControls](#sldrcommandcontrols) | field_770 |
| `77031C13` | [SLdrCommandControls](#sldrcommandcontrols) | field_7F8 |
| `3E73F38B` | [SLdrCommandControls](#sldrcommandcontrols) | field_880 |

### SLdrPlayerMovementParameters
| Field | Type | Description |
| --- | --- | --- |
| `A5A80B2B` | Float | field_0 |
| `AB43FDE9` | Float | field_4 |
| `0DB9CC20` | Float | field_8 |
| `720B76E5` | Float | field_C |
| `619B09A9` | Float | field_10 |
| `36066FB4` | Float | field_14 |
| `D9BA2208` | Float | field_18 |
| `2BCB63F3` | Float | field_1C |
| `D450A119` | Float | field_20 |
| `61590275` | Float | field_24 |
| `3DA12783` | Float | field_28 |

### SLdrPlayerMultiKillRewardData
| Field | Type | Description |
| --- | --- | --- |
| `7C8E9D07` | [CMayaSpline] | field_0 |
| `773FA8A3` | [SLdrPlayerMultiKillRewardTierData](#sldrplayermultikillrewardtierdata) | field_30 |
| `BADF4A10` | [SLdrPlayerMultiKillRewardTierData](#sldrplayermultikillrewardtierdata) | field_BC |
| `2E1E142F` | [SLdrPlayerMultiKillRewardSoundData](#sldrplayermultikillrewardsounddata) | field_148 |

### SLdrPlayerMultiKillRewardSoundData
| Field | Type | Description |
| --- | --- | --- |
| `D4128740` | [CObjectId] | field_0 |
| `DCC4F2C7` | [CObjectId] | field_10 |
| `52C5C74C` | [CObjectId] | field_20 |
| `C6A3BA54` | [CObjectId] | field_30 |
| `7B2BF8BB` | [CObjectId] | field_40 |
| `9D8E4B74` | [CObjectId] | field_50 |
| `564E9347` | [CObjectId] | field_60 |
| `EA0555FD` | [CObjectId] | field_70 |

### SLdrPlayerMultiKillRewardTierData
| Field | Type | Description |
| --- | --- | --- |
| `0E477EF3` | [SLdrPlayerItem](#sldrplayeritem) | field_0 |
| `978221CB` | Uint32 | field_4 |
| `057A4BF9` | Uint32 | field_8 |
| `25DADDC7` | Uint32 | field_C |
| `B8D1D2B1` | Float | field_10 |
| `6F5F5184` | Float | field_14 |
| `225580AC` | [CObjectId] | field_18 |
| `9B71AFF0` | [CObjectId] | field_28 |
| `79DBCEF3` | [String] | field_38 |
| `F992B8DF` | [CObjectId] | field_44 |
| `EFD13E86` | [CObjectId] | field_54 |
| `B8C2DF53` | [SLdrModelLightingData](#sldrmodellightingdata) | field_64 |
| `13DB8BD2` | [List]&lt;[SLdrMaterialDataOverride](#sldrmaterialdataoverride)&gt; | field_80 |

### SLdrPlayerOffscreenData
| Field | Type | Description |
| --- | --- | --- |
| `EDA6126E` | Float | field_0 |
| `697E4A7C` | Float | field_4 |
| `E3F0F705` | Uint32 | field_8 |
| `5658A5B3` | Uint32 | field_C |
| `12C4A47A` | [CObjectId] | field_10 |
| `2A9141E7` | [CObjectId] | field_20 |
| `90E70F35` | [SLdrPlayerOffscreenIndicatorTextData](#sldrplayeroffscreenindicatortextdata) | field_30 |
| `74812F08` | [SLdrPlayerOffscreenIndicatorIconData](#sldrplayeroffscreenindicatoricondata) | field_70 |

### SLdrPlayerOffscreenIndicatorIconData
| Field | Type | Description |
| --- | --- | --- |
| `527BFCFF` | [CObjectId] | field_0 |
| `2C36E9B7` | [SLdrPlayerOffscreenIndicatorRect](#sldrplayeroffscreenindicatorrect) | field_10 |

### SLdrPlayerOffscreenIndicatorRect
| Field | Type | Description |
| --- | --- | --- |
| `4C6D583D` | Uint32 | field_0 |
| `0E0787FE` | Uint32 | field_4 |
| `A138ECE6` | Bool | field_8 |
| `60434E43` | Uint32 | field_C |
| `FAB624B4` | Uint32 | field_10 |

### SLdrPlayerOffscreenIndicatorTextData
| Field | Type | Description |
| --- | --- | --- |
| `40DF3CEA` | [CColor4f] | field_0 |
| `E3D0C9F8` | [SLdrSimpleFont](#sldrsimplefont) | field_10 |
| `D73C63EB` | [SLdrPlayerOffscreenIndicatorRect](#sldrplayeroffscreenindicatorrect) | field_2C |

### SLdrPlayerPeanutGunData
| Field | Type | Description |
| --- | --- | --- |
| `97AD2B50` | Bool | field_0 |
| `1583BE03` | Float | field_4 |
| `D08E280D` | Bool | field_8 |
| `6BEF6B14` | Bool | field_9 |
| `099CD373` | Bool | field_A |
| `00C8768D` | [String] | field_C |
| `2B95349A` | [String] | field_18 |
| `6684795C` | [String] | field_24 |
| `6A05E002` | Bool | field_30 |

### SLdrPlayerPeriodicAdditiveAnimationData
| Field | Type | Description |
| --- | --- | --- |
| `1893E575` | Float | field_0 |
| `CB8672D5` | Float | field_4 |
| `9D4BB60E` | [String] | field_8 |

### SLdrPlayerPogoStickData
| Field | Type | Description |
| --- | --- | --- |
| `B0A0F80C` | Float | field_0 |
| `A6D59FC5` | [SLdrPlayerJumpHeights](#sldrplayerjumpheights) | field_4 |
| `00C95C9B` | [CObjectId] | field_64 |

### SLdrPlayerProxy
| Field | Type | Description |
| --- | --- | --- |
| `86CA69F4` | Bool | field_0 |
| `E199ECCF` | Bool | field_1 |
| `E51722C6` | Bool | field_2 |
| `FA6509A8` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_3 |
| `52A9DA2A` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_A |
| `E0D8749C` | Float | field_14 |
| `35370CBD` | Float | field_18 |
| `95B93F00` | Float | field_1C |
| `9B2B2FA4` | Float | field_20 |
| `0DF0BD33` | Float | field_24 |
| `F9253EB1` | Uint32 | field_28 |

### SLdrPlayerRespawn
| Field | Type | Description |
| --- | --- | --- |
| `D8A53275` | Bool | field_0 |
| `ACF911EB` | Float | field_4 |
| `8C13A2CA` | Bool | field_8 |
| `B1C02D18` | [SLdrPlayerRespawnData](#sldrplayerrespawndata) | field_C |
| `1CE9EDBE` | [SLdrPlayerGameoverData](#sldrplayergameoverdata) | field_38 |
| `7BCBD2C1` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_50 |
| `286A9786` | [String] | field_6C |
| `B9E90866` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_78 |
| `9E40BE9C` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_94 |
| `095803A0` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_B0 |
| `2D8B8A88` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_CC |
| `643CCCBC` | [SLdrCharacterAnimationSet](#sldrcharacteranimationset) | field_E8 |
| `53EBDFE4` | [List]&lt;[CGuid]&gt; | field_104 |

### SLdrPlayerRespawnData
| Field | Type | Description |
| --- | --- | --- |
| `639B32C0` | Bool | field_0 |
| `7BE6DDA1` | Float | field_4 |
| `13462118` | Float | field_8 |
| `2E214F22` | Float | field_C |
| `D74606AC` | Float | field_10 |
| `9C7D3AD6` | Float | field_14 |
| `8376E189` | Float | field_18 |
| `F1404A08` | [CObjectId] | field_1C |

### SLdrPlayerRollData
| Field | Type | Description |
| --- | --- | --- |
| `B30D04F8` | [CVector3f] | field_0 |
| `E89F00C4` | Float | field_C |
| `91CAE8CB` | Float | field_10 |
| `A1DF6BC7` | Float | field_14 |
| `57A6B878` | Float | field_18 |
| `BC31C19B` | Float | field_1C |
| `DCDE846F` | [SLdrPlayerAttackBounceData](#sldrplayerattackbouncedata) | field_20 |
| `0172DE32` | Float | field_78 |
| `8EE1D32E` | Float | field_7C |
| `6D99D348` | Float | field_80 |
| `8606A0C0` | Float | field_84 |
| `AB58C82D` | Float | field_88 |
| `04867906` | [CObjectId] | field_8C |

### SLdrPlayerShieldData
| Field | Type | Description |
| --- | --- | --- |
| `61A4DC91` | Float | field_0 |
| `630E3BAE` | Float | field_4 |
| `CC2CB831` | Float | field_8 |

### SLdrPlayerSlaveData
| Field | Type | Description |
| --- | --- | --- |
| `5665012F` | Float | field_0 |
| `36B98734` | Float | field_4 |
| `5B5CC29F` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_8 |
| `422004C6` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_F |

### SLdrPlayerSlideData
| Field | Type | Description |
| --- | --- | --- |
| `7A998F93` | Float | field_0 |
| `63E2CEC9` | Float | field_4 |
| `C9E0A9A4` | Float | field_8 |
| `DDE29C22` | Float | field_C |
| `D48C95F4` | Float | field_10 |
| `CEDD9529` | Float | field_14 |
| `AC2C1705` | Float | field_18 |
| `0D26D98B` | Float | field_1C |
| `6F5D8E4D` | Float | field_20 |
| `6313145D` | Float | field_24 |
| `4A83BE0B` | Float | field_28 |
| `DAE56416` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_2C |
| `2C3F4DE0` | Float | field_CC |
| `185483B6` | [List]&lt;[SLdrMaterialSoundPair](#sldrmaterialsoundpair)&gt; | field_D0 |

### SLdrPlayerSlipperySurfaceSoundData
| Field | Type | Description |
| --- | --- | --- |
| `09633C8C` | Float | field_0 |
| `2A683050` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_4 |
| `A92F6A98` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_A4 |

### SLdrPlayerSound
| Field | Type | Description |
| --- | --- | --- |
| `1C7ADEB9` | Bool | field_0 |
| `326AC711` | Bool | field_1 |
| `85993698` | Bool | field_2 |

### SLdrPlayerSplineAdvancementData
| Field | Type | Description |
| --- | --- | --- |
| `9C694A55` | [SLdrPlayerMovementParameters](#sldrplayermovementparameters) | field_0 |
| `F167ABF9` | [SLdrPlayerMovementParameters](#sldrplayermovementparameters) | field_2C |
| `95DF952F` | Float | field_58 |
| `C2A8F2A9` | Bool | field_5C |
| `EADD6B6C` | Float | field_60 |
| `3C8F68A4` | Bool | field_64 |
| `863CF1D5` | Bool | field_65 |
| `46224E09` | Float | field_68 |
| `B0868552` | Float | field_6C |
| `AB296E96` | Float | field_70 |
| `D373D9EA` | Float | field_74 |
| `6DDB5F15` | Float | field_78 |
| `52E7D0FD` | Float | field_7C |
| `C2120004` | [SLdrPlayerSlipperySurfaceSoundData](#sldrplayerslipperysurfacesounddata) | field_80 |
| `0C99D747` | Bool | field_1C4 |

### SLdrPlayerStalledDescentData
| Field | Type | Description |
| --- | --- | --- |
| `9298F433` | Float | field_0 |
| `4FC8D2C0` | Float | field_4 |
| `62D96F8F` | Float | field_8 |
| `D14AF202` | Float | field_C |
| `866200C4` | [String] | field_10 |
| `19B73434` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_1C |
| `2E9CC2A7` | [SLdrExplosionData](#sldrexplosiondata) | field_BC |
| `F2FB84E3` | [SLdrExplosionData](#sldrexplosiondata) | field_F0 |
| `3A342063` | [SLdrExplosionData](#sldrexplosiondata) | field_124 |

### SLdrPlayerSwimCollisionData
| Field | Type | Description |
| --- | --- | --- |
| `785C5B96` | Float | field_0 |
| `777C787B` | Float | field_4 |
| `4E5D3748` | Float | field_8 |

### SLdrPlayerSwimMovementData
| Field | Type | Description |
| --- | --- | --- |
| `8A771E7C` | Float | field_0 |
| `E2BA6240` | Float | field_4 |
| `F18C14FE` | Float | field_8 |
| `0DFEFC2B` | Float | field_C |
| `27A7374E` | Float | field_10 |
| `E4A4FDFE` | Float | field_14 |
| `CB9BC577` | Float | field_18 |
| `80B0E5A0` | Float | field_1C |
| `926EA8D8` | Float | field_20 |
| `A0A976E6` | Float | field_24 |
| `07389752` | Float | field_28 |
| `AA5B0425` | Float | field_2C |
| `CE5B9922` | Float | field_30 |
| `AE55FE76` | Float | field_34 |
| `ADE00FD2` | Float | field_38 |
| `B42E54C5` | [SLdrPlayerSwimSteeringData](#sldrplayerswimsteeringdata) | field_3C |
| `1AF9900C` | [SLdrPlayerSwimSteeringData](#sldrplayerswimsteeringdata) | field_4C |
| `F6CD66AA` | Float | field_5C |
| `2C0D9F4D` | Float | field_60 |

### SLdrPlayerSwimSteeringData
| Field | Type | Description |
| --- | --- | --- |
| `07B2E2AB` | Float | field_0 |
| `F1D06EA6` | Float | field_4 |
| `81C0A342` | Float | field_8 |
| `51902C3B` | Float | field_C |

### SLdrPlayerSwimSurfaceData
| Field | Type | Description |
| --- | --- | --- |
| `7747ADCE` | [SLdrExplosionData](#sldrexplosiondata) | field_0 |

### SLdrPlayerSwingData
| Field | Type | Description |
| --- | --- | --- |
| `C73B5F6A` | Float | field_0 |
| `2AE6F8F4` | Float | field_4 |
| `8FC88B48` | Float | field_8 |
| `A47D5018` | Float | field_C |
| `5BC7FEE4` | Float | field_10 |
| `79BA3E41` | Float | field_14 |
| `227D2321` | Float | field_18 |
| `998D0888` | Float | field_1C |
| `3BF0E4E9` | Float | field_20 |
| `DF4A673F` | Float | field_24 |
| `7791005E` | Float | field_28 |
| `4BBCFE5C` | Float | field_2C |
| `FAFD5EB7` | Float | field_30 |
| `50BCC6A4` | Float | field_34 |
| `C876082F` | Float | field_38 |
| `9D0190F9` | Float | field_3C |
| `75B3A202` | Float | field_40 |
| `0CB7A7DC` | Float | field_44 |
| `88936CFF` | Float | field_48 |
| `010807B4` | Float | field_4C |
| `ED77B09C` | Float | field_50 |
| `375723EC` | Float | field_54 |
| `F35FE5A9` | Float | field_58 |
| `9574C5F0` | Float | field_5C |
| `6D14AC72` | Float | field_60 |
| `94DF331E` | Float | field_64 |
| `F082C804` | Float | field_68 |
| `5C81085C` | Float | field_6C |

### SLdrPlayerTeleportData
| Field | Type | Description |
| --- | --- | --- |
| `E6F227F7` | [String] | field_0 |
| `4169E9B2` | Float | field_C |
| `492CB24D` | [SLdrConvergence](#sldrconvergence) | field_10 |

### SLdrPlayerTerrainAlignmentData
| Field | Type | Description |
| --- | --- | --- |
| `16CEECAF` | Bool | field_0 |
| `6E0D14DC` | [CVector3f] | field_4 |
| `805D7AAF` | Float | field_10 |
| `110DFB35` | Float | field_14 |

### SLdrPlayerTireInteractionData
| Field | Type | Description |
| --- | --- | --- |
| `9EACA305` | Float | field_0 |
| `BA37F076` | Float | field_4 |
| `AD2AA0D7` | Float | field_8 |
| `38E1588A` | Float | field_C |

### SLdrPlayerType
| Field | Type | Description |
| --- | --- | --- |
| `DF0E4092` | [enum_10065c08](#enum_10065c08) | field_0 |

### SLdrPlayerZiplineData
| Field | Type | Description |
| --- | --- | --- |
| `19E4AE12` | Float | field_0 |
| `743705E7` | Float | field_4 |
| `5256D66C` | Float | field_8 |
| `A8C43A25` | [SLdrExplosionData](#sldrexplosiondata) | field_C |
| `B948C431` | [CVector3f] | field_40 |
| `70EF71ED` | [SLdrExplosionData](#sldrexplosiondata) | field_4C |
| `568E400E` | [CVector3f] | field_80 |

### SLdrPlaylist
| Field | Type | Description |
| --- | --- | --- |
| `EFD8D539` | [List]&lt;[SLdrPlaylistActions](#sldrplaylistactions)&gt; | field_0 |

### SLdrPlaylistActions
| Field | Type | Description |
| --- | --- | --- |
| `BBA645D8` | Uint32 | field_0 |
| `DD427CDC` | [List]&lt;Int32&gt; | field_4 |

### SLdrPoiObject
| Field | Type | Description |
| --- | --- | --- |
| `0F8DE094` | Uint32 | field_0 |
| `ED96CD47` | Float | field_4 |
| `962CB720` | Bool | field_8 |
| `16B72E03` | Bool | field_9 |
| `19C5B259` | Float | field_C |
| `8E459FBB` | Float | field_10 |
| `CBF25BC5` | Bool | field_14 |
| `570E8FAC` | Bool | field_15 |

### SLdrPolarBear
| Field | Type | Description |
| --- | --- | --- |
| `20B95C9C` | [List]&lt;[Property]&gt; | field_0 |

### SLdrPolarBearActionPhase
| Field | Type | Description |
| --- | --- | --- |
| `76D88AF4` | [List]&lt;[Property]&gt; | field_0 |
| `6838A60D` | [Property] | field_C |
| `F322E014` | Uint32 | field_14 |

### SLdrPolarBearControllerData
| Field | Type | Description |
| --- | --- | --- |
| `8B9CBFC5` | Uint32 | field_0 |
| `4A30945C` | [List]&lt;[SLdrPolarBearActionPhase](#sldrpolarbearactionphase)&gt; | field_4 |
| `B9275410` | String | field_10 |

### SLdrPolarBearCubeSling
| Field | Type | Description |
| --- | --- | --- |
| `636F00CD` | [Property] | field_0 |

### SLdrPolarBearDelayedSlam
| Field | Type | Description |
| --- | --- | --- |
| `363896AF` | [Property] | field_0 |

### SLdrPolarBearIcyCharge
| Field | Type | Description |
| --- | --- | --- |
| `1875C4D1` | [Property] | field_0 |

### SLdrPolarBearIcyRoar
| Field | Type | Description |
| --- | --- | --- |
| `B64ED435` | [Property] | field_0 |

### SLdrPolarBearMegaLeap
| Field | Type | Description |
| --- | --- | --- |
| `C73A32E2` | [Property] | field_0 |

### SLdrPolarBearMegaSlam
| Field | Type | Description |
| --- | --- | --- |
| `8C8A9D13` | [Property] | field_0 |

### SLdrPolarBearRandomAction
| Field | Type | Description |
| --- | --- | --- |
| `D7949143` | [List]&lt;[SLdrPolarBearRandomActionData](#sldrpolarbearrandomactiondata)&gt; | field_0 |

### SLdrPolarBearRandomActionData
| Field | Type | Description |
| --- | --- | --- |
| `332AE0FF` | Uint32 | field_0 |
| `93AEFD7F` | [Property] | field_4 |

### SLdrPolarBearSlammerTime
This struct does not have any fields

### SLdrPolarBearSummersaultSlam
| Field | Type | Description |
| --- | --- | --- |
| `73C5BAB1` | [Property] | field_0 |

### SLdrPositionAtTimeSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `9961F548` | [CMayaSpline] | field_0 |
| `E32F0536` | Float | field_30 |
| `3DBD4BE8` | Float | field_34 |
| `ED969F0F` | [enum_100822f8](#enum_100822f8) | field_38 |

### SLdrPrimaryTargetTrackingBehaviorData
This struct does not have any fields

### SLdrProductionFrontEndProxy
This struct does not have any fields

### SLdrProgressiveForceField
| Field | Type | Description |
| --- | --- | --- |
| `3B0FF045` | [CVector3f] | field_0 |
| `CE51A513` | Bool | field_C |
| `291FB57E` | [CMayaSpline] | field_10 |

### SLdrProjectedSimpleShadowReceiver
| Field | Type | Description |
| --- | --- | --- |
| `9C46993B` | Bool | field_0 |
| `AAAFAEE5` | Bool | field_1 |
| `4B9F03C7` | [CObjectId] | field_4 |
| `D371B0C2` | [SLdrDepthBiasOverride](#sldrdepthbiasoverride) | field_14 |

### SLdrProjectile
| Field | Type | Description |
| --- | --- | --- |
| `1D2CAA5B` | [SLdrProjectileLaunchData](#sldrprojectilelaunchdata) | field_0 |
| `24D128E9` | [SLdrProjectileLifetimeData](#sldrprojectilelifetimedata) | field_3C |
| `1477F1F0` | [SLdrProjectileCollisionData](#sldrprojectilecollisiondata) | field_E8 |
| `FBB4AC81` | Bool | field_18C |
| `742A18E9` | Bool | field_18D |

### SLdrProjectileAttackActionFireProjectile
| Field | Type | Description |
| --- | --- | --- |
| `215C83DE` | Uint32 | field_0 |

### SLdrProjectileAttackActionPause
| Field | Type | Description |
| --- | --- | --- |
| `AA6FD324` | Float | field_0 |

### SLdrProjectileAttackActionSequence
| Field | Type | Description |
| --- | --- | --- |
| `CC01A3D5` | [List]&lt;[Property]&gt; | field_0 |

### SLdrProjectileAttackActionSequenceRandom
| Field | Type | Description |
| --- | --- | --- |
| `863E1A6A` | [List]&lt;[Property]&gt; | field_0 |

### SLdrProjectileAttackWeightedAction
| Field | Type | Description |
| --- | --- | --- |
| `C88EBEF5` | Float | field_0 |
| `8D32B2D5` | [Property] | field_4 |

### SLdrProjectileBounceData
| Field | Type | Description |
| --- | --- | --- |
| `5B6FCB7F` | Uint32 | field_0 |
| `2446D920` | Float | field_4 |
| `77871F50` | Float | field_8 |
| `94EF4630` | Float | field_C |
| `A1859146` | [SLdrExplosionData](#sldrexplosiondata) | field_10 |
| `B8AE2BC2` | Bool | field_44 |
| `5980032E` | [CVector3f] | field_48 |
| `69FD9016` | [enum_10072584](#enum_10072584) | field_54 |
| `EF5BF2DA` | Bool | field_58 |
| `30AAE17C` | Bool | field_59 |
| `EB7C7CC2` | Bool | field_5A |

### SLdrProjectileCollisionData
| Field | Type | Description |
| --- | --- | --- |
| `38269260` | [Property] | field_0 |
| `484976DE` | Bool | field_8 |
| `1D3A2A0D` | Bool | field_9 |
| `11232AFB` | Bool | field_A |
| `E0FF6220` | Bool | field_B |
| `B1330D9E` | Bool | field_C |
| `70A56AC8` | [SLdrProjectileBounceData](#sldrprojectilebouncedata) | field_10 |
| `52B27FD1` | [List]&lt;[SLdrProjectileCollisionResponseData](#sldrprojectilecollisionresponsedata)&gt; | field_6C |
| `46735B04` | [SLdrDamageInfo](#sldrdamageinfo) | field_78 |
| `BA37938E` | Bool | field_9C |
| `94EA9C9F` | Float | field_A0 |

### SLdrProjectileCollisionIgnoreFlags
| Field | Type | Description |
| --- | --- | --- |
| `3F7BF6BA` | Bool | field_0 |
| `62CEEBB0` | Bool | field_1 |
| `04A16BC8` | Bool | field_2 |
| `DC9AB8F2` | Bool | field_3 |
| `26DDA71E` | Bool | field_4 |
| `CC160DEB` | Bool | field_5 |
| `61C9FDDD` | Bool | field_6 |
| `1C8EFD05` | Bool | field_7 |
| `66350B50` | Bool | field_8 |

### SLdrProjectileCollisionPrimitiveAABox
| Field | Type | Description |
| --- | --- | --- |
| `A00EC692` | [Property] | field_0 |
| `C51CB4FA` | [SLdrProjectileCollisionPrimitiveIgnoreFlags](#sldrprojectilecollisionprimitiveignoreflags) | field_8 |

### SLdrProjectileCollisionPrimitiveIgnoreFlags
| Field | Type | Description |
| --- | --- | --- |
| `27A03E2C` | [SLdrProjectileCollisionIgnoreFlags](#sldrprojectilecollisionignoreflags) | field_0 |
| `C688B1DF` | [SLdrProjectileCollisionIgnoreFlags](#sldrprojectilecollisionignoreflags) | field_9 |
| `F7AC4EF9` | Bool | field_12 |

### SLdrProjectileCollisionPrimitiveModelBounds
| Field | Type | Description |
| --- | --- | --- |
| `775405EF` | [SLdrProjectileCollisionPrimitiveIgnoreFlags](#sldrprojectilecollisionprimitiveignoreflags) | field_0 |

### SLdrProjectileCollisionPrimitiveSphere
| Field | Type | Description |
| --- | --- | --- |
| `61B40DFA` | [Property] | field_0 |
| `4F5E1EFB` | [SLdrProjectileCollisionPrimitiveIgnoreFlags](#sldrprojectilecollisionprimitiveignoreflags) | field_8 |

### SLdrProjectileCollisionResponseData
| Field | Type | Description |
| --- | --- | --- |
| `5BB37C51` | [enum_100725bc](#enum_100725bc) | field_0 |
| `3441AA04` | [SLdrExplosionData](#sldrexplosiondata) | field_4 |
| `95507586` | Bool | field_38 |

### SLdrProjectileColorFadeData
| Field | Type | Description |
| --- | --- | --- |
| `F033D30B` | Float | field_0 |
| `68A9BF83` | Float | field_4 |
| `E4BC4AFF` | [CColor4f] | field_8 |
| `ADAB1DCB` | [CColor4f] | field_18 |
| `294DC894` | [CColor4f] | field_28 |
| `EA8B8272` | Bool | field_38 |
| `7AE7A309` | Bool | field_39 |
| `1A622474` | Bool | field_3A |

### SLdrProjectileEffectData
| Field | Type | Description |
| --- | --- | --- |
| `BE31CAF2` | [CObjectId] | field_0 |
| `23FC48AA` | Bool | field_10 |

### SLdrProjectileLaunchData
| Field | Type | Description |
| --- | --- | --- |
| `8539AEE1` | [SLdrExplosionData](#sldrexplosiondata) | field_0 |
| `8A2161C5` | [Property] | field_34 |

### SLdrProjectileLifetimeData
| Field | Type | Description |
| --- | --- | --- |
| `B68FDB8D` | Float | field_0 |
| `78CE6E99` | Float | field_4 |
| `B00114F7` | Bool | field_8 |
| `14E5CF51` | [List]&lt;[SLdrProjectileEffectData](#sldrprojectileeffectdata)&gt; | field_C |
| `9D8442DC` | [CObjectId] | field_18 |
| `D78CAB39` | [enum_100725f8](#enum_100725f8) | field_28 |
| `EBEF249B` | Bool | field_2C |
| `A9785D5B` | [CVector3f] | field_30 |
| `F3DFB351` | [CVector3f] | field_3C |
| `ACB838A6` | [CVector3f] | field_48 |
| `22E850BA` | Bool | field_54 |
| `CB573F46` | [SLdrProjectileColorFadeData](#sldrprojectilecolorfadedata) | field_58 |
| `DB030318` | Float | field_94 |
| `F799D5CD` | [CVector3f] | field_98 |
| `F1C70234` | [Property] | field_A4 |

### SLdrProjectileMotionHomingMissile
| Field | Type | Description |
| --- | --- | --- |
| `94439F7F` | [enum_1008169c](#enum_1008169c) | field_0 |
| `F17C6DCB` | Float | field_4 |
| `2DFA8465` | [CMayaSpline] | field_8 |

### SLdrProjectileMotionPhysics
| Field | Type | Description |
| --- | --- | --- |
| `6CFCAA93` | [enum_100817d8](#enum_100817d8) | field_0 |
| `36288388` | [enum_10081788](#enum_10081788) | field_4 |
| `6134BDF7` | [CVector3f] | field_8 |
| `513AB727` | [CVector3f] | field_14 |
| `B83C3432` | Float | field_20 |
| `9B24DA44` | Float | field_24 |
| `0348D3A0` | Float | field_28 |
| `1160B1F2` | Float | field_2C |
| `793C77EE` | Float | field_30 |
| `BB70337F` | [enum_10072584](#enum_10072584) | field_34 |
| `B77B5FC0` | Bool | field_38 |
| `E4F59846` | Float | field_3C |
| `15096C1F` | Bool | field_40 |

### SLdrProjectileMotionSpline
| Field | Type | Description |
| --- | --- | --- |
| `41EF4565` | [CMayaSpline] | field_0 |
| `8CC8DA65` | [CMayaSpline] | field_30 |
| `CCD1E5D0` | [CMayaSpline] | field_60 |

### SLdrProjectileMotionTargetedPhysics
| Field | Type | Description |
| --- | --- | --- |
| `CF20F779` | [enum_100819cc](#enum_100819cc) | field_0 |
| `1E311363` | Float | field_4 |
| `E804CC34` | [enum_100819fc](#enum_100819fc) | field_8 |
| `4EC84D1B` | Float | field_C |
| `728C37F7` | Float | field_10 |
| `9F2CCA1C` | Float | field_14 |
| `38FF2038` | Float | field_18 |
| `ADCF33BA` | Bool | field_1C |
| `47782505` | Bool | field_1D |
| `FCB2F7E3` | Float | field_20 |
| `9CC408C6` | Float | field_24 |
| `44DF472D` | Bool | field_28 |
| `27EF6261` | Float | field_2C |
| `66EA0819` | Float | field_30 |
| `0D085E38` | Bool | field_34 |
| `9E349EAE` | Bool | field_35 |
| `6C50FD67` | Bool | field_36 |
| `6C6ABC25` | Float | field_38 |
| `6FFF2FB4` | Float | field_3C |
| `4A41121B` | Bool | field_40 |
| `DD59E501` | Float | field_44 |
| `4F67BAEE` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_48 |

### SLdrProjectileMotionTargetedSpline
| Field | Type | Description |
| --- | --- | --- |
| `2F61C44B` | [enum_10081b18](#enum_10081b18) | field_0 |
| `695FA98E` | Float | field_4 |
| `70F742FB` | Float | field_8 |
| `20A365A5` | [CMayaSpline] | field_C |
| `EF309C61` | [CMayaSpline] | field_3C |
| `2269C05D` | Bool | field_6C |
| `89B8B5C3` | Bool | field_6D |

### SLdrProjectileMotionTerrainMovement
| Field | Type | Description |
| --- | --- | --- |
| `2D71AF6A` | Float | field_0 |
| `E3A6E3EB` | Bool | field_4 |
| `F8AD1108` | Bool | field_5 |
| `9FE8F876` | Bool | field_6 |
| `44BB6327` | Bool | field_7 |
| `C71A19EA` | [SLdrTerrainAlignment](#sldrterrainalignment) | field_8 |

### SLdrProjectileMotionWaterCurrent
This struct does not have any fields

### SLdrProjectileMotionWaypointFollower
| Field | Type | Description |
| --- | --- | --- |
| `5574738F` | [enum_1005b060](#enum_1005b060) | field_0 |
| `AC9A023C` | [CMayaSpline] | field_4 |

### SLdrProportionalConvergenceData
| Field | Type | Description |
| --- | --- | --- |
| `1762266E` | Float | field_0 |
| `172BC391` | [CMayaSpline] | field_4 |

### SLdrPufferFish
| Field | Type | Description |
| --- | --- | --- |
| `8D31A9C7` | [List]&lt;[Property]&gt; | field_0 |

### SLdrPufferFishActionPhase
| Field | Type | Description |
| --- | --- | --- |
| `07E4BF3E` | [List]&lt;[Property]&gt; | field_0 |
| `A79AA77B` | [Property] | field_C |
| `DBE3BF32` | Uint32 | field_14 |

### SLdrPufferFishBounceAnimDriven
| Field | Type | Description |
| --- | --- | --- |
| `45B4E2AE` | [enum_100747f0](#enum_100747f0) | field_0 |
| `9D1D788F` | Uint32 | field_4 |
| `1170FE25` | Uint32 | field_8 |
| `9E784758` | [enum_10074818](#enum_10074818) | field_C |

### SLdrPufferFishBounceSeekPlayer
| Field | Type | Description |
| --- | --- | --- |
| `ECC79EB3` | [enum_10074818](#enum_10074818) | field_0 |
| `87EA3B2E` | Float | field_4 |
| `59B10F76` | Float | field_8 |
| `8D67290C` | Float | field_C |
| `5F6AE3E1` | Float | field_10 |
| `68BAE6D0` | Float | field_14 |
| `6313EB30` | Float | field_18 |

### SLdrPufferFishControllerData
| Field | Type | Description |
| --- | --- | --- |
| `9453C6C6` | [enum_10074818](#enum_10074818) | field_0 |
| `A6725D64` | Uint32 | field_4 |
| `2B1415A4` | [List]&lt;[SLdrPufferFishActionPhase](#sldrpufferfishactionphase)&gt; | field_8 |
| `77FBF6B4` | Float | field_14 |
| `C845A0BD` | [Property] | field_18 |
| `36155D63` | [Property] | field_20 |
| `17C2ADAD` | [Property] | field_28 |
| `8C8775DE` | [Property] | field_30 |
| `EC69FEF6` | [String] | field_38 |
| `C60485DB` | Float | field_44 |
| `0F5DAD9B` | [Property] | field_48 |
| `74851552` | String | field_50 |

### SLdrPufferFishExhale
| Field | Type | Description |
| --- | --- | --- |
| `61C9492B` | [enum_10074a70](#enum_10074a70) | field_0 |

### SLdrPufferFishInhale
This struct does not have any fields

### SLdrPufferFishMegaRoll
| Field | Type | Description |
| --- | --- | --- |
| `C94E3447` | Float | field_0 |
| `2B6A0FE6` | Float | field_4 |

### SLdrPufferFishSpitObjects
| Field | Type | Description |
| --- | --- | --- |
| `82CB28D9` | Bool | field_0 |
| `361244F1` | Float | field_4 |
| `FFA16B66` | Float | field_8 |
| `24A40313` | NPufferFishPasDefs::EGeneratedObjectType | field_C |
| `85DC373D` | Float | field_18 |
| `F551598A` | Float | field_1C |
| `5F60040A` | Float | field_20 |
| `2DF0D69F` | [enum_10074dbc](#enum_10074dbc) | field_24 |
| `151BC4F2` | [enum_10074a70](#enum_10074a70) | field_28 |

### SLdrPufferFishSwimCharge
| Field | Type | Description |
| --- | --- | --- |
| `A3A9498A` | Uint32 | field_0 |
| `08436A98` | Float | field_4 |
| `F2AF7565` | Float | field_8 |
| `38B9A4B9` | Float | field_C |
| `3717C8A2` | Float | field_10 |
| `FF3D6777` | [SLdrKnockbackProceduralData](#sldrknockbackproceduraldata) | field_14 |
| `197A33A3` | Float | field_20 |
| `E82009D7` | Uint32 | field_24 |
| `5775882D` | [Property] | field_28 |
| `AC002264` | Float | field_30 |
| `7BBDB17E` | Bool | field_34 |
| `CADF6CF4` | Float | field_38 |
| `7CC068EC` | Float | field_3C |
| `F16AD44A` | Float | field_40 |
| `6BA0301D` | Float | field_44 |

### SLdrPufferFishSwimSeekPlayer
| Field | Type | Description |
| --- | --- | --- |
| `534C3C11` | Float | field_0 |
| `D29C6BF4` | [enum_10074818](#enum_10074818) | field_4 |
| `A0982672` | Float | field_8 |

### SLdrPufferFishWallSlam
| Field | Type | Description |
| --- | --- | --- |
| `A17C013C` | Uint32 | field_0 |

### SLdrPullbackMotionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `FD3159E6` | Float | field_0 |
| `72ABAF72` | [SLdrConvergence](#sldrconvergence) | field_4 |

### SLdrRambiControllerData
| Field | Type | Description |
| --- | --- | --- |
| `6F4B4A83` | Float | field_0 |
| `08212A3C` | Float | field_4 |
| `FDA2638E` | Float | field_8 |
| `90B20241` | Float | field_C |
| `0948E616` | Float | field_10 |
| `95B33485` | Float | field_14 |

### SLdrRambiCrate
| Field | Type | Description |
| --- | --- | --- |
| `AAB7F099` | [CObjectId] | field_0 |
| `BE20747E` | [String] | field_10 |
| `0CE52E90` | [String] | field_1C |
| `3E3291D1` | Float | field_28 |
| `D84C61C0` | Float | field_2C |
| `1615D964` | Float | field_30 |
| `BF341699` | [SLdrExplosionData](#sldrexplosiondata) | field_34 |

### SLdrRandomBopJumpSequence
| Field | Type | Description |
| --- | --- | --- |
| `1E5AC262` | [List]&lt;[SLdrBopJumpProceduralJumpData](#sldrbopjumpproceduraljumpdata)&gt; | field_0 |

### SLdrRectangle
| Field | Type | Description |
| --- | --- | --- |
| `5794204E` | Float | field_0 |
| `72103D5E` | Float | field_4 |

### SLdrRelay
| Field | Type | Description |
| --- | --- | --- |
| `F59484E6` | Bool | field_0 |
| `49D81978` | Bool | field_1 |

### SLdrRelayAutoFire
This struct does not have any fields

### SLdrRelayConditional
| Field | Type | Description |
| --- | --- | --- |
| `3FFE7883` | Bool | field_0 |
| `C2E39C54` | [SLdrRelayConditionalTest](#sldrrelayconditionaltest) | field_4 |
| `052EB2FA` | [SLdrRelayConditionalTest](#sldrrelayconditionaltest) | field_1C |
| `2292940A` | [SLdrRelayConditionalTest](#sldrrelayconditionaltest) | field_34 |
| `67249679` | [SLdrRelayConditionalTest](#sldrrelayconditionaltest) | field_4C |

### SLdrRelayConditionalTest
| Field | Type | Description |
| --- | --- | --- |
| `07DBAD20` | [enum_1006d010](#enum_1006d010) | field_0 |
| `D3802722` | [enum_1006d028](#enum_1006d028) | field_4 |
| `4F8C21DE` | [enum_1006d060](#enum_1006d060) | field_8 |
| `02C55115` | [enum_1006d028](#enum_1006d028) | field_C |
| `F1D4D4B4` | [SLdrPlayerItem](#sldrplayeritem) | field_10 |
| `47C63B1D` | Uint32 | field_14 |

### SLdrRelayProbabilityGameMode
| Field | Type | Description |
| --- | --- | --- |
| `5F595FE7` | [SLdrRelayProbabilityGameModeData](#sldrrelayprobabilitygamemodedata) | field_0 |
| `2FBAC003` | [SLdrRelayProbabilityGameModeData](#sldrrelayprobabilitygamemodedata) | field_28 |
| `1F8ADB0E` | [SLdrRelayProbabilityGameModeData](#sldrrelayprobabilitygamemodedata) | field_50 |
| `7F316A52` | [SLdrRelayProbabilityGameModeData](#sldrrelayprobabilitygamemodedata) | field_78 |

### SLdrRelayProbabilityGameModeData
| Field | Type | Description |
| --- | --- | --- |
| `C78402D5` | Float | field_0 |
| `2A20B180` | Float | field_4 |
| `6E386824` | Float | field_8 |
| `A4198C41` | Float | field_C |
| `58DF2013` | Float | field_10 |
| `A7E440E4` | Float | field_14 |
| `0D793710` | Float | field_18 |
| `D4DEE41E` | Float | field_1C |
| `84BB91F2` | Float | field_20 |
| `63F6DAC4` | Float | field_24 |

### SLdrRelayRandom
| Field | Type | Description |
| --- | --- | --- |
| `2BE9FABC` | Bool | field_0 |
| `95934127` | Bool | field_1 |
| `A4C065DB` | Uint32 | field_4 |
| `2FB6BB5E` | Uint32 | field_8 |
| `E43DAE98` | Uint32 | field_C |
| `C5DAB447` | Uint32 | field_10 |
| `9C327FDF` | Uint32 | field_14 |
| `05C8FABA` | Bool | field_18 |

### SLdrReloadSetLoader
| Field | Type | Description |
| --- | --- | --- |
| `1BC676D9` | [List]&lt;[CGuid]&gt; | field_0 |

### SLdrRender
| Field | Type | Description |
| --- | --- | --- |
| `948D7F67` | [Property] | field_0 |
| `2B1317A0` | [SLdrModelLightingData](#sldrmodellightingdata) | field_8 |

### SLdrRenderAnimatedModel
| Field | Type | Description |
| --- | --- | --- |
| `6CD6726A` | [CObjectId] | field_0 |
| `362CA84B` | [String] | field_10 |
| `4C296D10` | Float | field_1C |
| `1B0B9230` | Float | field_20 |
| `A7B66D7A` | Bool | field_24 |
| `C60D7BB7` | Bool | field_25 |
| `18B6EBF7` | Bool | field_26 |
| `0EA96E02` | Bool | field_27 |
| `61D31DA5` | Bool | field_28 |
| `B5BFCDE3` | Float | field_2C |
| `DAF36550` | [List]&lt;[SLdrMaterialDataOverride](#sldrmaterialdataoverride)&gt; | field_30 |
| `D291C1DD` | [SLdrDepthBiasOverride](#sldrdepthbiasoverride) | field_3C |
| `AA18B454` | [SLdrRenderAnimatedModelFlags](#sldrrenderanimatedmodelflags) | field_40 |
| `DE27DFA4` | [SLdrRenderAnimatedModelSort](#sldrrenderanimatedmodelsort) | field_44 |
| `1B69D5ED` | Bool | field_4C |

### SLdrRenderAnimatedModelFlags
| Field | Type | Description |
| --- | --- | --- |
| `3FC1BA75` | Bool | field_0 |
| `B8587959` | Bool | field_1 |

### SLdrRenderAnimatedModelSort
| Field | Type | Description |
| --- | --- | --- |
| `2511DBBB` | [enum_100179c4](#enum_100179c4) | field_0 |
| `E315AEBA` | Float | field_4 |

### SLdrRenderGroup
| Field | Type | Description |
| --- | --- | --- |
| `CA976DC7` | [enum_1006d580](#enum_1006d580) | field_0 |

### SLdrRenderMethodGameMode
| Field | Type | Description |
| --- | --- | --- |
| `6F3201B9` | [Property] | field_0 |
| `1B53F39E` | [Property] | field_8 |

### SLdrRenderMethodResolver
This struct does not have any fields

### SLdrRenderStaticModel
| Field | Type | Description |
| --- | --- | --- |
| `E8BDC12B` | [CObjectId] | field_0 |
| `FE69F600` | [List]&lt;[SLdrMaterialDataOverride](#sldrmaterialdataoverride)&gt; | field_10 |
| `BA315753` | [SLdrDepthBiasOverride](#sldrdepthbiasoverride) | field_1C |
| `C88CFE7C` | [SLdrRenderStaticModelFlags](#sldrrenderstaticmodelflags) | field_20 |
| `7721158B` | [SLdrRenderStaticModelSort](#sldrrenderstaticmodelsort) | field_28 |

### SLdrRenderStaticModelArray
| Field | Type | Description |
| --- | --- | --- |
| `E2517798` | [List]&lt;[CObjectId]&gt; | field_0 |
| `B885CF8C` | [List]&lt;[SLdrMaterialDataOverride](#sldrmaterialdataoverride)&gt; | field_C |
| `233ABDFB` | [SLdrDepthBiasOverride](#sldrdepthbiasoverride) | field_18 |

### SLdrRenderStaticModelFlags
| Field | Type | Description |
| --- | --- | --- |
| `903A5083` | Bool | field_0 |
| `077F0C20` | Bool | field_1 |
| `5002B79B` | Bool | field_2 |
| `890498CC` | Bool | field_3 |
| `8A444676` | Bool | field_4 |

### SLdrRenderStaticModelSort
| Field | Type | Description |
| --- | --- | --- |
| `E3E7FFC0` | [enum_100179c4](#enum_100179c4) | field_0 |
| `9F0195E0` | Float | field_4 |

### SLdrRenderToFlash
| Field | Type | Description |
| --- | --- | --- |
| `51576F2B` | [enum_1006d728](#enum_1006d728) | field_0 |
| `29BC1438` | [enum_1006d720](#enum_1006d720) | field_4 |

### SLdrRenderWorld
| Field | Type | Description |
| --- | --- | --- |
| `9339AFEE` | [CObjectId] | field_0 |
| `1A3BC4DB` | [SLdrModelLightingData](#sldrmodellightingdata) | field_10 |
| `A1DCE201` | [SLdrRenderWorldFlags](#sldrrenderworldflags) | field_2C |

### SLdrRenderWorldFlags
| Field | Type | Description |
| --- | --- | --- |
| `EDB6D296` | Bool | field_0 |
| `7602A14A` | Bool | field_1 |

### SLdrResetDetectionCameraBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `D8BE6FE1` | Bool | field_0 |
| `A3F69626` | Bool | field_1 |
| `CC6C7350` | Float | field_4 |

### SLdrRespawn
| Field | Type | Description |
| --- | --- | --- |
| `B99A9FA4` | Bool | field_0 |
| `207FA632` | [Property] | field_4 |
| `2B213D1A` | Bool | field_C |
| `D4B2A1BE` | Bool | field_D |
| `54258A09` | Bool | field_E |
| `4CC6B5B4` | Float | field_10 |
| `3D644414` | Float | field_14 |
| `066FD586` | [enum_1006dbd0](#enum_1006dbd0) | field_18 |
| `D06121AF` | Bool | field_1C |
| `5392E41B` | Bool | field_1D |
| `EE2F13BD` | Float | field_20 |
| `EF02F369` | Float | field_24 |
| `63DA8221` | Bool | field_28 |
| `037C2133` | Bool | field_29 |
| `9563630B` | Bool | field_2A |
| `CFA2BF79` | Float | field_2C |
| `A4312C51` | Float | field_30 |
| `3F867032` | Float | field_34 |
| `832E3481` | Float | field_38 |
| `A8209738` | Bool | field_3C |
| `B2BD0E78` | Bool | field_3D |
| `4224CBE6` | Bool | field_3E |
| `53B35E6C` | Float | field_40 |
| `C80BBEEC` | Float | field_44 |
| `46E5A833` | Bool | field_48 |

### SLdrRespawnBalloon
| Field | Type | Description |
| --- | --- | --- |
| `07431838` | Float | field_0 |
| `B07FBDED` | Float | field_4 |
| `9D24B4D8` | [String] | field_8 |
| `2B69E419` | Float | field_14 |
| `C73D1C4E` | Float | field_18 |
| `2F247DEB` | [SLdrExplosionData](#sldrexplosiondata) | field_1C |
| `3FB0AA91` | [SLdrExplosionData](#sldrexplosiondata) | field_50 |

### SLdrRestrictPositionCameraBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `7075DE92` | [Property] | field_0 |
| `6B492AF0` | Bool | field_8 |
| `34E3D2F8` | Bool | field_9 |
| `E228EE5F` | Bool | field_A |
| `AC27FDB8` | Bool | field_B |

### SLdrRetronome
| Field | Type | Description |
| --- | --- | --- |
| `63162A7B` | Float | field_0 |
| `5AA73F8C` | Bool | field_4 |
| `8C75C29E` | Bool | field_5 |
| `8802E5C5` | Bool | field_6 |
| `B574F8CE` | Bool | field_7 |

### SLdrRetronomeDriver
| Field | Type | Description |
| --- | --- | --- |
| `E8D470BE` | Uint32 | field_0 |
| `FBA49457` | Uint32 | field_4 |
| `D10CD5AA` | Float | field_8 |
| `7F5566F8` | Float | field_C |
| `C566A747` | Bool | field_10 |
| `F45E20CD` | [List]&lt;Int32&gt; | field_14 |

### SLdrReverbSettings
| Field | Type | Description |
| --- | --- | --- |
| `813126BA` | Uint32 | field_0 |
| `F4F87597` | Float | field_4 |
| `6A21E4B1` | [CMayaSpline] | field_8 |
| `3264BB66` | Float | field_38 |
| `11B84DFF` | [CMayaSpline] | field_3C |
| `304DCB27` | Float | field_6C |
| `1EC9752A` | [CMayaSpline] | field_70 |
| `34185C9A` | Float | field_A0 |
| `FACD2945` | [CMayaSpline] | field_A4 |
| `B1DB5376` | Float | field_D4 |
| `764BDE84` | [CMayaSpline] | field_D8 |
| `54882C23` | Float | field_108 |
| `A296D988` | [CMayaSpline] | field_10C |

### SLdrRocketBarrelProxy
| Field | Type | Description |
| --- | --- | --- |
| `36A93DD3` | [SLdrPlayerCharactersBitField](#sldrplayercharactersbitfield) | field_0 |
| `92476CA1` | Float | field_8 |
| `35FFA1C2` | Float | field_C |
| `7400297A` | Float | field_10 |
| `B9630FC3` | Float | field_14 |
| `9655D783` | Float | field_18 |

### SLdrRocketBarrelThrustData
| Field | Type | Description |
| --- | --- | --- |
| `1A3F304A` | Float | field_0 |
| `7E5A06A3` | Float | field_4 |
| `D63BD570` | Float | field_8 |
| `E376F502` | Float | field_C |
| `59B5178A` | Float | field_10 |
| `191C3870` | Float | field_14 |
| `6BA67A9D` | Float | field_18 |
| `BF6F7CED` | Float | field_1C |
| `4294960C` | Float | field_20 |
| `81AC6934` | Float | field_24 |
| `757AA6FC` | Float | field_28 |
| `17E3F385` | Float | field_2C |
| `15E54E4F` | Float | field_30 |
| `62A3FB4B` | Float | field_34 |
| `BFD14946` | Float | field_38 |
| `C1EAA39E` | Float | field_3C |
| `C938C76D` | Float | field_40 |
| `1EBAAEC7` | Float | field_44 |
| `EBB70FFC` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_48 |
| `310B4B8F` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_E8 |
| `45796195` | Float | field_188 |
| `39B77E37` | Float | field_18C |
| `15AEC0E1` | Float | field_190 |
| `A0EDE271` | Float | field_194 |
| `EC152845` | Float | field_198 |
| `F5C3C2D2` | Float | field_19C |
| `BE89FEA3` | Float | field_1A0 |
| `33B4AD30` | Float | field_1A4 |

### SLdrRocketBarrelWakeData
| Field | Type | Description |
| --- | --- | --- |
| `4989F035` | Float | field_0 |
| `A62736CB` | Float | field_4 |
| `AF890BE4` | Float | field_8 |
| `E3E0F3C0` | Float | field_C |
| `4E0AB475` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_10 |

### SLdrRoomRenderSettings
| Field | Type | Description |
| --- | --- | --- |
| `8C6C2969` | Bool | field_0 |
| `52D6E77C` | Bool | field_1 |
| `71A12A41` | Bool | field_2 |
| `E95BE09F` | Bool | field_3 |
| `92184C73` | [CColor4f] | field_4 |

### SLdrRoomSettings
| Field | Type | Description |
| --- | --- | --- |
| `C028D01F` | [SLdrRoomRenderSettings](#sldrroomrendersettings) | field_0 |

### SLdrRuleSetData
| Field | Type | Description |
| --- | --- | --- |
| `FC22AD62` | [List]&lt;[CObjectId]&gt; | field_0 |

### SLdrRumbleEffect
| Field | Type | Description |
| --- | --- | --- |
| `1D943EC1` | Bool | field_0 |
| `E9B0D183` | Bool | field_1 |
| `C65A2B54` | Bool | field_2 |
| `A163C2EA` | Bool | field_3 |
| `F15C12C0` | Bool | field_4 |
| `B85A10CF` | Bool | field_5 |
| `3F98B46B` | Bool | field_6 |
| `62EC77C4` | Bool | field_7 |
| `ED372C0A` | [CMayaSpline] | field_8 |
| `90247CDE` | Float | field_38 |
| `B2396176` | [enum_1006e734](#enum_1006e734) | field_3C |

### SLdrScaleSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `6D527A9F` | [CMayaSpline] | field_0 |
| `D7A45EDB` | [CMayaSpline] | field_30 |
| `5865942B` | [CMayaSpline] | field_60 |

### SLdrScreenCaptureToFlash
| Field | Type | Description |
| --- | --- | --- |
| `F5DD3E20` | [enum_1006e8e0](#enum_1006e8e0) | field_0 |

### SLdrSeaLion
| Field | Type | Description |
| --- | --- | --- |
| `4A528612` | [List]&lt;[Property]&gt; | field_0 |

### SLdrSeaLionAttackPhase
| Field | Type | Description |
| --- | --- | --- |
| `EFDD0056` | Float | field_0 |
| `4F29FA45` | Bool | field_4 |
| `02B8D3F9` | [SLdrSeaLionBoppedActionList](#sldrsealionboppedactionlist) | field_8 |
| `7D57CB3F` | [List]&lt;[Property]&gt; | field_1C |
| `772229D4` | [Property] | field_28 |

### SLdrSeaLionBellyFlop
| Field | Type | Description |
| --- | --- | --- |
| `0D5AB338` | Uint32 | field_0 |
| `0CF79AF5` | Uint32 | field_4 |

### SLdrSeaLionBoppedActionList
| Field | Type | Description |
| --- | --- | --- |
| `F1C30A31` | [List]&lt;[Property]&gt; | field_0 |
| `94E809CB` | Uint32 | field_C |
| `C05B988A` | Uint32 | field_10 |

### SLdrSeaLionBreach
| Field | Type | Description |
| --- | --- | --- |
| `6B5E8683` | Float | field_0 |
| `5F63CF91` | [List]&lt;[SLdrSeaLionBreachData](#sldrsealionbreachdata)&gt; | field_4 |
| `F19D5A95` | Uint32 | field_10 |
| `6F4B4CAF` | Uint32 | field_14 |
| `0E30EAB5` | Float | field_18 |
| `B4134B0B` | Float | field_1C |

### SLdrSeaLionBreachData
| Field | Type | Description |
| --- | --- | --- |
| `49F482A9` | Uint32 | field_0 |
| `BDA1258F` | Uint32 | field_4 |
| `C794046F` | Float | field_8 |
| `E89C0F37` | Float | field_C |

### SLdrSeaLionControllerData
| Field | Type | Description |
| --- | --- | --- |
| `3F29FCF3` | String | field_0 |
| `818AB0AF` | [List]&lt;[SLdrSeaLionAttackPhase](#sldrsealionattackphase)&gt; | field_C |

### SLdrSeaLionHandStand
| Field | Type | Description |
| --- | --- | --- |
| `3D782185` | Bool | field_0 |

### SLdrSeaLionLowRoller
| Field | Type | Description |
| --- | --- | --- |
| `57061E78` | Uint32 | field_0 |
| `B2777B0B` | Uint32 | field_4 |

### SLdrSeaLionRuleSetData
This struct does not have any fields

### SLdrSeaLionSlipNFlip
| Field | Type | Description |
| --- | --- | --- |
| `3017ADE1` | Uint32 | field_0 |
| `F3AC387F` | Uint32 | field_4 |
| `B427D664` | Uint32 | field_8 |

### SLdrSeaLionSlipNStop
This struct does not have any fields

### SLdrSeaLionTossAttack
| Field | Type | Description |
| --- | --- | --- |
| `81F6D1A8` | [List]&lt;[SLdrSeaLionTossAttackTypeData](#sldrsealiontossattacktypedata)&gt; | field_0 |

### SLdrSeaLionTossAttackTypeData
| Field | Type | Description |
| --- | --- | --- |
| `EF713288` | Uint32 | field_0 |
| `BA29AF85` | [List]&lt;Int32&gt; | field_4 |
| `15F36367` | [Property] | field_10 |

### SLdrSeaLionTurboSlide
This struct does not have any fields

### SLdrSeaLionWheel
| Field | Type | Description |
| --- | --- | --- |
| `A1D7CB70` | Uint32 | field_0 |

### SLdrShopData
| Field | Type | Description |
| --- | --- | --- |
| `21506BDD` | [CObjectId] | field_0 |
| `4F21FA6D` | [List]&lt;[SLdrShopItemCost](#sldrshopitemcost)&gt; | field_10 |
| `FB7D71BB` | [List]&lt;Float&gt; | field_1C |

### SLdrShopInstance
| Field | Type | Description |
| --- | --- | --- |
| `AE3D1465` | [enum_10069760](#enum_10069760) | field_0 |

### SLdrShopItemCost
| Field | Type | Description |
| --- | --- | --- |
| `69532C37` | [enum_100726a8](#enum_100726a8) | field_0 |
| `48E4AC9B` | Uint32 | field_4 |
| `EE43C4F6` | Uint32 | field_8 |

### SLdrSidescrollPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `C728E92F` | [Property] | field_0 |
| `53883EAA` | [Property] | field_8 |
| `21021144` | [Property] | field_10 |
| `4587B134` | [SLdrSidescrollSwitchBehaviorData](#sldrsidescrollswitchbehaviordata) | field_18 |

### SLdrSidescrollSwitchBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `A68FA0AA` | Float | field_0 |
| `303AF1B7` | Bool | field_4 |
| `177E0871` | Float | field_8 |
| `09FF452B` | Float | field_C |

### SLdrSidescrollerTrackingBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `70CD7014` | [enum_1007c900](#enum_1007c900) | field_0 |
| `0BC97B70` | Bool | field_4 |
| `EC619E4F` | Bool | field_5 |

### SLdrSimpleFont
| Field | Type | Description |
| --- | --- | --- |
| `4B981B72` | [CObjectId] | field_0 |
| `EA236D40` | [List]&lt;[SLdrSimpleFontGlyph](#sldrsimplefontglyph)&gt; | field_10 |

### SLdrSimpleFontGlyph
| Field | Type | Description |
| --- | --- | --- |
| `9AE7C4FD` | Uint32 | field_0 |
| `9E09095C` | Uint32 | field_4 |
| `5CEF1CA5` | Uint32 | field_8 |
| `9ED234FB` | Uint32 | field_C |
| `ED4ED4D4` | Uint32 | field_10 |
| `67E91E2B` | Uint32 | field_14 |
| `D264B5FF` | Uint32 | field_18 |
| `381840AE` | Uint32 | field_1C |
| `C77B8F17` | Uint32 | field_20 |
| `7F71F7E6` | Bool | field_24 |
| `EA757263` | Bool | field_25 |
| `27E4B27D` | Bool | field_26 |
| `68E1BF34` | Bool | field_27 |

### SLdrSimpleMotionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `A3625DBD` | [SLdrConvergence](#sldrconvergence) | field_0 |
| `D5D1527B` | Bool | field_1C |
| `AE2B6BD0` | [SLdrConvergence](#sldrconvergence) | field_20 |
| `AB048300` | [SLdrConvergence](#sldrconvergence) | field_3C |
| `8C8F86DF` | Float | field_58 |
| `0AFD411D` | Float | field_5C |
| `91B10398` | Float | field_60 |

### SLdrSimpleShadow
| Field | Type | Description |
| --- | --- | --- |
| `9684F4B8` | Bool | field_0 |
| `6AA40102` | Bool | field_1 |
| `8B95978E` | Bool | field_2 |
| `67DFF0B3` | [CObjectId] | field_4 |
| `E1811B8E` | [String] | field_14 |
| `C673B016` | [SLdrLightDistanceAttenuation](#sldrlightdistanceattenuation) | field_20 |
| `BB4200A9` | [SLdrLightDistanceAttenuation](#sldrlightdistanceattenuation) | field_2C |
| `58892B35` | Float | field_38 |
| `017940E8` | Float | field_3C |
| `C02C6C18` | Float | field_40 |
| `EEBB5E9B` | Float | field_44 |
| `DA756041` | Float | field_48 |
| `C9444A0F` | Float | field_4C |
| `A97D28EA` | Float | field_50 |
| `AA1FBAAE` | Float | field_54 |
| `4A31B0D9` | Float | field_58 |
| `E2D25248` | Uint32 | field_5C |
| `E950006D` | Float | field_60 |

### SLdrSimpleSound
| Field | Type | Description |
| --- | --- | --- |
| `AA1F804C` | [SLdrTunableSoundData](#sldrtunablesounddata) | field_0 |

### SLdrSkinSwap
| Field | Type | Description |
| --- | --- | --- |
| `722BE25B` | String | field_0 |

### SLdrSound
| Field | Type | Description |
| --- | --- | --- |
| `D7B241B2` | [CObjectId] | field_0 |
| `5DC7081F` | Float | field_10 |
| `2E87D6B5` | Float | field_14 |
| `0B9AD3F2` | Float | field_18 |
| `43095078` | Float | field_1C |
| `23B7522B` | Float | field_20 |
| `0A53BEA7` | Float | field_24 |
| `AD74FFFA` | Float | field_28 |
| `163F8E09` | Float | field_2C |
| `B2B2A775` | Float | field_30 |
| `C4D943B4` | Bool | field_34 |
| `0D0C5102` | Bool | field_35 |
| `57FA18FB` | Bool | field_36 |
| `36623ED9` | Bool | field_37 |
| `0195EE0B` | Bool | field_38 |
| `ABE04FCF` | Bool | field_39 |
| `97A8C9A0` | Bool | field_3A |
| `30E11FE0` | Bool | field_3B |
| `31CAE15B` | Bool | field_3C |
| `86505DDB` | Float | field_40 |
| `CFB4AF60` | Float | field_44 |
| `16FC82FA` | Float | field_48 |
| `CDD286CB` | Float | field_4C |
| `B9A442DB` | Float | field_50 |
| `6D965207` | Float | field_54 |
| `1DE4FDF8` | [CVector3f] | field_58 |
| `1BACE1B0` | Bool | field_64 |
| `E8D9A871` | Bool | field_65 |

### SLdrSpawnOverride
| Field | Type | Description |
| --- | --- | --- |
| `15B0C853` | Bool | field_0 |
| `F65FDA22` | Bool | field_1 |
| `2787E2D9` | Float | field_4 |
| `5538D27F` | Float | field_8 |
| `A3660994` | [enum_1006dbd0](#enum_1006dbd0) | field_C |
| `96E53D4C` | Bool | field_10 |
| `9CD60DA5` | Bool | field_11 |
| `7B2C3B21` | Float | field_14 |
| `E2F60E33` | Float | field_18 |
| `D5814E74` | Bool | field_1C |
| `40977674` | Float | field_20 |
| `C730B3DF` | Float | field_24 |
| `870FA6B7` | Float | field_28 |

### SLdrSpawnPoint
| Field | Type | Description |
| --- | --- | --- |
| `003F3AA5` | Bool | field_0 |
| `A4A9E173` | Bool | field_1 |
| `2FF0D3D7` | Bool | field_2 |
| `93F57959` | Bool | field_3 |
| `B3393DC3` | Bool | field_4 |
| `271AD75A` | Bool | field_5 |
| `A7D6A5C5` | Bool | field_6 |
| `910115A9` | Bool | field_7 |
| `B65E23FD` | Bool | field_8 |
| `F18159E2` | Bool | field_9 |
| `946F02BF` | Bool | field_A |

### SLdrSphereShape
| Field | Type | Description |
| --- | --- | --- |
| `3A66CBF2` | Float | field_0 |
| `C6DF0354` | [CVector3f] | field_4 |

### SLdrSphereShapeData
| Field | Type | Description |
| --- | --- | --- |
| `1D62D49D` | [CVector3f] | field_0 |
| `9988156A` | Float | field_C |
| `8BF22D17` | Bool | field_10 |

### SLdrSplineMotion
| Field | Type | Description |
| --- | --- | --- |
| `5E36053E` | Float | field_0 |
| `DEDC25FB` | Float | field_4 |
| `6107788C` | Bool | field_8 |
| `A7DF6480` | Bool | field_9 |
| `C23141A6` | Bool | field_A |
| `E99D9D07` | Bool | field_B |
| `24E071BC` | Bool | field_C |
| `5500056C` | Bool | field_D |
| `84EE70B1` | Bool | field_E |
| `9878D30B` | Bool | field_F |
| `B90B0615` | Bool | field_10 |
| `024C807F` | [Property] | field_14 |
| `ADB0BFA9` | [Property] | field_1C |
| `5FFEF3FC` | [Property] | field_24 |

### SLdrSplineMotionTimeJumpMomentumOverride
| Field | Type | Description |
| --- | --- | --- |
| `96B9B2F7` | [CMayaSpline] | field_0 |

### SLdrSplineTrackerData
| Field | Type | Description |
| --- | --- | --- |
| `1336C96F` | [enum_1007e130](#enum_1007e130) | field_0 |
| `1E0C6428` | [enum_10079b9c](#enum_10079b9c) | field_4 |
| `C77CF8AD` | [enum_10077550](#enum_10077550) | field_8 |
| `5E5AC3D4` | [enum_1007a89c](#enum_1007a89c) | field_C |
| `7ADC5140` | [enum_1007a8ac](#enum_1007a8ac) | field_10 |
| `FE32852D` | Bool | field_14 |
| `9714EEA0` | Bool | field_15 |
| `3CACE8F7` | Float | field_18 |

### SLdrSpringConvergenceData
| Field | Type | Description |
| --- | --- | --- |
| `B8F2FEE8` | Bool | field_0 |
| `9881DB50` | Float | field_4 |
| `7B4DF5DB` | Float | field_8 |
| `DEAEFE7C` | Float | field_C |
| `3E186CD0` | Float | field_10 |
| `05FDBD37` | Float | field_14 |

### SLdrSquawks
| Field | Type | Description |
| --- | --- | --- |
| `A4E5E13B` | [CObjectId] | field_0 |
| `530C5F0E` | Float | field_10 |
| `32B12B82` | Float | field_14 |

### SLdrSquawksProxy
| Field | Type | Description |
| --- | --- | --- |
| `4F0532E0` | Float | field_0 |
| `8D0A6ADF` | Float | field_4 |

### SLdrStackData
| Field | Type | Description |
| --- | --- | --- |
| `80863600` | [List]&lt;Int32&gt; | field_0 |
| `25C24838` | [List]&lt;Int32&gt; | field_C |
| `D07B452F` | String | field_18 |
| `C2F0EF34` | Float | field_24 |
| `880DCB01` | [String] | field_28 |

### SLdrStaticCollision
| Field | Type | Description |
| --- | --- | --- |
| `C6793AF2` | [CObjectId] | field_0 |

### SLdrStreamedMovie
| Field | Type | Description |
| --- | --- | --- |
| `884C3906` | [String] | field_0 |
| `769AFB75` | Float | field_C |
| `89390DF2` | Float | field_10 |
| `D70874AD` | Bool | field_14 |
| `27646A78` | Float | field_18 |
| `334FA053` | Float | field_1C |
| `562665EF` | Bool | field_20 |
| `A4C93CE3` | Bool | field_21 |

### SLdrSummersaultSlamAttackParameters
| Field | Type | Description |
| --- | --- | --- |
| `70BCEADE` | Float | field_0 |
| `84D664D2` | [enum_1009c43c](#enum_1009c43c) | field_4 |

### SLdrSummersaultSlamAttackSequence
| Field | Type | Description |
| --- | --- | --- |
| `7DC48D74` | [List]&lt;[SLdrSummersaultSlamAttackParameters](#sldrsummersaultslamattackparameters)&gt; | field_0 |

### SLdrSuperCombinedAbilityData
| Field | Type | Description |
| --- | --- | --- |
| `BE25D7F8` | [enum_10097070](#enum_10097070) | field_0 |

### SLdrSuperCombinedAbilityEmitter
| Field | Type | Description |
| --- | --- | --- |
| `163A2370` | Float | field_0 |

### SLdrSuperCombinedAbilityResponder
| Field | Type | Description |
| --- | --- | --- |
| `10043FF1` | [Property] | field_0 |

### SLdrSurfaceControl
| Field | Type | Description |
| --- | --- | --- |
| `C90670E4` | [Property] | field_0 |

### SLdrSurfaceFollowerMovementConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `42F4AEEE` | Uint32 | field_0 |
| `456D87E4` | Uint32 | field_4 |

### SLdrSurfaceInputBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `5B095330` | [Property] | field_0 |
| `42FC0EC7` | [CMayaSpline] | field_8 |
| `AC41151C` | [Property] | field_38 |
| `80EE3E38` | [CMayaSpline] | field_40 |

### SLdrSurfacePositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `2DD04E2F` | [SLdrConvergence](#sldrconvergence) | field_0 |
| `F678B67D` | [CMayaSpline] | field_1C |
| `E3921435` | [CMayaSpline] | field_4C |
| `9DBB1BC6` | [CMayaSpline] | field_7C |

### SLdrSwimmer
| Field | Type | Description |
| --- | --- | --- |
| `48B0093B` | Bool | field_0 |
| `116D382A` | Bool | field_1 |

### SLdrSwingRope
| Field | Type | Description |
| --- | --- | --- |
| `789E6168` | Float | field_0 |
| `9E8B8FF6` | Float | field_4 |
| `588AC8D0` | Bool | field_8 |
| `77A7B389` | Bool | field_9 |
| `B41E33A6` | Bool | field_A |
| `E282AC15` | Float | field_C |
| `E77D8E74` | Bool | field_10 |
| `C0A80DC8` | [CMayaSpline] | field_14 |
| `2E8667DC` | Float | field_44 |
| `A348A13A` | Float | field_48 |
| `677850F2` | Bool | field_4C |
| `EA4E572A` | Bool | field_4D |
| `56AB0DCB` | [List]&lt;Int32&gt; | field_50 |
| `AB9D1D72` | Float | field_5C |
| `1BA7DFE0` | Float | field_60 |
| `3CDA8F0D` | Uint32 | field_64 |
| `D5B5CB81` | Float | field_68 |
| `3A03F379` | Float | field_6C |
| `29D6BF3B` | Float | field_70 |
| `5A8EEFB5` | Bool | field_74 |

### SLdrSwitch
| Field | Type | Description |
| --- | --- | --- |
| `FEB45495` | Bool | field_0 |
| `7E217C6F` | Bool | field_1 |

### SLdrTakeDamage
| Field | Type | Description |
| --- | --- | --- |
| `75464B80` | Bool | field_0 |
| `96605CB3` | Float | field_4 |

### SLdrTargetBoundingBoxSizeCameraDataInput
| Field | Type | Description |
| --- | --- | --- |
| `3CB545E3` | Bool | field_0 |
| `75BC1920` | Bool | field_1 |
| `FEAF5364` | Bool | field_2 |

### SLdrTargetOrientationSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `93ED840A` | [enum_1007e8bc](#enum_1007e8bc) | field_0 |
| `B86CA24D` | [CVector3f] | field_4 |
| `D0D8FCC9` | Bool | field_10 |
| `BD2A15A5` | Bool | field_11 |
| `3A5E0515` | Float | field_14 |
| `6C314DFE` | Bool | field_18 |
| `6F205448` | [SLdrConvergence](#sldrconvergence) | field_1C |

### SLdrTargetSelector
| Field | Type | Description |
| --- | --- | --- |
| `B7335A41` | Float | field_0 |
| `F7B17D7F` | Float | field_4 |
| `2CB30418` | Float | field_8 |
| `352F589D` | Float | field_C |
| `28F0DF29` | Bool | field_10 |
| `954205C4` | Float | field_14 |
| `ED03CF36` | Float | field_18 |
| `BF28BBAD` | [SLdrTargetingFilters](#sldrtargetingfilters) | field_1C |
| `6FFF04A2` | Bool | field_1F |

### SLdrTargetSelectorLinked
| Field | Type | Description |
| --- | --- | --- |
| `D5510F90` | Float | field_0 |

### SLdrTargetSelectorOffScreen
| Field | Type | Description |
| --- | --- | --- |
| `E8FB1CA5` | Float | field_0 |
| `061F1E2E` | Bool | field_4 |
| `F3D9F833` | Float | field_8 |

### SLdrTargetSelectorRaycast
| Field | Type | Description |
| --- | --- | --- |
| `29B565A4` | [CVector3f] | field_0 |
| `1F8B7B9A` | Float | field_C |
| `8833E91E` | [CVector3f] | field_10 |
| `C8F81452` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_1C |
| `1B28C161` | [SLdrCollisionFilters](#sldrcollisionfilters) | field_29 |
| `901AA321` | Bool | field_36 |

### SLdrTargetedWanderSplineLengthTargeting
| Field | Type | Description |
| --- | --- | --- |
| `BB813ED6` | Float | field_0 |
| `AFCD1695` | Float | field_4 |

### SLdrTargetedWanderTargetSelectorTargeting
This struct does not have any fields

### SLdrTargetingData
| Field | Type | Description |
| --- | --- | --- |
| `FB23D3A7` | Float | field_0 |
| `9D10B215` | Float | field_4 |
| `8119AB3E` | Bool | field_8 |
| `2FC94252` | [Property] | field_C |

### SLdrTargetingFilters
| Field | Type | Description |
| --- | --- | --- |
| `B45FEDBA` | Bool | field_0 |
| `8196E839` | Bool | field_1 |
| `FAEEE581` | Bool | field_2 |

### SLdrTerrainAlignment
| Field | Type | Description |
| --- | --- | --- |
| `5E3E4EE0` | Float | field_0 |
| `D324C1A8` | Float | field_4 |
| `E7941E35` | Float | field_8 |
| `25868F84` | Float | field_C |
| `27C8A3CC` | Float | field_10 |
| `C9326E95` | Bool | field_14 |

### SLdrTerrainAlignmentData
| Field | Type | Description |
| --- | --- | --- |
| `32BFDBD3` | Bool | field_0 |
| `E8B2FC62` | Bool | field_1 |
| `B47944E7` | Float | field_4 |
| `59AD0706` | Float | field_8 |
| `7409CE5E` | Float | field_C |
| `DE1E3955` | Float | field_10 |
| `9B4ADCC7` | Float | field_14 |
| `7270324A` | Float | field_18 |
| `DA546AA4` | [enum_1007a998](#enum_1007a998) | field_1C |

### SLdrThrownLandingConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `6269127F` | [enum_1007e0f8](#enum_1007e0f8) | field_0 |
| `B876025C` | Bool | field_4 |

### SLdrTimeKeyframe
| Field | Type | Description |
| --- | --- | --- |
| `68928B8B` | Float | field_0 |

### SLdrTimer
| Field | Type | Description |
| --- | --- | --- |
| `651D6DFD` | Float | field_0 |
| `800E060E` | Float | field_4 |
| `72C7F9F4` | Bool | field_8 |
| `3459BF46` | Bool | field_9 |

### SLdrTimerAnimationGridParamProvider
This struct does not have any fields

### SLdrTimerSequence
| Field | Type | Description |
| --- | --- | --- |
| `A835FD69` | [CTimelineData] | field_0 |
| `C1B65ED5` | Float | field_C |
| `AF069EF4` | Float | field_10 |
| `9C5CE296` | Float | field_14 |
| `84B0B3FB` | Bool | field_18 |
| `61E5ABE2` | Bool | field_19 |
| `07A19707` | Bool | field_1A |

### SLdrTippy
| Field | Type | Description |
| --- | --- | --- |
| `69277E45` | Uint32 | field_0 |
| `523AFADF` | Uint32 | field_4 |
| `39C657FA` | Uint32 | field_8 |
| `3857484E` | Float | field_C |
| `C10C6303` | Float | field_10 |
| `56FD0874` | Float | field_14 |
| `F47D0542` | Float | field_18 |
| `4A594E9C` | Float | field_1C |
| `79FA408D` | Float | field_20 |
| `C32E64C7` | Float | field_24 |
| `CBDCF987` | [CMayaSpline] | field_28 |
| `397ECF2B` | Float | field_58 |
| `8951F6C0` | [CMayaSpline] | field_5C |
| `6C431204` | [CObjectId] | field_8C |
| `DDA27363` | [CObjectId] | field_9C |
| `1E36A06D` | [CObjectId] | field_AC |
| `131C967A` | Float | field_BC |
| `A0DB62E0` | [CMayaSpline] | field_C0 |
| `7F7D75C3` | [CMayaSpline] | field_F0 |
| `352EEF1E` | [CMayaSpline] | field_120 |
| `41980435` | [CMayaSpline] | field_150 |
| `1FFEF09E` | [CMayaSpline] | field_180 |

### SLdrTireBounce
| Field | Type | Description |
| --- | --- | --- |
| `8DB763DF` | Bool | field_0 |
| `37A250DF` | [SLdrBounceeData](#sldrbounceedata) | field_4 |

### SLdrTouchSet
| Field | Type | Description |
| --- | --- | --- |
| `7CEBD34B` | Bool | field_0 |
| `DB795928` | Bool | field_1 |
| `DA70D67F` | Bool | field_2 |

### SLdrTouchableTrigger
| Field | Type | Description |
| --- | --- | --- |
| `B3DF0D94` | [List]&lt;[Property]&gt; | field_0 |

### SLdrToucher
| Field | Type | Description |
| --- | --- | --- |
| `437BC1BF` | Bool | field_0 |
| `C7463BD8` | Bool | field_1 |
| `8E6452AD` | Bool | field_2 |
| `D24C2C1F` | Bool | field_3 |
| `BAED31C5` | Bool | field_4 |
| `A157523F` | Bool | field_5 |
| `01E31C3A` | Bool | field_6 |
| `0BB9F564` | Bool | field_7 |
| `730677B3` | Bool | field_8 |

### SLdrTraceObject
This struct does not have any fields

### SLdrTransform
| Field | Type | Description |
| --- | --- | --- |
| `EB08B8D9` | [CVector3f] | field_0 |
| `F34C7E99` | [CVector3f] | field_C |
| `080BE1C6` | [CVector3f] | field_18 |

### SLdrTransformCameraHintBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `27BC3778` | Bool | field_0 |
| `0E75F616` | Bool | field_1 |

### SLdrTriggerDetectionModifiers
| Field | Type | Description |
| --- | --- | --- |
| `0FF6D177` | Bool | field_0 |
| `38F63E1C` | Bool | field_1 |
| `C4866ADA` | Bool | field_2 |
| `0B9BFBA8` | Bool | field_3 |
| `46739B9B` | Bool | field_4 |
| `7E8E8CA0` | Bool | field_5 |
| `594CAD85` | Bool | field_6 |
| `CDC597D7` | Bool | field_7 |
| `CCD32C6D` | Bool | field_8 |
| `E26CEDE8` | Bool | field_9 |
| `4E44CE5A` | Bool | field_A |
| `644B3B67` | Bool | field_B |
| `708D98D7` | Bool | field_C |
| `8D2E8582` | Bool | field_D |
| `031A5E95` | Bool | field_E |
| `A8A9B1E4` | Bool | field_F |
| `D1B6468B` | Bool | field_10 |
| `FD517441` | Bool | field_11 |
| `44BEA0F1` | Bool | field_12 |
| `DD2A6CC7` | Bool | field_13 |
| `A3986961` | Bool | field_14 |
| `57F6ABCE` | Bool | field_15 |
| `52B8A8F1` | Bool | field_16 |

### SLdrTriggerDetectionObjectTypes
| Field | Type | Description |
| --- | --- | --- |
| `D3C335E2` | Bool | field_0 |
| `2201B0D4` | Bool | field_1 |
| `8B2F7C8F` | Bool | field_2 |
| `46AC2521` | Bool | field_3 |
| `32FD1EE2` | Bool | field_4 |
| `FF073C50` | Bool | field_5 |
| `9FDD805B` | Bool | field_6 |
| `5EDCB505` | Bool | field_7 |
| `2E64F351` | Bool | field_8 |
| `D272AD06` | Bool | field_9 |
| `6002E199` | Bool | field_A |
| `50B20397` | Bool | field_B |
| `806C702D` | Bool | field_C |

### SLdrTriggerForce
| Field | Type | Description |
| --- | --- | --- |
| `628170E3` | [Property] | field_0 |
| `A689634E` | Float | field_8 |
| `AF3B732D` | Float | field_C |
| `1E3DEDB3` | Float | field_10 |
| `6EBFF5DB` | Float | field_14 |
| `295F593D` | Bool | field_18 |

### SLdrTriggerLogic
| Field | Type | Description |
| --- | --- | --- |
| `0C41E789` | [SLdrTriggerDetectionObjectTypes](#sldrtriggerdetectionobjecttypes) | field_0 |
| `C68EB3B5` | [SLdrTriggerDetectionModifiers](#sldrtriggerdetectionmodifiers) | field_D |
| `D4FB303B` | [SLdrTriggerDetectionModifiers](#sldrtriggerdetectionmodifiers) | field_24 |
| `06A6023B` | [SLdrTriggerMiscOptions](#sldrtriggermiscoptions) | field_3B |

### SLdrTriggerMiscOptions
| Field | Type | Description |
| --- | --- | --- |
| `BD8A224F` | Bool | field_0 |
| `07E569B6` | Bool | field_1 |
| `04360C56` | Bool | field_2 |
| `8C130903` | Bool | field_3 |
| `4B48B759` | Bool | field_4 |
| `251E055B` | Bool | field_5 |
| `54DE0778` | Bool | field_6 |
| `AABB273A` | Bool | field_7 |

### SLdrTunableSoundData
| Field | Type | Description |
| --- | --- | --- |
| `91B94311` | [CObjectId] | field_0 |
| `13D57890` | [CMayaSpline] | field_10 |
| `0D28AC5D` | [CMayaSpline] | field_40 |
| `0B06D9D8` | [CMayaSpline] | field_70 |

### SLdrUICameraSelector
| Field | Type | Description |
| --- | --- | --- |
| `EE54067C` | [String] | field_0 |

### SLdrUVTransform
| Field | Type | Description |
| --- | --- | --- |
| `C809C7E7` | Bool | field_0 |
| `E5F35534` | Bool | field_1 |
| `1824CC0D` | Bool | field_2 |
| `BDF21432` | Bool | field_3 |
| `F2CF9ED7` | [CMayaSpline] | field_4 |

### SLdrVelocityConvergenceData
| Field | Type | Description |
| --- | --- | --- |
| `6F50CD2F` | Float | field_0 |
| `CBF76CB1` | Float | field_4 |
| `74756515` | Float | field_8 |
| `D2255C78` | Float | field_C |

### SLdrVerticalLeadPositionBehaviorData
| Field | Type | Description |
| --- | --- | --- |
| `F63258ED` | [CMayaSpline] | field_0 |
| `3D1CE411` | Bool | field_30 |
| `F6ACB621` | Bool | field_31 |
| `3F3A857B` | Bool | field_32 |
| `9FD2CD1C` | Bool | field_33 |
| `284033E7` | Float | field_34 |
| `1AE52C3E` | Float | field_38 |

### SLdrWarusKing
| Field | Type | Description |
| --- | --- | --- |
| `7AE6F3A7` | [List]&lt;[Property]&gt; | field_0 |

### SLdrWarusKingActionPhase
| Field | Type | Description |
| --- | --- | --- |
| `494BDA1A` | Float | field_0 |
| `11DC3A2D` | [List]&lt;[Property]&gt; | field_4 |
| `7FB5C8AD` | [Property] | field_10 |

### SLdrWarusKingAvalanche
| Field | Type | Description |
| --- | --- | --- |
| `0C4CD0AB` | Uint32 | field_0 |
| `D6DC19FF` | Uint32 | field_4 |
| `54DDE275` | [enum_10075d28](#enum_10075d28) | field_8 |

### SLdrWarusKingBlockTriggerEventData
| Field | Type | Description |
| --- | --- | --- |
| `48BE9B73` | [enum_10093c7c](#enum_10093c7c) | field_0 |
| `FE656070` | Float | field_4 |
| `EE09CF3A` | Float | field_8 |

### SLdrWarusKingBullCharge
| Field | Type | Description |
| --- | --- | --- |
| `59D312F5` | Uint32 | field_0 |
| `80C384F6` | Uint32 | field_4 |
| `81B9B99E` | Float | field_8 |
| `223B2B00` | [enum_10075d28](#enum_10075d28) | field_C |
| `3D37343D` | [enum_10075eb8](#enum_10075eb8) | field_10 |
| `28E2D34F` | Uint32 | field_14 |
| `EA484A74` | Float | field_18 |

### SLdrWarusKingControllerData
| Field | Type | Description |
| --- | --- | --- |
| `48A88496` | [String] | field_0 |
| `8593241C` | [String] | field_C |
| `5F5D406C` | Float | field_18 |
| `6BB0A18A` | Uint32 | field_1C |
| `D31F6CF2` | Float | field_20 |
| `37022809` | Float | field_24 |
| `D0233EE1` | Float | field_28 |
| `625D4CA5` | Float | field_2C |
| `D5C0F8CB` | String | field_30 |
| `CF37FFFA` | [List]&lt;[SLdrWarusKingActionPhase](#sldrwaruskingactionphase)&gt; | field_3C |

### SLdrWarusKingIceStorm
| Field | Type | Description |
| --- | --- | --- |
| `5BED34F8` | Uint32 | field_0 |
| `B534B7CD` | Uint32 | field_4 |
| `2EF0E3F2` | [enum_10075d28](#enum_10075d28) | field_8 |
| `975176CE` | [SLdrWarusKingSupportEventSet](#sldrwaruskingsupporteventset) | field_C |

### SLdrWarusKingIcyBlast
| Field | Type | Description |
| --- | --- | --- |
| `58A97186` | Uint32 | field_0 |
| `A0A0C2B1` | Uint32 | field_4 |
| `7CBF015B` | [enum_10075d28](#enum_10075d28) | field_8 |
| `F1F1A232` | Uint32 | field_C |
| `2F7AAC82` | [enum_100761b0](#enum_100761b0) | field_10 |
| `500AD23A` | [SLdrWarusKingIcyBlastProjectileSequenceData](#sldrwaruskingicyblastprojectilesequencedata) | field_14 |
| `DB8E0AB7` | [SLdrWarusKingIcyBlastProjectileSequenceData](#sldrwaruskingicyblastprojectilesequencedata) | field_20 |

### SLdrWarusKingIcyBlastProjectileSequenceData
| Field | Type | Description |
| --- | --- | --- |
| `08F62C77` | [List]&lt;[Property]&gt; | field_0 |

### SLdrWarusKingMegaQuake
| Field | Type | Description |
| --- | --- | --- |
| `9C7DA691` | Uint32 | field_0 |
| `3D2EB87B` | Uint32 | field_4 |
| `2365184B` | [enum_10075d28](#enum_10075d28) | field_8 |
| `CF44AEE5` | [enum_10076330](#enum_10076330) | field_C |
| `0397BF2C` | Bool | field_10 |
| `8511693F` | [List]&lt;[SLdrWarusKingMegaQuakeBlockTriggerEventData](#sldrwaruskingmegaquakeblocktriggereventdata)&gt; | field_14 |
| `80F517C5` | [SLdrWarusKingBlockTriggerEventData](#sldrwaruskingblocktriggereventdata) | field_20 |
| `5695588E` | [List]&lt;Float&gt; | field_2C |

### SLdrWarusKingMegaQuakeBlockTriggerEventData
| Field | Type | Description |
| --- | --- | --- |
| `EF150125` | NWarusKing::EMegaQuakeBlockTriggerEvent | field_0 |

### SLdrWarusKingRageStomp
| Field | Type | Description |
| --- | --- | --- |
| `275BB07F` | Uint32 | field_0 |
| `6FAA40F7` | Uint32 | field_4 |
| `2183BF8A` | Uint32 | field_8 |
| `1E7FA1BD` | Float | field_C |
| `1E60B920` | [enum_10075d28](#enum_10075d28) | field_10 |
| `4E567B1C` | [SLdrWarusKingStompPositionSet](#sldrwaruskingstomppositionset) | field_14 |

### SLdrWarusKingRoyalRumble
| Field | Type | Description |
| --- | --- | --- |
| `CC45EC2F` | Uint32 | field_0 |
| `1597ECD9` | Uint32 | field_4 |
| `B72B541F` | [enum_10075d28](#enum_10075d28) | field_8 |
| `3130A204` | [SLdrWarusKingBlockTriggerEventData](#sldrwaruskingblocktriggereventdata) | field_C |

### SLdrWarusKingRoyalStomp
| Field | Type | Description |
| --- | --- | --- |
| `2538852B` | Uint32 | field_0 |
| `ED3D2E6A` | Uint32 | field_4 |
| `D3D6F75E` | Uint32 | field_8 |
| `ED3D03E3` | Float | field_C |
| `AD300FD1` | [enum_10075d28](#enum_10075d28) | field_10 |
| `11BB9E37` | [SLdrWarusKingBlockTriggerEventData](#sldrwaruskingblocktriggereventdata) | field_14 |

### SLdrWarusKingSiegeHorn
| Field | Type | Description |
| --- | --- | --- |
| `C680F66E` | Uint32 | field_0 |
| `FC2217F9` | Float | field_4 |
| `793EFEC7` | Float | field_8 |
| `D59141D3` | Float | field_C |
| `3BAA0B40` | Uint32 | field_10 |
| `AEE481F4` | Float | field_14 |
| `531ADBEB` | [enum_10075d28](#enum_10075d28) | field_18 |
| `F92C1FBA` | Bool | field_1C |
| `36799125` | [SLdrWarusKingSupportEventSet](#sldrwaruskingsupporteventset) | field_20 |

### SLdrWarusKingStompPosition
| Field | Type | Description |
| --- | --- | --- |
| `DF204396` | [List]&lt;Int32&gt; | field_0 |

### SLdrWarusKingStompPositionSet
| Field | Type | Description |
| --- | --- | --- |
| `12C1F170` | [List]&lt;[SLdrWarusKingStompPosition](#sldrwaruskingstompposition)&gt; | field_0 |

### SLdrWarusKingSupportEvent
| Field | Type | Description |
| --- | --- | --- |
| `D2ED546B` | Uint32 | field_0 |
| `879CDF3D` | Uint32 | field_4 |
| `132E0349` | Float | field_8 |
| `3DA3A8CA` | Float | field_C |

### SLdrWarusKingSupportEventData
| Field | Type | Description |
| --- | --- | --- |
| `583800E1` | Float | field_0 |
| `E44C9B91` | [List]&lt;[SLdrWarusKingSupportEvent](#sldrwaruskingsupportevent)&gt; | field_4 |

### SLdrWarusKingSupportEventSet
| Field | Type | Description |
| --- | --- | --- |
| `A7A9BF19` | [SLdrWarusKingSupportEventSetData](#sldrwaruskingsupporteventsetdata) | field_0 |
| `5C5E19B8` | [List]&lt;[SLdrWarusKingSupportEventSetData](#sldrwaruskingsupporteventsetdata)&gt; | field_10 |
| `0EBB7F47` | Float | field_1C |
| `61CBE78F` | Float | field_20 |
| `4248D791` | Bool | field_24 |

### SLdrWarusKingSupportEventSetData
| Field | Type | Description |
| --- | --- | --- |
| `1634C1D2` | [enum_10076330](#enum_10076330) | field_0 |
| `0A892512` | [List]&lt;[SLdrWarusKingSupportEventData](#sldrwaruskingsupporteventdata)&gt; | field_4 |

### SLdrWarusKingSupportObjectMovementConfiguration
| Field | Type | Description |
| --- | --- | --- |
| `8B8E8CEB` | Float | field_0 |
| `F15AF695` | [enum_1007e0f8](#enum_1007e0f8) | field_4 |

### SLdrWaterCurrentVolume
| Field | Type | Description |
| --- | --- | --- |
| `6251B7B1` | Float | field_0 |
| `88BD204A` | Float | field_4 |
| `27BE849A` | [enum_1001693c](#enum_1001693c) | field_8 |
| `18410943` | [CVector3f] | field_C |
| `38D7A07F` | Float | field_18 |
| `5E2DE3D6` | Float | field_1C |
| `B57D7678` | Float | field_20 |
| `A39E2D21` | Float | field_24 |
| `CBE00DD9` | Float | field_28 |
| `07CE4F8A` | Float | field_2C |
| `CFE840DA` | Float | field_30 |
| `4EEB92CE` | Float | field_34 |
| `9698CE8A` | Bool | field_38 |
| `CD09DFCF` | Float | field_3C |
| `0275B820` | Float | field_40 |
| `F105C65E` | [CVector3f] | field_44 |
| `B1BD1BFB` | Bool | field_50 |
| `4802903C` | Bool | field_51 |
| `1F1AC8CE` | [CMayaSpline] | field_54 |
| `7638AE10` | [CMayaSpline] | field_84 |
| `A08F3F85` | [CMayaSpline] | field_B4 |
| `8D11E3D9` | [CMayaSpline] | field_E4 |
| `8B8AB602` | [CMayaSpline] | field_114 |
| `67F60251` | [CMayaSpline] | field_144 |
| `CE68B6BA` | [CMayaSpline] | field_174 |

### SLdrWaterDirection
| Field | Type | Description |
| --- | --- | --- |
| `B9303984` | Float | field_0 |
| `51F42492` | Float | field_4 |

### SLdrWaterFeatureFlags
| Field | Type | Description |
| --- | --- | --- |
| `8B294D2E` | Bool | field_0 |
| `68999D0E` | Bool | field_1 |
| `D7F0419B` | Bool | field_2 |
| `BF2C11DB` | Bool | field_3 |
| `F2D5D4BE` | Bool | field_4 |
| `FCFCE6E6` | Bool | field_5 |
| `1878894A` | Bool | field_6 |

### SLdrWaterFog
| Field | Type | Description |
| --- | --- | --- |
| `6F7355A3` | [CColor4f] | field_0 |
| `3B29E512` | Float | field_10 |

### SLdrWaterFresnel
| Field | Type | Description |
| --- | --- | --- |
| `FAA21CEB` | Float | field_0 |
| `5CDD63CE` | Float | field_4 |

### SLdrWaterMaterialData
| Field | Type | Description |
| --- | --- | --- |
| `E8969FAD` | [CColor4f] | field_0 |
| `E8878EE7` | [CColor4f] | field_10 |
| `50C8AC86` | Float | field_20 |
| `39EBE3DE` | Float | field_24 |
| `03E33F4B` | [SLdrWaterNormalMap](#sldrwaternormalmap) | field_28 |
| `828A7993` | [SLdrWaterNormalMap](#sldrwaternormalmap) | field_48 |
| `094EACF2` | [SLdrWaterReflection](#sldrwaterreflection) | field_68 |
| `C5DDDE70` | [SLdrWaterRefraction](#sldrwaterrefraction) | field_8C |
| `C72FE289` | [SLdrWaterSpecular](#sldrwaterspecular) | field_94 |
| `BC1FC02D` | [SLdrWaterFresnel](#sldrwaterfresnel) | field_A8 |
| `7982E07B` | [SLdrWaterFog](#sldrwaterfog) | field_B0 |
| `81FFE012` | [SLdrWaterSurfaceExternalFog](#sldrwatersurfaceexternalfog) | field_C4 |
| `7AB8E654` | [SLdrWaterUnderwaterFog](#sldrwaterunderwaterfog) | field_E0 |
| `DCEE7D4D` | [SLdrWaterProjectedLightmapData](#sldrwaterprojectedlightmapdata) | field_10C |
| `1A6AAC69` | [SLdrWaterRainDropRippleData](#sldrwaterraindroprippledata) | field_11C |

### SLdrWaterNormalMap
| Field | Type | Description |
| --- | --- | --- |
| `90A143EF` | [CObjectId] | field_0 |
| `522ABD8A` | Float | field_10 |
| `D4483C7E` | Float | field_14 |
| `138DB2F0` | [SLdrWaterDirection](#sldrwaterdirection) | field_18 |

### SLdrWaterProjectedLightmapData
| Field | Type | Description |
| --- | --- | --- |
| `797A7FF1` | [CObjectId] | field_0 |

### SLdrWaterRainDropRippleData
| Field | Type | Description |
| --- | --- | --- |
| `A61E08D3` | [CObjectId] | field_0 |
| `E4732770` | Float | field_10 |
| `5E94C719` | Float | field_14 |
| `E89F4385` | Float | field_18 |
| `C5DAD5EC` | Float | field_1C |
| `BC212B78` | Float | field_20 |
| `7B56B6DD` | Float | field_24 |
| `3BDA1181` | Float | field_28 |
| `6E5A8B34` | Float | field_2C |
| `851D5509` | Float | field_30 |
| `53160E29` | Float | field_34 |

### SLdrWaterReflection
| Field | Type | Description |
| --- | --- | --- |
| `8658ADDC` | [CObjectId] | field_0 |
| `E22EFEE4` | Float | field_10 |
| `36D9C405` | [CColor4f] | field_14 |

### SLdrWaterRefraction
| Field | Type | Description |
| --- | --- | --- |
| `07979D1E` | Bool | field_0 |
| `CEDAA6CA` | Float | field_4 |

### SLdrWaterRenderDecal
| Field | Type | Description |
| --- | --- | --- |
| `F47826C1` | [CObjectId] | field_0 |

### SLdrWaterRenderVolume
| Field | Type | Description |
| --- | --- | --- |
| `736E5890` | [CObjectId] | field_0 |
| `7470B292` | [CObjectId] | field_10 |
| `54F39685` | [SLdrWaterFeatureFlags](#sldrwaterfeatureflags) | field_20 |
| `DA360B79` | [SLdrModelLightingData](#sldrmodellightingdata) | field_28 |
| `30FBB790` | [SLdrWaterWaveParams](#sldrwaterwaveparams) | field_44 |
| `0951BF3E` | [SLdrWaterWaveParams](#sldrwaterwaveparams) | field_58 |
| `D1E9D29D` | [SLdrWaterMaterialData](#sldrwatermaterialdata) | field_6C |

### SLdrWaterSpecular
| Field | Type | Description |
| --- | --- | --- |
| `B67ECFF7` | Float | field_0 |
| `1B025477` | [CColor4f] | field_4 |

### SLdrWaterSurfaceExternalFog
| Field | Type | Description |
| --- | --- | --- |
| `C4FCAE94` | Bool | field_0 |
| `1507EDF8` | [CColor4f] | field_4 |
| `84A499E2` | Float | field_14 |
| `EE0021AD` | Float | field_18 |

### SLdrWaterUnderwaterFog
| Field | Type | Description |
| --- | --- | --- |
| `44CD8AE7` | [CColor4f] | field_0 |
| `4A5AC8CA` | [CColor4f] | field_10 |
| `D13F7741` | Float | field_20 |
| `AE353E31` | Float | field_24 |
| `796308DD` | Float | field_28 |

### SLdrWaterVolume
| Field | Type | Description |
| --- | --- | --- |
| `4ACC0E01` | [SLdrWaterVolumeData](#sldrwatervolumedata) | field_0 |

### SLdrWaterVolumeData
| Field | Type | Description |
| --- | --- | --- |
| `90B492AA` | [enum_10016a60](#enum_10016a60) | field_0 |
| `0261247E` | [enum_10079210](#enum_10079210) | field_4 |

### SLdrWaterWaveParams
| Field | Type | Description |
| --- | --- | --- |
| `D1EDD7B5` | Float | field_0 |
| `ABE1BACD` | Float | field_4 |
| `F6266364` | Float | field_8 |
| `4574DE4F` | Float | field_C |
| `921415EB` | Float | field_10 |

### SLdrWaypoint
| Field | Type | Description |
| --- | --- | --- |
| `F6A98696` | Float | field_0 |

### SLdrWaypointSpeedControl
| Field | Type | Description |
| --- | --- | --- |
| `B6CD1E94` | Float | field_0 |
| `5DC07BE6` | [enum_10082454](#enum_10082454) | field_4 |
| `88EAFFC2` | [enum_100822f8](#enum_100822f8) | field_8 |

### SLdrWeaponData
| Field | Type | Description |
| --- | --- | --- |
| `B36A06F2` | Bool | field_0 |

### SLdrWindWaker
| Field | Type | Description |
| --- | --- | --- |
| `EE53521F` | [CMayaSpline] | field_0 |

### SLdrWindWakerImpulseData
| Field | Type | Description |
| --- | --- | --- |
| `1D9217E7` | Float | field_0 |
| `40B318CB` | [CVector3f] | field_4 |
| `59A2D38E` | [CMayaSpline] | field_10 |
| `02798A3E` | [CMayaSpline] | field_40 |

### SLdrWindWakerImpulser
| Field | Type | Description |
| --- | --- | --- |
| `0550B4A7` | [SLdrWindWakerImpulseData](#sldrwindwakerimpulsedata) | field_0 |

### SLdrWorldType
| Field | Type | Description |
| --- | --- | --- |
| `72BE7F31` | [enum_10013fdc](#enum_10013fdc) | field_0 |

### SLdrXYZPositionSplineControl
| Field | Type | Description |
| --- | --- | --- |
| `1677468F` | [CMayaSpline] | field_0 |
| `C85850CB` | [CMayaSpline] | field_30 |
| `75A2B772` | [CMayaSpline] | field_60 |
| `D8171987` | Bool | field_90 |

### enum_10006c68
| Hash | Value | Description |
| --- | --- | --- |
| `96144B9F` | 1 | Unknown |
| `0A68658A` | 2 | Unknown |
| `83D7EB1C` | 3 | Unknown |
| `EA101B4C` | 4 | Unknown |
| `0E698490` | 5 | Unknown |
| `8097E7C5` | 6 | Unknown |
| `1CFB3A64` | 7 | Unknown |
| `E07CD0DC` | 8 | Unknown |
| `35AC3B64` | 9 | Unknown |
| `B947F1FF` | 10 | Unknown |
| `E9A884B5` | 11 | Unknown |
| `1BBA33BA` | 12 | Unknown |
| `6DFA66B7` | 13 | Unknown |
| `D5601A25` | 14 | Unknown |
| `59A26ACD` | 15 | Unknown |
| `287473B1` | 16 | Unknown |
| `EF96A260` | 17 | Unknown |
| `3949E1D3` | 18 | Unknown |
| `6A12D854` | 19 | Unknown |
| `6BA64410` | 20 | Unknown |
| `C5BBB783` | 21 | Unknown |
| `AFE2BAF0` | 22 | Unknown |
| `43C3F5AB` | 23 | Unknown |
| `1423884C` | 24 | Unknown |
| `57D7D635` | 25 | Unknown |
| `A5F51EEB` | 26 | Unknown |
| `6330345D` | 27 | Unknown |
| `48693C9F` | 28 | Unknown |
| `27FD1786` | 29 | Unknown |
| `1A7DF6F8` | 30 | Unknown |
| `DBA98694` | 31 | Unknown |
| `0E1BEADF` | 32 | Unknown |
| `D43D95F3` | 33 | Unknown |
| `37700366` | 34 | Unknown |
| `7DB9D0DC` | 35 | Unknown |
| `98C71E45` | 36 | Unknown |
| `512204BB` | 37 | Unknown |
| `693DD22A` | 38 | Unknown |
| `96C362C6` | 39 | Unknown |
| `97EA53D7` | 40 | Unknown |
| `B0D29779` | 41 | Unknown |
| `06519FDC` | 42 | Unknown |
| `B32BD143` | 43 | Unknown |
| `3F76CF47` | 44 | Unknown |
| `915D64AF` | 45 | Unknown |
| `DBB9DCCF` | 46 | Unknown |
| `E335BCEC` | 47 | Unknown |
| `907A919F` | 48 | Unknown |
| `AAA336A4` | 49 | Unknown |
| `277EA2CA` | 50 | Unknown |
| `F7E63538` | 51 | Unknown |
| `0A17EEB9` | 52 | Unknown |
| `C1213E4A` | 53 | Unknown |
| `ABC0149B` | 54 | Unknown |
| `F3DF575B` | 55 | Unknown |
| `D45DAF1C` | 56 | Unknown |
| `E89124D6` | 57 | Unknown |
| `F66AA2F7` | 58 | Unknown |
| `D1B184BF` | 59 | Unknown |
| `65BE6B4B` | 60 | Unknown |
| `BE1B80BA` | 61 | Unknown |
| `41D43C82` | 62 | Unknown |
| `7012A176` | 63 | Unknown |
| `75992AB7` | 64 | Unknown |
| `C82087C0` | 65 | Unknown |
| `072AB2DA` | 66 | Unknown |
| `0AB007AF` | 67 | Unknown |
| `CC93AF38` | 68 | Unknown |
| `2FFFC944` | 69 | Unknown |
| `D5BE9262` | 70 | Unknown |
| `E719633A` | 71 | Unknown |
| `A4CD0A14` | 72 | Unknown |
| `F777856E` | 73 | Unknown |
| `BBE5A45A` | 74 | Unknown |
| `7D4E3617` | 75 | Unknown |
| `EAFE78BC` | 76 | Unknown |
| `31E8537E` | 77 | Unknown |
| `5AFFA851` | 78 | Unknown |
| `B6A2096E` | 79 | Unknown |
| `AE0187EB` | 80 | Unknown |
| `797ECF5C` | 81 | Unknown |
| `EE9D27B9` | 82 | Unknown |
| `6580FDEA` | 83 | Unknown |
| `CCE4DE04` | 84 | Unknown |
| `799DF45C` | 85 | Unknown |
| `131B9DDC` | 86 | Unknown |
| `1F05C8A3` | 87 | Unknown |
| `B819607E` | 88 | Unknown |
| `4785ADC7` | 89 | Unknown |
| `1568766C` | 90 | Unknown |
| `BC7636C8` | 91 | Unknown |
| `70A04B76` | 92 | Unknown |
| `D4933FA9` | 93 | Unknown |
| `CB239A3A` | 94 | Unknown |
| `85600198` | 95 | Unknown |
| `8BA6C5E3` | 96 | Unknown |
| `969E9FBA` | 97 | Unknown |
| `C3EE24C0` | 98 | Unknown |
| `993D7B65` | 99 | Unknown |
| `8ADCD748` | 100 | Unknown |
| `13DF7084` | 101 | Unknown |
| `C586F3F4` | 102 | Unknown |
| `BC8D8C76` | 103 | Unknown |
| `DDBFE278` | 104 | Unknown |
| `9E14628C` | 105 | Unknown |
| `77210F80` | 106 | Unknown |
| `27A6238F` | 107 | Unknown |
| `557A6D81` | 108 | Unknown |
| `B7D8FFAB` | 109 | Unknown |
| `AD1B00A6` | 110 | Unknown |
| `7DD4FDD0` | 111 | Unknown |
| `B7F029B3` | 112 | Unknown |
| `C5A03D8A` | 113 | Unknown |
| `4E9C56B1` | 114 | Unknown |
| `61F9ECDB` | 115 | Unknown |
| `AC202156` | 116 | Unknown |
| `A47526A7` | 117 | Unknown |
| `813AFD66` | 118 | Unknown |
| `D9075288` | 119 | Unknown |
| `E95E82A7` | 120 | Unknown |
| `E1CEC635` | 121 | Unknown |
| `A38B9F87` | 122 | Unknown |
| `3F8C2019` | 123 | Unknown |
| `AD88F644` | 124 | Unknown |
| `299CF0B6` | 125 | Unknown |
| `21D836EF` | 126 | Unknown |
| `AD7CD4DB` | 127 | Unknown |
| `390D3E47` | 128 | Unknown |
| `B15102A6` | 129 | Unknown |
| `78670B23` | 130 | Unknown |
| `581C7811` | 131 | Unknown |
| `0DB328B5` | 132 | Unknown |
| `9FC5CF09` | 133 | Unknown |
| `5A15F6FD` | 134 | Unknown |
| `186D08BC` | 135 | Unknown |
| `EB11443E` | 136 | Unknown |
| `CE5DC387` | 137 | Unknown |
| `C3D60E24` | 138 | Unknown |
| `84B623F2` | 139 | Unknown |
| `4D2862FF` | 140 | Unknown |
| `5FAB6C18` | 141 | Unknown |
| `5E9B6E14` | 142 | Unknown |
| `D0B0709F` | 143 | Unknown |
| `4F680B33` | 144 | Unknown |
| `D92738DA` | 145 | Unknown |
| `CB13141B` | 146 | Unknown |
| `639EB70D` | 147 | Unknown |
| `B9505350` | 148 | Unknown |
| `4581CC4E` | 149 | Unknown |
| `2518214A` | 150 | Unknown |
| `49AE7456` | 151 | Unknown |
| `0511C4F5` | 152 | Unknown |
| `24B78BB9` | 153 | Unknown |
| `DBD889D5` | 154 | Unknown |
| `DE630B1C` | 155 | Unknown |
| `0CF0C870` | 156 | Unknown |
| `F128C8E1` | 157 | Unknown |
| `2D0817A4` | 158 | Unknown |
| `87BBBA70` | 159 | Unknown |
| `C0DDE5EC` | 160 | Unknown |
| `F647A5D6` | 161 | Unknown |
| `BCC9214E` | 162 | Unknown |
| `FF2256FE` | 163 | Unknown |
| `319499DE` | 164 | Unknown |
| `46E4BB26` | 165 | Unknown |
| `9C41F9AC` | 166 | Unknown |
| `C1EE4818` | 167 | Unknown |
| `4C65500A` | 168 | Unknown |
| `571C5488` | 169 | Unknown |
| `BB1B0639` | 170 | Unknown |
| `EFE003D2` | 171 | Unknown |
| `31E06520` | 172 | Unknown |
| `8E8990C7` | 173 | Unknown |
| `2811FDCD` | 174 | Unknown |

### enum_100071d8
| Hash | Value | Description |
| --- | --- | --- |
| `1AF39F6C` | 0 | Unknown |
| `7EC72C93` | 1 | Unknown |
| `66031027` | 2 | Unknown |
| `EE0BCCC8` | 3 | Unknown |
| `8339A6F6` | 4 | Unknown |
| `1B4EB174` | 5 | Unknown |
| `BE3999E1` | 6 | Unknown |
| `CB8420BF` | 7 | Unknown |

### enum_10007218
| Hash | Value | Description |
| --- | --- | --- |
| `B0F70587` | 0 | Unknown |
| `6EF30417` | 1 | Unknown |
| `B24933A1` | 2 | Unknown |

### enum_100072c0
| Hash | Value | Description |
| --- | --- | --- |
| `65FF4CBB` | 0 | Unknown |
| `3F968D6C` | 1 | Unknown |
| `93CB5BD8` | 2 | Unknown |
| `5E6D2471` | 3 | Unknown |
| `FDAB9446` | 4 | Unknown |
| `B9D97942` | 5 | Unknown |
| `4C9E9D9E` | 6 | Unknown |
| `4B22B37D` | 7 | Unknown |
| `CCFE2BAC` | 8 | Unknown |
| `DA28935F` | 9 | Unknown |
| `AB7EB560` | 10 | Unknown |
| `387B8F4C` | 11 | Unknown |
| `EBBCA6DD` | 12 | Unknown |
| `F749E6D5` | 13 | Unknown |
| `26A9AA51` | 14 | Unknown |
| `1FF0C0FD` | 15 | Unknown |
| `F43C4C6B` | 16 | Unknown |
| `2AA85CF5` | 17 | Unknown |

### enum_10007350
| Hash | Value | Description |
| --- | --- | --- |
| `EA260D49` | 0 | Unknown |
| `06AB1D42` | 1 | Unknown |
| `C4FE40E7` | 2 | Unknown |
| `12900FB8` | 3 | Unknown |
| `F01ED7D9` | 4 | Unknown |
| `5B35295F` | 5 | Unknown |
| `E9C4E252` | 6 | Unknown |
| `78416B8B` | 7 | Unknown |
| `8D885E27` | 8 | Unknown |
| `8DBA2779` | 9 | Unknown |
| `5B8B0326` | 10 | Unknown |
| `5B93F4C5` | 11 | Unknown |

### enum_1001326c
| Hash | Value | Description |
| --- | --- | --- |
| `5D2046AC` | 0 | Unknown |
| `6054358C` | 1 | Unknown |
| `6B4F276C` | 2 | Unknown |
| `974EEF32` | 3 | Unknown |
| `251A35FF` | 4 | Unknown |
| `419AFC5B` | 5 | Unknown |
| `990813BF` | 8 | Unknown |
| `23BE12FD` | 9 | Unknown |
| `5E0780CA` | 10 | Unknown |
| `86890A81` | 11 | Unknown |
| `36B7707B` | 12 | Unknown |
| `D9A6F54C` | 13 | Unknown |
| `60822353` | 14 | Unknown |
| `69726077` | 15 | Unknown |
| `9C9A3061` | 18 | Unknown |
| `8001AE14` | 19 | Unknown |
| `0505A932` | 20 | Unknown |
| `7888C12C` | 21 | Unknown |
| `72E0F6D5` | 22 | Unknown |
| `634F53BA` | 23 | Unknown |
| `AC4F4418` | 24 | Unknown |
| `40DEF85D` | 25 | Unknown |
| `BB09308C` | 27 | Unknown |
| `95A3A329` | 30 | Unknown |
| `7516EFD1` | 34 | Unknown |
| `F55F5365` | 36 | Unknown |
| `23733F0F` | 37 | Unknown |

### enum_10013ca8
| Hash | Value | Description |
| --- | --- | --- |
| `E09C0195` | 0 | Unknown |
| `D973171F` | 1 | Unknown |
| `03E72597` | 2 | Unknown |
| `FB4E754B` | 3 | Unknown |
| `D93A64DC` | 4 | Unknown |
| `7225752B` | 5 | Unknown |
| `687148A6` | 6 | Unknown |
| `2C9080FD` | 7 | Unknown |
| `9C52A0BA` | 8 | Unknown |
| `248D1E4A` | 9 | Unknown |
| `8D5C15F3` | 10 | Unknown |
| `3270EC97` | 11 | Unknown |
| `AF6BFCFE` | 12 | Unknown |
| `AE618522` | 13 | Unknown |
| `A6EAD18A` | 14 | Unknown |
| `81E9BEBC` | 15 | Unknown |
| `62F25C09` | 16 | Unknown |
| `CEB93A6C` | 17 | Unknown |
| `6F7B27CB` | 18 | Unknown |
| `36AA5D67` | 19 | Unknown |
| `82DB950F` | 20 | Unknown |
| `966FCB08` | 21 | Unknown |
| `5B9B3793` | 22 | Unknown |
| `F5609932` | 23 | Unknown |
| `F16E792B` | 24 | Unknown |
| `0B838236` | 25 | Unknown |
| `5B5748C2` | 26 | Unknown |
| `33E03A1B` | 27 | Unknown |
| `35F0F1A1` | 28 | Unknown |
| `30E8645B` | 29 | Unknown |
| `14CF0AF4` | 30 | Unknown |
| `2D4039ED` | 31 | Unknown |
| `BEF2A82C` | 32 | Unknown |
| `D6B3AA7E` | 33 | Unknown |
| `FFCB0218` | 34 | Unknown |
| `A203B262` | 35 | Unknown |
| `C2353382` | 36 | Unknown |
| `E703BD3E` | 37 | Unknown |
| `C6916C55` | 38 | Unknown |
| `4F16E4E3` | 39 | Unknown |
| `1B07EBD8` | 40 | Unknown |
| `907AEFE7` | 41 | Unknown |
| `424ADE1F` | 42 | Unknown |
| `AC76C45C` | 43 | Unknown |
| `D3AB3588` | 44 | Unknown |
| `587C78F9` | 45 | Unknown |
| `15EE895B` | 46 | Unknown |
| `60FF7ABB` | 47 | Unknown |
| `E6D32B24` | 48 | Unknown |
| `1FE31ED4` | 49 | Unknown |
| `8A9A1D6A` | 50 | Unknown |
| `AF330339` | 51 | Unknown |
| `99B180F6` | 52 | Unknown |
| `A324E87C` | 53 | Unknown |
| `8FA751E1` | 54 | Unknown |
| `7267F3FA` | 55 | Unknown |
| `4D2A14BF` | 56 | Unknown |
| `B2D82135` | 57 | Unknown |
| `353BC44B` | 58 | Unknown |
| `3474DD22` | 59 | Unknown |
| `32B48B40` | 60 | Unknown |
| `20F7A713` | 61 | Unknown |
| `7FA1EB70` | 62 | Unknown |
| `B57C325B` | 63 | Unknown |
| `66656B5A` | 64 | Unknown |
| `9079710C` | 65 | Unknown |
| `8924C6B2` | 66 | Unknown |
| `BA4F0750` | 67 | Unknown |
| `421BAD47` | 68 | Unknown |
| `773CEF36` | 69 | Unknown |
| `DA2E185C` | 70 | Unknown |
| `723573AD` | 71 | Unknown |
| `730B1E58` | 72 | Unknown |
| `E86D2550` | 73 | Unknown |
| `F83746C2` | 74 | Unknown |
| `08ADDE42` | 76 | Unknown |
| `205B4E1C` | 77 | Unknown |
| `BB4EEF81` | 78 | Unknown |
| `D3B8BDE0` | 79 | Unknown |
| `05E728F0` | 80 | Unknown |

### enum_10013fdc
| Hash | Value | Description |
| --- | --- | --- |
| `DBABA8AC` | 0 | Unknown |
| `86664350` | 1 | Unknown |
| `9BE4BC7C` | 2 | Unknown |
| `79925C31` | 3 | Unknown |
| `A73BD7A1` | 4 | Unknown |
| `54F94247` | 5 | Unknown |
| `174626DA` | 6 | Unknown |
| `8725406E` | 7 | Unknown |

### enum_10014400
| Hash | Value | Description |
| --- | --- | --- |
| `F6EB5B38` | 0 | Unknown |
| `187C1E7D` | 1 | Unknown |
| `F3648460` | 2 | Unknown |
| `09A577B8` | 3 | Unknown |
| `4ACE145C` | 4 | Unknown |
| `CCC7A0E4` | 5 | Unknown |
| `0C5FFF93` | 6 | Unknown |
| `B20C73AD` | 7 | Unknown |

### enum_10014440
| Hash | Value | Description |
| --- | --- | --- |
| `E532C618` | 0 | Unknown |
| `32794361` | 1 | Unknown |
| `F4C9F667` | 2 | Unknown |
| `A0DCA485` | 3 | Unknown |

### enum_10014460
| Hash | Value | Description |
| --- | --- | --- |
| `3E6DF0B3` | 0 | Unknown |
| `53F37B97` | 1 | Unknown |
| `E049E25F` | 2 | Unknown |
| `32F3AF4E` | 3 | Unknown |

### enum_10014b3c
| Hash | Value | Description |
| --- | --- | --- |
| `7F4B92AF` | 0 | Unknown |
| `5EC5A89E` | 1 | Unknown |
| `568FD69C` | 2 | Unknown |

### enum_10014c94
| Hash | Value | Description |
| --- | --- | --- |
| `111C2649` | 0 | Unknown |
| `5025E87F` | 1 | Unknown |

### enum_1001693c
| Hash | Value | Description |
| --- | --- | --- |
| `E44BF297` | 0 | Unknown |
| `C0D3B253` | 1 | Unknown |
| `19D04E37` | 2 | Unknown |
| `5F3985D5` | 3 | Unknown |

### enum_10016a60
| Hash | Value | Description |
| --- | --- | --- |
| `B3DEBE02` | 0 | Unknown |
| `1DBD942A` | 1 | Unknown |
| `03BD5C49` | 2 | Unknown |
| `4822581D` | 3 | Unknown |

### enum_10017488
| Hash | Value | Description |
| --- | --- | --- |
| `6E226A07` | 0 | Unknown |
| `31189396` | 1 | Unknown |
| `0861A731` | 2 | Unknown |

### enum_100179c4
| Hash | Value | Description |
| --- | --- | --- |
| `1D5F7C20` | 0 | Unknown |
| `266701CD` | 1 | Unknown |
| `CFFA68C3` | 2 | Unknown |

### enum_1001a854
| Hash | Value | Description |
| --- | --- | --- |
| `F09AB5FF` | 0 | Unknown |

### enum_1001a85c
| Hash | Value | Description |
| --- | --- | --- |
| `EBEBAAB3` | 0 | Unknown |

### enum_1001a864
| Hash | Value | Description |
| --- | --- | --- |
| `78FB3426` | 0 | Unknown |
| `F0F5EE72` | 1 | Unknown |
| `1C43BC13` | 2 | Unknown |

### enum_1001a87c
| Hash | Value | Description |
| --- | --- | --- |
| `09B414A1` | 0 | Unknown |
| `526983FB` | 1 | Unknown |
| `D0299CBD` | 2 | Unknown |
| `CA0A67F4` | 3 | Unknown |
| `B77C32C7` | 4 | Unknown |

### enum_1005afd8
| Hash | Value | Description |
| --- | --- | --- |
| `44EEA562` | 0 | Unknown |
| `3F1CB4CB` | 1 | Unknown |
| `9D6C3C22` | 2 | Unknown |
| `3224E9C7` | 3 | Unknown |
| `335F4821` | 4 | Unknown |
| `FA17B0FD` | 5 | Unknown |
| `CB976B4D` | 6 | Unknown |
| `27E19660` | 7 | Unknown |

### enum_1005b020
| Hash | Value | Description |
| --- | --- | --- |
| `B816E016` | 0 | Unknown |
| `783BA972` | 1 | Unknown |
| `8E6F734E` | 2 | Unknown |
| `28FEC4F7` | 3 | Unknown |
| `BCE27411` | 4 | Unknown |
| `DEAE9143` | 5 | Unknown |
| `B33ED595` | 6 | Unknown |
| `E3C7E92A` | 7 | Unknown |

### enum_1005b060
| Hash | Value | Description |
| --- | --- | --- |
| `B7EC7A51` | 0 | Unknown |
| `28745CD7` | 1 | Unknown |
| `B13635D6` | 2 | Unknown |
| `D963888D` | 3 | Unknown |
| `69EEA715` | 4 | Unknown |

### enum_1005b088
| Hash | Value | Description |
| --- | --- | --- |
| `41BF7E01` | 0 | Unknown |
| `C0E263F0` | 1 | Unknown |
| `83F66B25` | 2 | Unknown |
| `87CB16CF` | 3 | Unknown |
| `7BB11962` | 4 | Unknown |
| `9C0CB480` | 5 | Unknown |
| `3DA5FDCF` | 6 | Unknown |

### enum_1005b0c0
| Hash | Value | Description |
| --- | --- | --- |
| `87576FBB` | 0 | Unknown |
| `1312D199` | 1 | Unknown |
| `B302083E` | 2 | Unknown |

### enum_1005bae8
| Hash | Value | Description |
| --- | --- | --- |
| `EA694F28` | 0 | Unknown |
| `57B87986` | 1 | Unknown |

### enum_100625f8
| Hash | Value | Description |
| --- | --- | --- |
| `882E9F41` | 49 | Unknown |
| `BCD38DD8` | 50 | Unknown |
| `23D5EF0F` | 51 | Unknown |
| `1EA8194D` | 52 | Unknown |
| `2463A949` | 53 | Unknown |
| `039E82F2` | 54 | Unknown |
| `E7CA951B` | 55 | Unknown |
| `F3958897` | 56 | Unknown |
| `0B041705` | 57 | Unknown |
| `AD7341E9` | 58 | Unknown |
| `5FFB0052` | 59 | Unknown |
| `49AAEBE0` | 60 | Unknown |
| `015E0619` | 61 | Unknown |
| `92717486` | 62 | Unknown |
| `30A51DD8` | 63 | Unknown |
| `08757856` | 64 | Unknown |
| `44CDFC72` | 65 | Unknown |
| `91FB22A4` | 66 | Unknown |
| `D3EF578A` | 67 | Unknown |
| `9C112A8E` | 68 | Unknown |

### enum_10062788
| Hash | Value | Description |
| --- | --- | --- |
| `28521DE8` | 0 | Unknown |
| `877BCAD6` | 1 | Unknown |
| `A75BFF8F` | 2 | Unknown |
| `8E171442` | 3 | Unknown |
| `A56DC07C` | 4 | Unknown |
| `A91D7C1D` | 5 | Unknown |
| `43ECBEF0` | 6 | Unknown |
| `76DAA5F7` | 7 | Unknown |
| `54BA211C` | 8 | Unknown |
| `4B2263D3` | 9 | Unknown |
| `70647BFC` | 10 | Unknown |
| `C36D5F62` | 11 | Unknown |
| `D490401C` | 12 | Unknown |

### enum_10063184
| Hash | Value | Description |
| --- | --- | --- |
| `D2A4CC31` | 0 | Unknown |
| `FFA34C00` | 1 | Unknown |

### enum_1006349c
| Hash | Value | Description |
| --- | --- | --- |
| `E16BF6ED` | 0 | Unknown |
| `77AE54CF` | 1 | Unknown |
| `A147AFD7` | 2 | Unknown |

### enum_100634b4
| Hash | Value | Description |
| --- | --- | --- |
| `D0DF2C32` | 0 | Unknown |
| `87B5B2A5` | 1 | Unknown |
| `10987914` | 2 | Unknown |
| `02637DC1` | 3 | Unknown |

### enum_10063dd4
| Hash | Value | Description |
| --- | --- | --- |
| `6C7FA393` | 0 | Unknown |
| `DA721143` | 1 | Unknown |
| `11749399` | 2 | Unknown |
| `8A260F84` | 3 | Unknown |
| `B707BDCB` | 4 | Unknown |
| `9805B65D` | 5 | Unknown |
| `C321A4A2` | 6 | Unknown |
| `2D757AA1` | 7 | Unknown |
| `9D4D5FB7` | 8 | Unknown |

### enum_10064500
| Hash | Value | Description |
| --- | --- | --- |
| `1CF0B4A6` | 0 | Unknown |
| `12BBDB40` | 1 | Unknown |
| `6563CE29` | 2 | Unknown |

### enum_100647b4
| Hash | Value | Description |
| --- | --- | --- |
| `376DE13D` | 0 | Unknown |
| `A1357B5F` | 3 | Unknown |

### enum_10065094
| Hash | Value | Description |
| --- | --- | --- |
| `6E1ABCF4` | 0 | Unknown |
| `D2FD45BC` | 1 | Unknown |
| `209EA819` | 2 | Unknown |
| `586D50A4` | 3 | Unknown |

### enum_10065560
| Hash | Value | Description |
| --- | --- | --- |
| `3191180C` | 0 | Unknown |
| `595E9B8C` | 1 | Unknown |
| `1201C9AF` | 2 | Unknown |

### enum_10065b90
| Hash | Value | Description |
| --- | --- | --- |
| `FF2D8D1F` | 0 | Unknown |
| `44CEF64B` | 1 | Unknown |
| `8FBCD751` | 2 | Unknown |
| `C147E849` | 3 | Unknown |
| `2718D132` | 4 | Unknown |

### enum_10065bb8
| Hash | Value | Description |
| --- | --- | --- |
| `59B5B2A8` | 0 | Unknown |
| `F28AC950` | 1 | Unknown |
| `E87F2182` | 2 | Unknown |
| `5F6D6C60` | 3 | Unknown |

### enum_10065bd8
| Hash | Value | Description |
| --- | --- | --- |
| `F1E6E990` | 0 | Unknown |
| `0D90F050` | 1 | Unknown |
| `FB5C98F2` | 2 | Unknown |
| `4EAE34C6` | 3 | Unknown |
| `01A9C4A6` | 4 | Unknown |
| `FBA406A6` | 5 | Unknown |

### enum_10065c08
| Hash | Value | Description |
| --- | --- | --- |
| `BA120A00` | 1 | Unknown |
| `6612352C` | 2 | Unknown |
| `668F641C` | 3 | Unknown |
| `099033E3` | 4 | Unknown |
| `5B318081` | 5 | Unknown |
| `A3EB7D9F` | 6 | Unknown |
| `A64ABDB8` | 7 | Unknown |

### enum_10065c40
| Hash | Value | Description |
| --- | --- | --- |
| `DCFA4009` | 0 | Unknown |
| `B2F54AD0` | 1 | Unknown |
| `CC5BDBD9` | 2 | Unknown |

### enum_10065c58
| Hash | Value | Description |
| --- | --- | --- |
| `908E19F6` | 0 | Unknown |
| `145AE48B` | 1 | Unknown |
| `FF814DA5` | 2 | Unknown |
| `C1B175B5` | 3 | Unknown |
| `FC9024A9` | 4 | Unknown |
| `F295F7EF` | 5 | Unknown |
| `6EB3AB88` | 6 | Unknown |
| `48CF2B85` | 7 | Unknown |
| `CF4F8BFA` | 8 | Unknown |
| `34D67A91` | 9 | Unknown |

### enum_10066324
| Hash | Value | Description |
| --- | --- | --- |
| `A1A1B52D` | 0 | Unknown |
| `B6F2BFDC` | 1 | Unknown |
| `385D3D21` | 2 | Unknown |

### enum_10066354
| Hash | Value | Description |
| --- | --- | --- |
| `0DA0A9C1` | 0 | Unknown |
| `DD0868E9` | 1 | Unknown |
| `387D0C50` | 2 | Unknown |
| `2BB71388` | 3 | Unknown |
| `46F7BCD0` | 4 | Unknown |
| `F7600EA7` | 5 | Unknown |
| `FEB7E676` | 6 | Unknown |
| `B263C4D7` | 7 | Unknown |

### enum_10066998
| Hash | Value | Description |
| --- | --- | --- |
| `8E9F2695` | 2 | Unknown |
| `5F9B6859` | 3 | Unknown |
| `C2081F73` | 4 | Unknown |
| `6F583355` | 5 | Unknown |

### enum_100669b8
| Hash | Value | Description |
| --- | --- | --- |
| `FB02933C` | 0 | Unknown |
| `57779E30` | 1 | Unknown |
| `01158FA5` | 2 | Unknown |

### enum_10067738
| Hash | Value | Description |
| --- | --- | --- |
| `EA370390` | 0 | Unknown |
| `E7B2AA82` | 1 | Unknown |
| `885A946C` | 2 | Unknown |
| `2C056B39` | 3 | Unknown |

### enum_10067aac
| Hash | Value | Description |
| --- | --- | --- |
| `0684E615` | 0 | Unknown |
| `7B493144` | 1 | Unknown |
| `827BDA9D` | 2 | Unknown |
| `5D1B72D7` | 3 | Unknown |
| `41F41411` | 4 | Unknown |

### enum_10067f78
| Hash | Value | Description |
| --- | --- | --- |
| `BEDDC41D` | 0 | Unknown |
| `9461EC92` | 1 | Unknown |
| `45BB1E60` | 2 | Unknown |
| `3E56F18D` | 3 | Unknown |
| `F4DD1E0B` | 4 | Unknown |
| `DB059632` | 5 | Unknown |
| `83D8149E` | 6 | Unknown |
| `B6F2D71F` | 7 | Unknown |
| `522B960F` | 8 | Unknown |
| `5D9E9B21` | 9 | Unknown |
| `7A0B29E0` | 10 | Unknown |

### enum_10068690
| Hash | Value | Description |
| --- | --- | --- |
| `AD29C053` | 0 | Unknown |
| `1DD314BF` | 1 | Unknown |
| `CC3C4C7F` | 2 | Unknown |
| `813FA723` | 3 | Unknown |
| `0380B3C1` | 4 | Unknown |
| `B498DC5D` | 5 | Unknown |
| `BE74C450` | 4294967295 | Unknown |

### enum_100689a0
| Hash | Value | Description |
| --- | --- | --- |
| `EFFC39CD` | 0 | Unknown |
| `447A88F2` | 1 | Unknown |
| `D6B3F792` | 2 | Unknown |
| `0E9C75AA` | 3 | Unknown |

### enum_100689c0
| Hash | Value | Description |
| --- | --- | --- |
| `F37EE8E6` | 0 | Unknown |
| `C3D529FC` | 1 | Unknown |
| `C024D2BA` | 2 | Unknown |
| `05F37854` | 3 | Unknown |
| `CAE848BB` | 4 | Unknown |

### enum_100689e8
| Hash | Value | Description |
| --- | --- | --- |
| `26570041` | 0 | Unknown |
| `986A644C` | 1 | Unknown |
| `7488FB7D` | 2 | Unknown |
| `2C671BA1` | 3 | Unknown |
| `3F1C5CF2` | 4 | Unknown |
| `62FD0938` | 5 | Unknown |
| `73195649` | 6 | Unknown |
| `941C6366` | 7 | Unknown |
| `0A19CE34` | 8 | Unknown |
| `8F692B38` | 9 | Unknown |
| `3DBD11CD` | 10 | Unknown |
| `F375FD2A` | 11 | Unknown |
| `3021A441` | 12 | Unknown |
| `F55C3CFF` | 13 | Unknown |
| `35B9B826` | 14 | Unknown |
| `FEEAE3AA` | 15 | Unknown |

### enum_10069720
| Hash | Value | Description |
| --- | --- | --- |
| `92EFF4D9` | 0 | Unknown |
| `7398EE4D` | 1 | Unknown |
| `A821497B` | 2 | Unknown |
| `F352AE8D` | 3 | Unknown |
| `3979CB0C` | 4 | Unknown |
| `31760EA8` | 5 | Unknown |
| `E26C201C` | 6 | Unknown |
| `C2AA05FC` | 7 | Unknown |

### enum_10069760
| Hash | Value | Description |
| --- | --- | --- |
| `E10EC963` | 0 | Unknown |
| `8A67B7EE` | 1 | Unknown |
| `3615C611` | 2 | Unknown |
| `8E310BB9` | 3 | Unknown |
| `72256D35` | 4 | Unknown |
| `3A569DD6` | 5 | Unknown |
| `63B7965D` | 6 | Unknown |
| `AE3C0966` | 7 | Unknown |

### enum_100697a0
| Hash | Value | Description |
| --- | --- | --- |
| `4482C8C2` | 0 | Unknown |
| `E1746521` | 1 | Unknown |
| `0DF5CB09` | 2 | Unknown |
| `85676792` | 3 | Unknown |
| `844427A6` | 4 | Unknown |

### enum_10069d84
| Hash | Value | Description |
| --- | --- | --- |
| `44556CED` | 0 | Unknown |
| `6F8E85C5` | 1 | Unknown |
| `49B10853` | 2 | Unknown |
| `AB9958FC` | 3 | Unknown |
| `0F04C0D5` | 4 | Unknown |

### enum_10069dc4
| Hash | Value | Description |
| --- | --- | --- |
| `5674C4C4` | 0 | Unknown |
| `73BE407C` | 1 | Unknown |
| `496403D8` | 2 | Unknown |
| `CAB09844` | 3 | Unknown |
| `27FA38CB` | 4 | Unknown |
| `4FC8BDFD` | 5 | Unknown |
| `E2A0A768` | 6 | Unknown |
| `A41DAC9C` | 7 | Unknown |
| `BA8A923D` | 8 | Unknown |

### enum_10069efc
| Hash | Value | Description |
| --- | --- | --- |
| `DD7847AE` | 0 | Unknown |
| `29D51768` | 1 | Unknown |

### enum_1006a908
| Hash | Value | Description |
| --- | --- | --- |
| `7B879133` | 0 | Unknown |
| `414A8F84` | 1 | Unknown |
| `DE71C86D` | 2 | Unknown |

### enum_1006acd0
| Hash | Value | Description |
| --- | --- | --- |
| `81CCA293` | 0 | Unknown |
| `247BE1E9` | 1 | Unknown |
| `A3A3D82F` | 2 | Unknown |

### enum_1006ace8
| Hash | Value | Description |
| --- | --- | --- |
| `1F7E10D9` | 0 | Unknown |
| `566FDFB0` | 1 | Unknown |
| `B6BCE6BE` | 2 | Unknown |
| `07ACB6D2` | 3 | Unknown |

### enum_1006ad08
| Hash | Value | Description |
| --- | --- | --- |
| `36EAC70D` | 0 | Unknown |
| `95E59460` | 1 | Unknown |
| `C31342A7` | 2 | Unknown |

### enum_1006ad20
| Hash | Value | Description |
| --- | --- | --- |
| `7F879FC2` | 0 | Unknown |
| `0A142868` | 1 | Unknown |
| `033C4454` | 2 | Unknown |
| `4B09F336` | 3 | Unknown |

### enum_1006ad40
| Hash | Value | Description |
| --- | --- | --- |
| `55273BAF` | 0 | Unknown |
| `FA3D6B51` | 1 | Unknown |
| `5DC05F5B` | 2 | Unknown |
| `2F98D32B` | 3 | Unknown |

### enum_1006ad60
| Hash | Value | Description |
| --- | --- | --- |
| `71BA08F2` | 0 | Unknown |
| `6DED0C31` | 1 | Unknown |
| `FE44580C` | 2 | Unknown |

### enum_1006d010
| Hash | Value | Description |
| --- | --- | --- |
| `853D1F05` | 0 | Unknown |
| `7805C47E` | 1 | Unknown |
| `51281500` | 2 | Unknown |

### enum_1006d028
| Hash | Value | Description |
| --- | --- | --- |
| `3E631196` | 0 | Unknown |
| `4BF1377B` | 1 | Unknown |
| `526E5E7B` | 2 | Unknown |
| `916E557E` | 3 | Unknown |
| `F7C0EEE1` | 4 | Unknown |
| `2F20343B` | 5 | Unknown |
| `8A15F883` | 6 | Unknown |

### enum_1006d060
| Hash | Value | Description |
| --- | --- | --- |
| `DF08310F` | 0 | Unknown |
| `CF3424E3` | 1 | Unknown |
| `B9300091` | 2 | Unknown |
| `761EC84A` | 3 | Unknown |
| `AB995A55` | 4 | Unknown |
| `CEB7CBC6` | 5 | Unknown |
| `4DBBD1D3` | 6 | Unknown |
| `355178AE` | 7 | Unknown |

### enum_1006d580
| Hash | Value | Description |
| --- | --- | --- |
| `43BC4B7F` | 0 | Unknown |
| `8DFA2F73` | 1 | Unknown |
| `0BFBA094` | 2 | Unknown |
| `E21CF832` | 3 | Unknown |

### enum_1006d720
| Hash | Value | Description |
| --- | --- | --- |
| `E78A1094` | 0 | Unknown |

### enum_1006d728
| Hash | Value | Description |
| --- | --- | --- |
| `C56ED496` | 0 | Unknown |
| `DC3226CC` | 1 | Unknown |
| `B983EFFC` | 2 | Unknown |

### enum_1006dbd0
| Hash | Value | Description |
| --- | --- | --- |
| `C9FFB594` | 0 | Unknown |
| `571ADB92` | 1 | Unknown |
| `23E6A4AA` | 2 | Unknown |

### enum_1006e734
| Hash | Value | Description |
| --- | --- | --- |
| `8D58FFF6` | 0 | Unknown |
| `9AB0B1DD` | 1 | Unknown |
| `6004DCE0` | 2 | Unknown |
| `DD35C2D8` | 3 | Unknown |
| `057B3023` | 4 | Unknown |
| `95367762` | 5 | Unknown |
| `F282760A` | 6 | Unknown |
| `CDC6D4FB` | 7 | Unknown |
| `32FB4822` | 8 | Unknown |
| `6F7EC99A` | 10 | Unknown |
| `D3D679CB` | 11 | Unknown |
| `2887ABFA` | 12 | Unknown |
| `6723D2B8` | 13 | Unknown |
| `D9C87035` | 14 | Unknown |
| `084D6A7B` | 15 | Unknown |
| `73950426` | 16 | Unknown |
| `3BD0FD91` | 17 | Unknown |
| `6F3F4B7D` | 18 | Unknown |
| `5CCF147F` | 19 | Unknown |
| `910BA67C` | 20 | Unknown |
| `48F3F3CF` | 21 | Unknown |
| `9F229415` | 22 | Unknown |
| `1C3A9AEC` | 23 | Unknown |
| `63142970` | 24 | Unknown |
| `0D70EB7D` | 25 | Unknown |

### enum_1006e8e0
| Hash | Value | Description |
| --- | --- | --- |
| `AF5FAFDD` | 0 | Unknown |
| `E2228F9C` | 1 | Unknown |

### enum_10072144
| Hash | Value | Description |
| --- | --- | --- |
| `8A37137C` | 0 | Unknown |
| `2F88764C` | 1 | Unknown |
| `0B85BC2A` | 2 | Unknown |

### enum_1007215c
| Hash | Value | Description |
| --- | --- | --- |
| `B2560F94` | 0 | Unknown |
| `8AD0D4C4` | 1 | Unknown |
| `297864C0` | 2 | Unknown |
| `4C8B8ACB` | 3 | Unknown |
| `515114EB` | 4 | Unknown |
| `FD913E84` | 5 | Unknown |
| `BDC537C5` | 6 | Unknown |
| `E588F629` | 7 | Unknown |
| `71E7BAC3` | 8 | Unknown |
| `5FF35748` | 9 | Unknown |
| `D29D5664` | 10 | Unknown |
| `F069C4A5` | 11 | Unknown |
| `083CDDF2` | 12 | Unknown |
| `E9B68FEA` | 13 | Unknown |
| `DEB31D61` | 14 | Unknown |
| `17B12AC2` | 15 | Unknown |
| `A4CC0D0D` | 16 | Unknown |
| `61A4C24A` | 17 | Unknown |
| `0DF20A9E` | 18 | Unknown |
| `23B24667` | 19 | Unknown |

### enum_10072400
| Hash | Value | Description |
| --- | --- | --- |
| `59B9160E` | 0 | Unknown |
| `0EF94CB3` | 1 | Unknown |
| `55A1344B` | 2 | Unknown |
| `2B2C5AC0` | 3 | Unknown |
| `FDFFD48F` | 4 | Unknown |
| `0DFB1961` | 5 | Unknown |
| `74791903` | 6 | Unknown |
| `E088A4B7` | 7 | Unknown |
| `1EB33111` | 8 | Unknown |
| `FCF10303` | 9 | Unknown |
| `472C001A` | 10 | Unknown |

### enum_10072584
| Hash | Value | Description |
| --- | --- | --- |
| `D3A1704F` | 0 | Unknown |
| `EFDF4FB3` | 1 | Unknown |
| `7D0F26BF` | 2 | Unknown |
| `87A57D30` | 3 | Unknown |
| `4D2C24BE` | 4 | Unknown |
| `143DF245` | 5 | Unknown |

### enum_100725bc
| Hash | Value | Description |
| --- | --- | --- |
| `A4B64C53` | 0 | Unknown |
| `5D2B46D7` | 1 | Unknown |
| `2B463AA4` | 2 | Unknown |
| `F921F854` | 3 | Unknown |
| `5E771522` | 4 | Unknown |
| `E2CC16BC` | 5 | Unknown |

### enum_100725f8
| Hash | Value | Description |
| --- | --- | --- |
| `816FE91B` | 0 | Unknown |
| `48E3B12D` | 1 | Unknown |

### enum_100726a8
| Hash | Value | Description |
| --- | --- | --- |
| `DE1FA629` | 0 | Unknown |
| `27859E0D` | 1 | Unknown |
| `3202AAAF` | 2 | Unknown |
| `2B626016` | 3 | Unknown |
| `74F4142F` | 4 | Unknown |
| `D6B9CB0E` | 5 | Unknown |
| `2860D7E4` | 6 | Unknown |
| `8164EF8C` | 7 | Unknown |
| `B410D547` | 8 | Unknown |
| `F22705C9` | 9 | Unknown |
| `7CE8756F` | 10 | Unknown |

### enum_10072edc
| Hash | Value | Description |
| --- | --- | --- |
| `8F8C9B7E` | 0 | Unknown |
| `F4B41268` | 1 | Unknown |
| `9B2526C1` | 2 | Unknown |
| `24C9DC47` | 3 | Unknown |
| `A1C0D4A2` | 4 | Unknown |

### enum_100747f0
| Hash | Value | Description |
| --- | --- | --- |
| `9E2914C8` | 0 | Unknown |
| `B8291D56` | 1 | Unknown |
| `CAADE6FC` | 2 | Unknown |
| `78A07890` | 3 | Unknown |
| `E1831399` | 4 | Unknown |

### enum_10074818
| Hash | Value | Description |
| --- | --- | --- |
| `745CAE3A` | 0 | Unknown |
| `C4E95FFD` | 1 | Unknown |
| `197B1B3F` | 2 | Unknown |
| `1B8D15E5` | 3 | Unknown |
| `446EC290` | 4 | Unknown |

### enum_10074a70
| Hash | Value | Description |
| --- | --- | --- |
| `6857F53C` | 0 | Unknown |
| `265D8DAE` | 1 | Unknown |
| `B1B8D415` | 2 | Unknown |
| `B068A5B9` | 3 | Unknown |
| `B4DF9D2D` | 4 | Unknown |
| `B275383C` | 5 | Unknown |

### enum_10074dbc
| Hash | Value | Description |
| --- | --- | --- |
| `BF28EE54` | 0 | Unknown |
| `942BE2B7` | 1 | Unknown |
| `FD9337D8` | 2 | Unknown |
| `D1BD1C3B` | 3 | Unknown |
| `AF17C2A1` | 4 | Unknown |

### enum_10075d28
| Hash | Value | Description |
| --- | --- | --- |
| `72ECFAC1` | 0 | Unknown |
| `18EEF1B9` | 1 | Unknown |
| `853E246F` | 2 | Unknown |
| `D30DCAC0` | 3 | Unknown |

### enum_10075eb8
| Hash | Value | Description |
| --- | --- | --- |
| `D5B3B9E2` | 1 | Unknown |
| `AFE11D94` | 2 | Unknown |
| `867597E5` | 3 | Unknown |

### enum_100761b0
| Hash | Value | Description |
| --- | --- | --- |
| `03322696` | 0 | Unknown |
| `7A7E2516` | 1 | Unknown |

### enum_10076330
| Hash | Value | Description |
| --- | --- | --- |
| `E2ACDA4F` | 0 | Unknown |
| `5AAD4776` | 1 | Unknown |
| `630CA8EC` | 2 | Unknown |

### enum_10077078
| Hash | Value | Description |
| --- | --- | --- |
| `EA0D3B4D` | 1 | Unknown |
| `467102B5` | 2 | Unknown |
| `D6F096EC` | 3 | Unknown |
| `51B3AD06` | 4 | Unknown |
| `50483579` | 5 | Unknown |

### enum_10077550
| Hash | Value | Description |
| --- | --- | --- |
| `C66DAD2A` | 0 | Unknown |
| `EFF6831A` | 1 | Unknown |

### enum_100781b8
| Hash | Value | Description |
| --- | --- | --- |
| `7B6E1013` | 1 | Unknown |
| `CEAE1152` | 2 | Unknown |

### enum_10079200
| Hash | Value | Description |
| --- | --- | --- |
| `8D804AE4` | 0 | Unknown |
| `179086D5` | 1 | Unknown |

### enum_10079210
| Hash | Value | Description |
| --- | --- | --- |
| `9ADFDF89` | 0 | Unknown |
| `2FE518DC` | 1 | Unknown |
| `5FA08273` | 2 | Unknown |
| `45E0A2AF` | 3 | Unknown |
| `4420B113` | 4 | Unknown |
| `2420556F` | 5 | Unknown |
| `5093CB7D` | 6 | Unknown |
| `597C542D` | 7 | Unknown |
| `AE4ABF7A` | 8 | Unknown |
| `05B0888D` | 9 | Unknown |
| `B572CD5C` | 10 | Unknown |
| `3336CE27` | 11 | Unknown |
| `D1B090C5` | 12 | Unknown |
| `3F9349DE` | 13 | Unknown |
| `57EB03AB` | 14 | Unknown |
| `286B2B1F` | 15 | Unknown |
| `D44E8F0A` | 16 | Unknown |
| `2268AEFB` | 17 | Unknown |

### enum_10079b9c
| Hash | Value | Description |
| --- | --- | --- |
| `39649833` | 0 | Unknown |
| `8D93376A` | 1 | Unknown |
| `E4008797` | 2 | Unknown |
| `A15A7B36` | 3 | Unknown |
| `8F7C4239` | 4 | Unknown |
| `62310E55` | 5 | Unknown |
| `95CF2827` | 6 | Unknown |
| `80F63B4E` | 7 | Unknown |

### enum_1007a31c
| Hash | Value | Description |
| --- | --- | --- |
| `0713E1D0` | 0 | Unknown |
| `EF5980BE` | 1 | Unknown |

### enum_1007a590
| Hash | Value | Description |
| --- | --- | --- |
| `B37859B1` | 0 | Unknown |
| `15E7951B` | 1 | Unknown |
| `361B519F` | 2 | Unknown |
| `DE65C47B` | 3 | Unknown |

### enum_1007a5b0
| Hash | Value | Description |
| --- | --- | --- |
| `25A3CB91` | 0 | Unknown |
| `0ED52426` | 1 | Unknown |
| `BAA2C3C0` | 2 | Unknown |
| `8BB632F5` | 3 | Unknown |
| `0632E543` | 4 | Unknown |
| `64D8A655` | 5 | Unknown |

### enum_1007a89c
| Hash | Value | Description |
| --- | --- | --- |
| `E2C73240` | 0 | Unknown |
| `251B8764` | 1 | Unknown |

### enum_1007a8ac
| Hash | Value | Description |
| --- | --- | --- |
| `341BABDF` | 0 | Unknown |
| `F5F672FE` | 1 | Unknown |

### enum_1007a998
| Hash | Value | Description |
| --- | --- | --- |
| `80D0BE65` | 0 | Unknown |
| `DC193DE2` | 1 | Unknown |

### enum_1007be40
| Hash | Value | Description |
| --- | --- | --- |
| `3465E40F` | 0 | Unknown |
| `1BE2D101` | 1 | Unknown |
| `FACD1FB0` | 2 | Unknown |

### enum_1007c078
| Hash | Value | Description |
| --- | --- | --- |
| `9B256798` | 0 | Unknown |
| `8EA42261` | 1 | Unknown |

### enum_1007c3ec
| Hash | Value | Description |
| --- | --- | --- |
| `5D1B268C` | 0 | Unknown |
| `EB240000` | 1 | Unknown |
| `5D64C83F` | 2 | Unknown |
| `60289DEF` | 3 | Unknown |

### enum_1007c4b8
| Hash | Value | Description |
| --- | --- | --- |
| `8E45B358` | 0 | Unknown |
| `75C15CD9` | 1 | Unknown |
| `B223AA8A` | 2 | Unknown |
| `140F251A` | 3 | Unknown |

### enum_1007c900
| Hash | Value | Description |
| --- | --- | --- |
| `FA36722E` | 0 | Unknown |
| `95A253CB` | 1 | Unknown |
| `7CF3C55F` | 2 | Unknown |
| `1D4EBE77` | 3 | Unknown |

### enum_1007d040
| Hash | Value | Description |
| --- | --- | --- |
| `E84CFC59` | 0 | Unknown |
| `0EA6CA02` | 1 | Unknown |
| `2F6FF6F4` | 2 | Unknown |
| `A1C9200B` | 3 | Unknown |

### enum_1007d080
| Hash | Value | Description |
| --- | --- | --- |
| `4A44387A` | 0 | Unknown |
| `11F22EA8` | 1 | Unknown |
| `38706BD5` | 2 | Unknown |
| `42ADC3BD` | 3 | Unknown |
| `3350D300` | 4 | Unknown |
| `13195797` | 5 | Unknown |
| `266C15B6` | 6 | Unknown |

### enum_1007d3b4
| Hash | Value | Description |
| --- | --- | --- |
| `C7CD87E9` | 0 | Unknown |
| `C18DED34` | 1 | Unknown |

### enum_1007da8c
| Hash | Value | Description |
| --- | --- | --- |
| `2AF87817` | 1 | Unknown |
| `8218D249` | 2 | Unknown |
| `C1C00517` | 3 | Unknown |
| `33CE301D` | 4 | Unknown |
| `4382B132` | 5 | Unknown |
| `6052C9BC` | 6 | Unknown |
| `F12E5A8A` | 7 | Unknown |

### enum_1007e0d8
| Hash | Value | Description |
| --- | --- | --- |
| `361DE251` | 0 | Unknown |
| `8FD3D8E6` | 1 | Unknown |
| `1A049079` | 2 | Unknown |
| `5022D958` | 3 | Unknown |

### enum_1007e0f8
| Hash | Value | Description |
| --- | --- | --- |
| `BC4CFEC2` | 0 | Unknown |
| `97E7A0F6` | 1 | Unknown |
| `C148B289` | 2 | Unknown |

### enum_1007e110
| Hash | Value | Description |
| --- | --- | --- |
| `44DEC60F` | 0 | Unknown |
| `BAB9DC76` | 1 | Unknown |
| `60F39987` | 2 | Unknown |
| `B15ED9E0` | 3 | Unknown |

### enum_1007e130
| Hash | Value | Description |
| --- | --- | --- |
| `BC82C314` | 0 | Unknown |
| `5CAE608D` | 1 | Unknown |
| `CE9F1B22` | 2 | Unknown |
| `430A3D85` | 3 | Unknown |
| `62ECD990` | 4 | Unknown |

### enum_1007e7f0
| Hash | Value | Description |
| --- | --- | --- |
| `A389FD1D` | 0 | Unknown |
| `49EC61C5` | 1 | Unknown |

### enum_1007e8bc
| Hash | Value | Description |
| --- | --- | --- |
| `B9FFD51B` | 0 | Unknown |
| `7A8AF911` | 1 | Unknown |
| `F6E09F04` | 2 | Unknown |
| `7595E986` | 3 | Unknown |
| `D4A3D919` | 4 | Unknown |

### enum_1008169c
| Hash | Value | Description |
| --- | --- | --- |
| `F606C0B1` | 0 | Unknown |
| `8DEE41BE` | 1 | Unknown |

### enum_10081788
| Hash | Value | Description |
| --- | --- | --- |
| `80CBD010` | 0 | Unknown |
| `F8775465` | 1 | Unknown |
| `93900C43` | 2 | Unknown |
| `7ECFF9A4` | 3 | Unknown |

### enum_100817d8
| Hash | Value | Description |
| --- | --- | --- |
| `1F639F4A` | 0 | Unknown |
| `3993549F` | 1 | Unknown |
| `F4E74A86` | 2 | Unknown |
| `25262061` | 3 | Unknown |
| `DAB18043` | 4 | Unknown |
| `87106DB2` | 5 | Unknown |
| `F9CDD384` | 6 | Unknown |
| `5F04C046` | 7 | Unknown |
| `CA1C9712` | 8 | Unknown |

### enum_100819cc
| Hash | Value | Description |
| --- | --- | --- |
| `B487DD88` | 0 | Unknown |
| `AAD2A32A` | 1 | Unknown |
| `90C33BCE` | 2 | Unknown |
| `35B38C2B` | 3 | Unknown |
| `9DC264E5` | 4 | Unknown |
| `804709A4` | 5 | Unknown |

### enum_100819fc
| Hash | Value | Description |
| --- | --- | --- |
| `DDE58284` | 0 | Unknown |
| `2F6B109A` | 1 | Unknown |
| `16DB42FA` | 2 | Unknown |
| `ED4E681A` | 3 | Unknown |

### enum_10081b18
| Hash | Value | Description |
| --- | --- | --- |
| `1A8DDE8A` | 0 | Unknown |
| `80043D46` | 1 | Unknown |
| `FC0B9025` | 2 | Unknown |

### enum_100822f8
| Hash | Value | Description |
| --- | --- | --- |
| `96479D6F` | 0 | Unknown |
| `50690788` | 1 | Unknown |

### enum_10082454
| Hash | Value | Description |
| --- | --- | --- |
| `A335CD6C` | 0 | Unknown |
| `B1D48655` | 1 | Unknown |
| `51F194BD` | 2 | Unknown |

### enum_10093c7c
| Hash | Value | Description |
| --- | --- | --- |
| `085860D9` | 0 | Unknown |
| `D45913B3` | 1 | Unknown |
| `081E7B2D` | 2 | Unknown |
| `A4032ACE` | 3 | Unknown |
| `7B29FDD2` | 4 | Unknown |
| `FBD835E2` | 5 | Unknown |

### enum_100942e8
| Hash | Value | Description |
| --- | --- | --- |
| `45988D1C` | 0 | Unknown |
| `95A5CB0D` | 1 | Unknown |
| `C3B929C5` | 2 | Unknown |

### enum_100953f8
| Hash | Value | Description |
| --- | --- | --- |
| `C1E17C86` | 0 | Unknown |
| `97705612` | 1 | Unknown |
| `E9E613D9` | 2 | Unknown |
| `88C38DB0` | 3 | Unknown |

### enum_10095418
| Hash | Value | Description |
| --- | --- | --- |
| `C7FAB687` | 0 | Unknown |
| `AE7A641B` | 1 | Unknown |
| `63BBEE31` | 2 | Unknown |
| `C0E0BE08` | 3 | Unknown |
| `BE6B2C15` | 4 | Unknown |
| `10196C3D` | 5 | Unknown |
| `89BCA1C4` | 6 | Unknown |
| `BE3FAE67` | 7 | Unknown |
| `253C841B` | 8 | Unknown |
| `CE94BF27` | 9 | Unknown |
| `30E01CC0` | 10 | Unknown |
| `0EAC449E` | 11 | Unknown |
| `5DE3B382` | 12 | Unknown |
| `B3D18503` | 13 | Unknown |
| `6E80A2D9` | 14 | Unknown |
| `5490625C` | 15 | Unknown |
| `E59EF4BD` | 16 | Unknown |
| `55E8D659` | 17 | Unknown |
| `F130D35E` | 18 | Unknown |
| `33253362` | 19 | Unknown |
| `F23F2C2E` | 20 | Unknown |
| `CE293835` | 22 | Unknown |
| `3A971FCA` | 23 | Unknown |
| `B669B865` | 24 | Unknown |
| `004D5E2C` | 25 | Unknown |
| `CCB4D165` | 26 | Unknown |
| `E323835F` | 27 | Unknown |

### enum_1009599c
| Hash | Value | Description |
| --- | --- | --- |
| `303B0F45` | 0 | Unknown |
| `732DF493` | 1 | Unknown |

### enum_10097070
| Hash | Value | Description |
| --- | --- | --- |
| `4C53DC4A` | 0 | Unknown |
| `C614B8E2` | 1 | Unknown |
| `ED45D05B` | 2 | Unknown |
| `4B23318F` | 3 | Unknown |
| `99CC32E0` | 4 | Unknown |

### enum_100980c4
| Hash | Value | Description |
| --- | --- | --- |
| `DBC557AC` | 0 | Unknown |
| `46226312` | 1 | Unknown |
| `19D356EE` | 2 | Unknown |

### enum_1009c43c
| Hash | Value | Description |
| --- | --- | --- |
| `7D212D80` | 0 | Unknown |
| `6F98DDAD` | 1 | Unknown |
| `A3B41761` | 2 | Unknown |
| `D2F37A3A` | 3 | Unknown |

[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[CVector3f]: types.md#cvector3f
[CColor4f]: types.md#ccolor4f
[CMayaSpline]: types.md#cmayaspline
[CTimelineData]: types.md#ctimelinedata
[Property]: properties.md
[List]: types.md#list
[String]: types.md#string
[CString]: types.md#cstring