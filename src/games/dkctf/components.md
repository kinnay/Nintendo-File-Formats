## [DKC:TF](../../formats.md#dkctf) > Components

A level consists of components, each of which belongs to an entity (CEntityGOC). Most components have their attributes stored in a [struct](structs.md).

| Table of Contents |
| --- |
| [Component Types](#component-types) |
| [Interface Types](#interface-types) |

# Component Types
| Hash | Component |
| --- | --- |
| `749749F1` | [CEntityGOC](#centitygoc) |
| `4EC5FA3A` | [CFakePlayerControlsGOC](#cfakeplayercontrolsgoc) |
| `57153AA4` | [CStaticCollisionGOC](#cstaticcollisiongoc) |
| `41956904` | [CRenderWorldGOC](#crenderworldgoc) |
| `B4361E7B` | [CActorCollisionGOC](#cactorcollisiongoc) |
| `2BE8BC19` | [CLightStaticGOC](#clightstaticgoc) |
| `9EE5541D` | [CLightDynamicGOC](#clightdynamicgoc) |
| `CD098F70` | [CEffectGOC](#ceffectgoc) |
| `8FE0BFC9` | [CRelayGOC](#crelaygoc) |
| `A7DB53C1` | [CCounterGOC](#ccountergoc) |
| `ADA85938` | [CSeaLionGOC](#csealiongoc) |
| `AAEBA313` | [CWarusKingGOC](#cwaruskinggoc) |
| `05DD288E` | [CSwitchGOC](#cswitchgoc) |
| `9E8A4940` | [CTimerGOC](#ctimergoc) |
| `D616EE8B` | [CControllerActionGOC](#ccontrolleractiongoc) |
| `D898656D` | [CWaypointGOC](#cwaypointgoc) |
| `F0240D23` | [CPathControlGOC](#cpathcontrolgoc) |
| `4FE57689` | [CCameraHintGOC](#ccamerahintgoc) |
| `97E65DDD` | [CTouchableTriggerGOC](#ctouchabletriggergoc) |
| `1A4117AB` | [CToucherGOC](#ctouchergoc) |
| `C49D730E` | [CTriggerLogicGOC](#ctriggerlogicgoc) |
| `D47974E4` | [CFiniteStateMachineGOC](#cfinitestatemachinegoc) |
| `1349E5AC` | [CCustomInterpolationGOC](#ccustominterpolationgoc) |
| `C1F64515` | [CCameraTargetGOC](#ccameratargetgoc) |
| `DE522669` | [CGeneratorGOC](#cgeneratorgoc) |
| `1383F6D6` | [CGeneratorDeleterGOC](#cgeneratordeletergoc) |
| `2C4F2D31` | [CSplineMotionGOC](#csplinemotiongoc) |
| `1223437C` | [CCreatureGOC](#ccreaturegoc) |
| `21C57D2B` | [CDynamicActorCollisionGOC](#cdynamicactorcollisiongoc) |
| `DF31EC16` | [CRenderGOC](#crendergoc) |
| `AE921C3B` | [CPlayerGOC](#cplayergoc) |
| `81A242A0` | [CDirectionalIrradianceMapGOC](#cdirectionalirradiancemapgoc) |
| `BDE4AB05` | [CTakeDamageGOC](#ctakedamagegoc) |
| `5453C979` | [CMasterSlaveGOC](#cmasterslavegoc) |
| `07E3137F` | [CTraceObjectGOC](#ctraceobjectgoc) |
| `046FAD23` | [CTimerSequenceGOC](#ctimersequencegoc) |
| `3175DF36` | [CApplyDamageGOC](#capplydamagegoc) |
| `65E2349B` | [CRelayRandomGOC](#crelayrandomgoc) |
| `ABBCFC6A` | [CRelayConditionalGOC](#crelayconditionalgoc) |
| `EA30E0B1` | [CSpawnPointGOC](#cspawnpointgoc) |
| `1FB9AF22` | [CActorKeyframeGOC](#cactorkeyframegoc) |
| `CB6D9ACE` | [CPlayerProxyGOC](#cplayerproxygoc) |
| `6FB22081` | [CBarrelCannonGOC](#cbarrelcannongoc) |
| `F4567AD7` | [CRumbleEffectGOC](#crumbleeffectgoc) |
| `10EA9EC8` | [CObjectFollowGOC](#cobjectfollowgoc) |
| `481EA5AF` | [CPickupGOC](#cpickupgoc) |
| `BC9A60AE` | [CCameraManagerGOC](#ccameramanagergoc) |
| `DB38B3FB` | [CGroundPoundDetectorGOC](#cgroundpounddetectorgoc) |
| `BE82DEF3` | [CProjectileGOC](#cprojectilegoc) |
| `43C0D52A` | [CClingPathControlGOC](#cclingpathcontrolgoc) |
| `B85D6790` | [CColorModifierGOC](#ccolormodifiergoc) |
| `021C14B0` | [CExplosionGOC](#cexplosiongoc) |
| `16702F15` | [CReloadSetLoaderGOC](#creloadsetloadergoc) |
| `660FC7C1` | [CCheckpointGOC](#ccheckpointgoc) |
| `8C2CCFAC` | [CPlayerRespawnGOC](#cplayerrespawngoc) |
| `C0281AE7` | [CImpulseDriverGOC](#cimpulsedrivergoc) |
| `D4538C9B` | [CBouncerGOC](#cbouncergoc) |
| `06E89BE7` | [CHealthGOC](#chealthgoc) |
| `E0AFAF06` | [CPlayerActionHintGOC](#cplayeractionhintgoc) |
| `1A90271D` | [CGrabbableGOC](#cgrabbablegoc) |
| `3C23783B` | [CGrabThrowGOC](#cgrabthrowgoc) |
| `9373FEC0` | [CRespawnGOC](#crespawngoc) |
| `AF565E69` | [CSwingRopeGOC](#cswingropegoc) |
| `C7B43DA6` | [CActorInteractionGOC](#cactorinteractiongoc) |
| `C9ED6454` | [CWindWakerGOC](#cwindwakergoc) |
| `78D8893A` | [CCameraTargetPlayerGOC](#ccameratargetplayergoc) |
| `A86E6401` | [CPoiObjectGOC](#cpoiobjectgoc) |
| `FDD83489` | [CSoundGOC](#csoundgoc) |
| `CCAD4BD9` | [CPerformanceGroupControllerGOC](#cperformancegroupcontrollergoc) |
| `502506D6` | [CTouchSetGOC](#ctouchsetgoc) |
| `88603CF7` | [CMineCartProxyGOC](#cminecartproxygoc) |
| `E1E1C49C` | [CWaterVolumeGOC](#cwatervolumegoc) |
| `6C5D597D` | [CNearVisibleGOC](#cnearvisiblegoc) |
| `3449A5DF` | [CSwimmerGOC](#cswimmergoc) |
| `591D8F55` | [CCharacterPrimitivesCollisionGOC](#ccharacterprimitivescollisiongoc) |
| `90D8D3CE` | [CRenderMethodResolverGOC](#crendermethodresolvergoc) |
| `BD4CFA2F` | [CTriggerForceGOC](#ctriggerforcegoc) |
| `3150D2F6` | [CFuseBombGOC](#cfusebombgoc) |
| `AF3A06F2` | [CPathControlZiplineGOC](#cpathcontrolziplinegoc) |
| `D32870DF` | [CPolarBearGOC](#cpolarbeargoc) |
| `2131C235` | [CGroupSpawnGOC](#cgroupspawngoc) |
| `2751EBF2` | [CAnimationGridControllerGOC](#canimationgridcontrollergoc) |
| `18B96D29` | [CTimerAnimationGridParamProviderGOC](#ctimeranimationgridparamprovidergoc) |
| `B9F9F04C` | [CActionDetectorGOC](#cactiondetectorgoc) |
| `343A47F7` | [CCameraShakerGOC](#ccamerashakergoc) |
| `06159C2D` | [CRespawnBalloonGOC](#crespawnballoongoc) |
| `7E6063C8` | [CPlayerActorGOC](#cplayeractorgoc) |
| `91F22DCF` | [CTippyGOC](#ctippygoc) |
| `89F426F2` | [CCinematicCameraShotGOC](#ccinematiccamerashotgoc) |
| `1EB2749F` | [CConveyorModifierGOC](#cconveyormodifiergoc) |
| `73AECD92` | [CFogVolumeGOC](#cfogvolumegoc) |
| `845E492A` | [CRetronomeGOC](#cretronomegoc) |
| `23C5DFF4` | [CWaterRenderVolumeGOC](#cwaterrendervolumegoc) |
| `55F80CCE` | [CCinematicSkipHandlerGOC](#ccinematicskiphandlergoc) |
| `AB5C5D7B` | [CBonusRoomGOC](#cbonusroomgoc) |
| `3A3A6FAD` | [CTireBounceGOC](#ctirebouncegoc) |
| `9D25FE2D` | [CBeatUpHandlerGOC](#cbeatuphandlergoc) |
| `9FC07D01` | [COwlGOC](#cowlgoc) |
| `A42F7AB9` | [CGrabbableGeneratorGOC](#cgrabbablegeneratorgoc) |
| `F34EDD1F` | [CInventoryItemGOC](#cinventoryitemgoc) |
| `18C0AD0F` | [CEndGameGOC](#cendgamegoc) |
| `EBE92100` | [CRocketBarrelProxyGOC](#crocketbarrelproxygoc) |
| `B7ADA3EC` | [CBurningBranchGOC](#cburningbranchgoc) |
| `59AB515E` | [CHotCoalsGOC](#chotcoalsgoc) |
| `E21D45CB` | [CBarrelBalloonGOC](#cbarrelballoongoc) |
| `6302BBB3` | [CUVTransformGOC](#cuvtransformgoc) |
| `5FEF037B` | [CBaboonGOC](#cbaboongoc) |
| `25899782` | [CMusicDataGOC](#cmusicdatagoc) |
| `1AC8C8FD` | [CMusicStateControllerGOC](#cmusicstatecontrollergoc) |
| `47A60DC3` | [CMusicSystemTransportGOC](#cmusicsystemtransportgoc) |
| `5CF17BFE` | [CAdapterManagerGOC](#cadaptermanagergoc) |
| `CA08C6A4` | [CWaterRenderDecalGOC](#cwaterrenderdecalgoc) |
| `7F6D1CBA` | [CRelayAutoFireGOC](#crelayautofiregoc) |
| `3DAAF68B` | [CBaboonManagerGOC](#cbaboonmanagergoc) |
| `D745DC42` | [CGraphicalTransitionGOC](#cgraphicaltransitiongoc) |
| `0FA3899C` | [CRetronomeDriverGOC](#cretronomedrivergoc) |
| `57E54B9D` | [CEndLevelGOC](#cendlevelgoc) |
| `6780941E` | [CSuperCombinedAbilityEmitterGOC](#csupercombinedabilityemittergoc) |
| `B8B6A22E` | [CSuperCombinedAbilityResponderGOC](#csupercombinedabilityrespondergoc) |
| `0AF8D63C` | [CMapPlayerGOC](#cmapplayergoc) |
| `8CB5BF7D` | [CMapPathControlGOC](#cmappathcontrolgoc) |
| `EBE0DAEE` | [CWaterCurrentVolumeGOC](#cwatercurrentvolumegoc) |
| `A7D1C922` | [CCausticVolumeGOC](#ccausticvolumegoc) |
| `35D8F3F0` | [CPufferFishGOC](#cpufferfishgoc) |
| `BA796FEF` | [CPlaylistGOC](#cplaylistgoc) |
| `C2F2282A` | [CWindWakerImpulserGOC](#cwindwakerimpulsergoc) |
| `E03DD39F` | [CMapNodeGOC](#cmapnodegoc) |
| `55AAB5F1` | [CRambiCrateGOC](#crambicrategoc) |
| `24D9D323` | [CAudioEffectGOC](#caudioeffectgoc) |
| `F7602744` | [CDSPGOC](#cdspgoc) |
| `160E9AF9` | [CRoomSettingsGOC](#croomsettingsgoc) |
| `5746A908` | [CDynamicActorControlGOC](#cdynamicactorcontrolgoc) |
| `59276E0E` | [CHUDAnchorGOC](#chudanchorgoc) |
| `F442A668` | [CTimeKeyframeGOC](#ctimekeyframegoc) |
| `B6040870` | [CRelayProbabilityGameModeGOC](#crelayprobabilitygamemodegoc) |
| `F3847DE3` | [CFlyingPickupEffectGOC](#cflyingpickupeffectgoc) |
| `212BCDF5` | [CSimpleShadowGOC](#csimpleshadowgoc) |
| `655C5175` | [CAudioBusControllerGOC](#caudiobuscontrollergoc) |
| `F6751A5D` | [CPlayerKeyframeGOC](#cplayerkeyframegoc) |
| `C04DAF13` | [CBreathMonitorGOC](#cbreathmonitorgoc) |
| `4C7B9FC8` | [CDirectionalIrradianceProbesGOC](#cdirectionalirradianceprobesgoc) |
| `0BE7FC29` | [CSurfaceControlGOC](#csurfacecontrolgoc) |
| `B6EC1A51` | [CSimpleSoundGOC](#csimplesoundgoc) |
| `D2CAC9A5` | [CLightGroupProxyGOC](#clightgroupproxygoc) |
| `DFD2A23A` | [CDialogPanelGOC](#cdialogpanelgoc) |
| `BCCB1B30` | [CMinecartPathManagerGOC](#cminecartpathmanagergoc) |
| `D856F6B9` | [CImpostorGOC](#cimpostorgoc) |
| `BD040603` | [CLevelDarkenerGOC](#cleveldarkenergoc) |
| `A72A9926` | [CRenderGroupGOC](#crendergroupgoc) |
| `3258FD44` | [CRenderToFlashGOC](#crendertoflashgoc) |
| `3ABCFF68` | [CSkinSwapGOC](#cskinswapgoc) |
| `C532AD25` | [CScreenCaptureToFlashGOC](#cscreencapturetoflashgoc) |
| `B152AD59` | [CPlayerSoundGOC](#cplayersoundgoc) |
| `BFF963D2` | [CStreamedMovieGOC](#cstreamedmoviegoc) |
| `7DCAF170` | [CBloomEffectGOC](#cbloomeffectgoc) |
| `1243C3E3` | [CProjectedSimpleShadowReceiverGOC](#cprojectedsimpleshadowreceivergoc) |
| `5368FF52` | [CShopDataGOC](#cshopdatagoc) |
| `A04F0C68` | [CShopInstanceGOC](#cshopinstancegoc) |
| `5B0C954B` | [CUICameraSelectorGOC](#cuicameraselectorgoc) |
| `7CC0B7BF` | [CSquawksGOC](#csquawksgoc) |
| `B177FA02` | [CSquawksProxyGOC](#csquawksproxygoc) |
| `4C53A836` | [CLoadUnitControllerGOC](#cloadunitcontrollergoc) |
| `008E3AF5` | [CFlashTextureSwapperGOC](#cflashtextureswappergoc) |
| `F5D80D1A` | [CExtrasGOC](#cextrasgoc) |
| `BB449D71` | [CExtrasTypeGOC](#cextrastypegoc) |
| `A98F9015` | [CExtrasCategoryGOC](#cextrascategorygoc) |
| `EE0D6FD4` | [CDynamicLoadManagerGOC](#cdynamicloadmanagergoc) |
| `FDDB58A1` | [CMapManagerProxyGOC](#cmapmanagerproxygoc) |
| `A32E718F` | [CAchievementGOC](#cachievementgoc) |
| `62913993` | [CAudioBusMixerGOC](#caudiobusmixergoc) |
| `ADCD416E` | [CCreditsGOC](#ccreditsgoc) |
| `A4E4FE1D` | [CHUDFadeDetectorGOC](#chudfadedetectorgoc) |
| `AF9DEA76` | [CProductionFrontEndProxyGOC](#cproductionfrontendproxygoc) |

## CEntityGOC
This component describes an entity in the game. An entity does nothing on its own. It must be linked to other components. An entity that wants to draw a model should be linked to a CRenderGOC for example.

| Type | Description |
| --- | --- |
| Bool | Active on construction |
| [CVector3f] | Position |
| [CVector3f] | Rotation |
| [CVector3f] | Scale |

The components that belong to this entity are linked to it with link id `COMP`.

## CFakePlayerControlsGOC

## CStaticCollisionGOC

## CRenderWorldGOC
This component draws a world model.

| Type | Description |
| --- | --- |
| [SLdrRenderWorld](DKCTF-Ldr-Types-(Q-Z)#sldrrenderworld) | Info |
| NBakedLighting::SDIMScriptData | DIM script data |

## CActorCollisionGOC
This component controls actor collisions.

| Type | Description |
| --- | --- |
| [SLdrActorCollision](DKCTF-Ldr-Types-(A-C)#sldractorcollision) | Info |

<br>

| Link ID | Description |
| --- | --- |
| `IL00` | [ITouchableGOC](#itouchablegoc) |

## CLightStaticGOC

## CLightDynamicGOC

## CEffectGOC

## CRelayGOC

## CCounterGOC

## CSeaLionGOC

## CWarusKingGOC

## CSwitchGOC

## CTimerGOC

## CControllerActionGOC

## CWaypointGOC

## CPathControlGOC

## CCameraHintGOC

## CTouchableTriggerGOC

## CToucherGOC

## CTriggerLogicGOC

## CFiniteStateMachineGOC

## CCustomInterpolationGOC

## CCameraTargetGOC

## CGeneratorGOC

## CGeneratorDeleterGOC

## CSplineMotionGOC
This component describes the movement behavior of an actor.

| Type | Description |
| --- | --- |
| [SLdrSplineMotion](DKCTF-Ldr-Types-(Q-Z)#sldrsplinemotion) | Info |

<br>

| Link ID | Description |
| --- | --- |
| `IL00` | [CPathControlGOC](#cpathcontrolgoc) |

## CCreatureGOC
This component describes an enemy.

| Type | Description |
| --- | --- |
| [SLdrCreature](DKCTF-Ldr-Types-(A-C)#sldrcreature) | Info |

<br>

| Link ID | Description |
| --- | --- |
| `IL01` | [CApplyDamageGOC](#capplydamagegoc) |
| `IL02` | [CTakeDamageGOC](#ctakedamagegoc) |
| `IL03` | [CDynamicActorCollisionGOC](#cdynamicactorcollisiongoc) |
| `IL04` | [ITouchableGOC](#itouchablegoc) |
| `IL09` | [CGrabbableGOC](#cgrabbablegoc) |
| `IL10` | [CActorInteractionGOC](#cactorinteractiongoc) |
| `IL11` | [CRespawnGOC](#crespawngoc) |
| `IL16` | [CSwimmerGOC](#cswimmergoc) |
| `IL18` | [CAdapterManagerGOC](#cadaptermanagergoc) |

## CDynamicActorCollisionGOC

## CRenderGOC
This component draws a static or animated model.

| Type | Description |
| --- | --- |
| [SLdrRender](DKCTF-Ldr-Types-(Q-Z)#sldrrender) | Info |

## CPlayerGOC

## CDirectionalIrradianceMapGOC

## CTakeDamageGOC

## CMasterSlaveGOC

## CTraceObjectGOC

## CTimerSequenceGOC

## CApplyDamageGOC

## CRelayRandomGOC

## CRelayConditionalGOC

## CSpawnPointGOC

## CActorKeyframeGOC

## CPlayerProxyGOC

## CBarrelCannonGOC

## CRumbleEffectGOC

## CObjectFollowGOC

## CPickupGOC

## CCameraManagerGOC

## CGroundPoundDetectorGOC

## CProjectileGOC

## CClingPathControlGOC

## CColorModifierGOC

## CExplosionGOC

## CReloadSetLoaderGOC

## CCheckpointGOC

## CPlayerRespawnGOC

## CImpulseDriverGOC

## CBouncerGOC

## CHealthGOC

## CPlayerActionHintGOC

## CGrabbableGOC

## CGrabThrowGOC

## CRespawnGOC

## CSwingRopeGOC

## CActorInteractionGOC

## CWindWakerGOC

## CCameraTargetPlayerGOC

## CPoiObjectGOC

## CSoundGOC

## CPerformanceGroupControllerGOC

## CTouchSetGOC

## CMineCartProxyGOC

## CWaterVolumeGOC

## CNearVisibleGOC

## CSwimmerGOC

## CCharacterPrimitivesCollisionGOC

## CRenderMethodResolverGOC

## CTriggerForceGOC

## CFuseBombGOC

## CPathControlZiplineGOC

## CPolarBearGOC

## CGroupSpawnGOC

## CAnimationGridControllerGOC

## CTimerAnimationGridParamProviderGOC

## CActionDetectorGOC

## CCameraShakerGOC

## CRespawnBalloonGOC

## CPlayerActorGOC

## CTippyGOC

## CCinematicCameraShotGOC

## CConveyorModifierGOC

## CFogVolumeGOC

## CRetronomeGOC

## CWaterRenderVolumeGOC

## CCinematicSkipHandlerGOC

## CBonusRoomGOC

## CTireBounceGOC

## CBeatUpHandlerGOC

## COwlGOC

## CGrabbableGeneratorGOC

## CInventoryItemGOC

## CEndGameGOC

## CRocketBarrelProxyGOC

## CBurningBranchGOC

## CHotCoalsGOC

## CBarrelBalloonGOC

## CUVTransformGOC

## CBaboonGOC

## CMusicDataGOC

## CMusicStateControllerGOC

## CMusicSystemTransportGOC

## CAdapterManagerGOC

## CWaterRenderDecalGOC

## CRelayAutoFireGOC

## CBaboonManagerGOC

## CGraphicalTransitionGOC

## CRetronomeDriverGOC

## CEndLevelGOC

## CSuperCombinedAbilityEmitterGOC

## CSuperCombinedAbilityResponderGOC

## CMapPlayerGOC

## CMapPathControlGOC

## CWaterCurrentVolumeGOC

## CCausticVolumeGOC

## CPufferFishGOC

## CPlaylistGOC

## CWindWakerImpulserGOC

## CMapNodeGOC

## CRambiCrateGOC

## CAudioEffectGOC

## CDSPGOC

## CRoomSettingsGOC

## CDynamicActorControlGOC

## CHUDAnchorGOC

## CTimeKeyframeGOC

## CRelayProbabilityGameModeGOC

## CFlyingPickupEffectGOC

## CSimpleShadowGOC

## CAudioBusControllerGOC

## CPlayerKeyframeGOC

## CBreathMonitorGOC

## CDirectionalIrradianceProbesGOC

## CSurfaceControlGOC

## CSimpleSoundGOC

## CLightGroupProxyGOC

## CDialogPanelGOC

## CMinecartPathManagerGOC

## CImpostorGOC

## CLevelDarkenerGOC

## CRenderGroupGOC

## CRenderToFlashGOC

## CSkinSwapGOC

## CScreenCaptureToFlashGOC

## CPlayerSoundGOC

## CStreamedMovieGOC

## CBloomEffectGOC

## CProjectedSimpleShadowReceiverGOC

## CShopDataGOC

## CShopInstanceGOC

## CUICameraSelectorGOC

## CSquawksGOC

## CSquawksProxyGOC

## CLoadUnitControllerGOC

## CFlashTextureSwapperGOC

## CExtrasGOC

## CExtrasTypeGOC

## CExtrasCategoryGOC

## CDynamicLoadManagerGOC

## CMapManagerProxyGOC

## CAchievementGOC

## CAudioBusMixerGOC

## CCreditsGOC

## CHUDFadeDetectorGOC

## CProductionFrontEndProxyGOC

# Interface Types
| Hash | Component |
| --- | --- |
| `F7251CB6` | [IPlayerGOC](#iplayergoc) |
| `6C4F0858` | [IPhysicsGOC](#iphysicsgoc) |
| `93A8D5FF` | [IActorGOC](#iactorgoc) |
| `AA305C31` | [IGameHintGOC](#igamehintgoc) |
| `9564C5D8` | [ITouchableGOC](#itouchablegoc) |
| `1F4A183F` | [IAnimationGridParamProviderGOC](#ianimationgridparamprovidergoc) |
| `4EC74F7D` | [ICameraTargetGOC](#icameratargetgoc) |
| `6DEAFE0C` | [ITimerGOC](#itimergoc) |

### IPlayerGOC
| Components |
| --- |
| [CPlayerGOC](#cplayergoc) |

### IPhysicsGOC
| Components |
| --- |
| [CActorCollisionGOC](#cactorcollisiongoc) |
| CDynamicActorCollisionGOC |
| CCharacterPrimitivesCollisionGOC |

### IActorGOC
| Components |
| --- |
| [CCreatureGOC](#ccreaturegoc) |
| [CSeaLionGOC](#csealiongoc) |
| [COwlGOC](#cowlgoc) |
| [CBaboonGOC](#cbaboongoc) |
| [CPufferFishGOC](#cpufferfishgoc) |
| [CPolarBearGOC](#cpolarbeargoc) |
| [CWarusKingGOC](#cwaruskinggoc) |

### IGameHintGOC
| Components |
| --- |
| [CCameraHintGOC](#ccamerahintgoc) |

### ITouchableGOC
| Components |
| --- |
| [CToucherGOC](#ctouchergoc) |
| [CTouchSetGOC](#ctouchsetgoc) |
| [CTouchableTriggerGOC](#ctouchabletriggergoc) |
| [CGroundPoundDetectorGOC](#cgroundpounddetectorgoc) |
| [CPoiObjectGOC](#cpoiobjectgoc) |

### IAnimationGridParamProviderGOC
| Components |
| --- |
| [CTimerAnimationGridParamProviderGOC](#ctimeranimationgridparamprovidergoc) |

### ICameraTargetGOC
| Components |
| --- |
| [CCameraTargetGOC](#ccameratargetgoc) |
| [CCameraTargetPlayerGOC](#ccameratargetplayergoc) |

### ITimerGOC
| Components |
| --- |
| [CTimerGOC](#ctimergoc) |
| [CTimerSequenceGOC](#ctimersequencegoc) |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CAssetHeader]: types.md#cassetheader
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[CVector3f]: types.md#cvector3f