## [DKC:TF](/formats.md#dkctf) > Properties

### Property Format
| Type | Description |
| --- | --- |
| Uint32 | [Type (crc32)](#property-table) |
| Uint16 | Length |
| ... | Data |

Most properties have their data stored in a [loader struct](structs.md).

### Interface Tables
Every property inherits an abstract interface class.

#### IRenderMethod
| Properties |
| --- |
| [CRenderStaticModel](#crenderstaticmodel) |
| [CRenderStaticModelArray](#crenderstaticmodelarray) |
| [CRenderAnimatedModel](#crenderanimatedmodel) |
| [CRenderMethodGameMode](#crendermethodgamemode) |

#### IPositionSplineControl
| Properties |
| --- |
| [CXYZPositionSplineControl](#cxyzpositionsplinecontrol) |

#### IActorModuleData
| Properties |
| --- |
| [CAlternateDamageInfoData](#CAlternateDamageInfoData) |
| [CAnimationControllerData](#CAnimationControllerData) |
| [CAnimationGridDriverData](#CAnimationGridDriverData) |
| [CBaboonControllerData](#CBaboonControllerData) |
| [CBehaviorAutoDestructData](#CBehaviorAutoDestructData) |
| [CBehaviorBopJumpData](#CBehaviorBopJumpData) |
| [CBehaviorBopJumpProceduralData](#CBehaviorBopJumpProceduralData) |
| [CBehaviorBreachJumpData](#CBehaviorBreachJumpData) |
| [CBehaviorChangePostureData](#CBehaviorChangePostureData) |
| [CBehaviorDespawnData](#CBehaviorDespawnData) |
| [CBehaviorExplodeReactionData](#CBehaviorExplodeReactionData) |
| [CBehaviorFlipData](#CBehaviorFlipData) |
| [CBehaviorFollowDynamicPathData](#CBehaviorFollowDynamicPathData) |
| [CBehaviorFollowPathProceduralData](#CBehaviorFollowPathProceduralData) |
| [CBehaviorFollowSurfaceData](#CBehaviorFollowSurfaceData) |
| [CBehaviorGlideJumpData](#CBehaviorGlideJumpData) |
| [CBehaviorGrabbedData](#CBehaviorGrabbedData) |
| [CBehaviorGridAttackData](#CBehaviorGridAttackData) |
| [CBehaviorHitReactionData](#CBehaviorHitReactionData) |
| [CBehaviorFallData](#CBehaviorFallData) |
| [CBehaviorIceCubeData](#CBehaviorIceCubeData) |
| [CBehaviorKnockbackProceduralData](#CBehaviorKnockbackProceduralData) |
| [CBehaviorLinearProjectileData](#CBehaviorLinearProjectileData) |
| [CBehaviorMeleeAttackData](#CBehaviorMeleeAttackData) |
| [CBehaviorPolarBearCubeSlingData](#CBehaviorPolarBearCubeSlingData) |
| [CBehaviorPolarBearDelayedSlamData](#CBehaviorPolarBearDelayedSlamData) |
| [CBehaviorPolarBearIcyChargeData](#CBehaviorPolarBearIcyChargeData) |
| [CBehaviorPolarBearIcyRoarData](#CBehaviorPolarBearIcyRoarData) |
| [CBehaviorPolarBearMegaLeapData](#CBehaviorPolarBearMegaLeapData) |
| [CBehaviorPolarBearMegaSlamData](#CBehaviorPolarBearMegaSlamData) |
| [CBehaviorPolarBearSummersaultSlamData](#CBehaviorPolarBearSummersaultSlamData) |
| [CBehaviorProjectileAttackData](#CBehaviorProjectileAttackData) |
| [CBehaviorScriptedOneShotAnimationData](#CBehaviorScriptedOneShotAnimationData) |
| [CBehaviorSeaLionPainguinData](#CBehaviorSeaLionPainguinData) |
| [CBehaviorSeaLionRingData](#CBehaviorSeaLionRingData) |
| [CBehaviorSecondaryProjectileAttackData](#CBehaviorSecondaryProjectileAttackData) |
| [CBehaviorSeekerData](#CBehaviorSeekerData) |
| [CBehaviorSlaveControllerData](#CBehaviorSlaveControllerData) |
| [CBehaviorStationaryData](#CBehaviorStationaryData) |
| [CBehaviorSwimPathProceduralData](#CBehaviorSwimPathProceduralData) |
| [CBehaviorSwimSurfaceData](#CBehaviorSwimSurfaceData) |
| [CBehaviorSwoopAttackData](#CBehaviorSwoopAttackData) |
| [CBehaviorTargetedWanderData](#CBehaviorTargetedWanderData) |
| [CBehaviorTeleportData](#CBehaviorTeleportData) |
| [CBehaviorVolumeTargetingData](#CBehaviorVolumeTargetingData) |
| [CBlinkAnimationData](#CBlinkAnimationData) |
| [CCharacterPrimitivesData](#CCharacterPrimitivesData) |
| [CDamageTypeRuleSetData](#CDamageTypeRuleSetData) |
| [CFollowerDriverData](#CFollowerDriverData) |
| [COwlControllerData](#COwlControllerData) |
| [CPolarBearControllerData](#CPolarBearControllerData) |
| [CPufferFishControllerData](#CPufferFishControllerData) |
| [CSeaLionControllerData](#CSeaLionControllerData) |
| [CSeaLionRuleSetData](#CSeaLionRuleSetData) |
| [CStackData](#CStackData) |
| [CTargetingData](#CTargetingData) |
| [CBehaviorFollowPathData](#CBehaviorFollowPathData) |
| [CBehaviorStunReactionData](#CBehaviorStunReactionData) |
| [CBehaviorHurlReactionData](#CBehaviorHurlReactionData) |
| [CBehaviorContactReactionData](#CBehaviorContactReactionData) |
| [CBehaviorKnockbackReactionData](#CBehaviorKnockbackReactionData) |
| [CBehaviorSpawnData](#CBehaviorSpawnData) |
| [CBehaviorWanderData](#CBehaviorWanderData) |
| [CBehaviorWanderProceduralData](#CBehaviorWanderProceduralData) |
| [CCollisionData](#CCollisionData) |
| [CHealthData](#CHealthData) |
| [CBehaviorKnockbackStunReactionData](#CBehaviorKnockbackStunReactionData) |
| [CMovementData](#CMovementData) |
| [CCreatureRuleSetData](#CCreatureRuleSetData) |
| [CFSMData](#CFSMData) |
| [CSplineTrackerData](#CSplineTrackerData) |
| [CTerrainAlignmentData](#CTerrainAlignmentData) |
| [CWarusKingControllerData](#CWarusKingControllerData) |
| [CWeaponData](#CWeaponData) |

### Property Table
| Type | Property |
| --- | --- |
| `FD5CF041` | [CCircle](#ccircle) |
| `1D8FDCE1` | [CRectangle](#crectangle) |
| `64E405E8` | [CMotionSplineControl](#cmotionsplinecontrol) |
| `2C408D6B` | [CEulerOrientationSplineControl](#ceulerorientationsplinecontrol) |
| `39C3A3CB` | [CTargetOrientationSplineControl](#ctargetorientationsplinecontrol) |
| `FFC90130` | [CAdoptSplineOrientationSplineControl](#cadoptsplineorientationsplinecontrol) |
| `288054B5` | [CAutoDestructTypeLandCounter](#cautodestructtypelandcounter) |
| `2D42F6D2` | [CAutoDestructTypeTimer](#cautodestructtypetimer) |
| `383736F8` | [CTargetingData](#ctargetingdata) |
| `B288914E` | [CBehaviorAutoDestructData](#cbehaviorautodestructdata) |
| `AF2788C7` | [CBlinkAnimationData](#cblinkanimationdata) |
| `AB5E7A9D` | [CBehaviorBopJumpData](#cbehaviorbopjumpdata) |
| `864A23A5` | [CBehaviorBopJumpProceduralData](#cbehaviorbopjumpproceduraldata) |
| `A1F64818` | [CBehaviorHitReactionData](#cbehaviorhitreactiondata) |
| `296F94B7` | [CBehaviorFallData](#cbehaviorfalldata) |
| `6D5FCBDD` | [CBehaviorFollowDynamicPathData](#cbehaviorfollowdynamicpathdata) |
| `BAFCD92D` | [CBehaviorFollowPathData](#cbehaviorfollowpathdata) |
| `0F27596C` | [CBehaviorSeaLionPainguinData](#cbehaviorsealionpainguindata) |
| `AC8FAED6` | [CBehaviorSeaLionRingData](#cbehaviorsealionringdata) |
| `226C8828` | [CBehaviorStunReactionData](#cbehaviorstunreactiondata) |
| `E429C269` | [CBehaviorHurlReactionData](#cbehaviorhurlreactiondata) |
| `C9C184D3` | [CBehaviorContactReactionData](#cbehaviorcontactreactiondata) |
| `60876DD4` | [CBehaviorKnockbackReactionData](#cbehaviorknockbackreactiondata) |
| `ABFD70AC` | [CBehaviorSpawnData](#cbehaviorspawndata) |
| `B79B006C` | [CBehaviorWanderData](#cbehaviorwanderdata) |
| `02ADE7CF` | [CBehaviorWanderProceduralData](#cbehaviorwanderproceduraldata) |
| `565A5AC9` | [CCollisionData](#ccollisiondata) |
| `E588D266` | [CHealthData](#chealthdata) |
| `57BFAFD2` | [CBehaviorKnockbackStunReactionData](#cbehaviorknockbackstunreactiondata) |
| `05EAAA12` | [CMovementData](#cmovementdata) |
| `C1CB7111` | [CCreatureRuleSetData](#ccreaturerulesetdata) |
| `96582863` | [CDamageTypeRuleSetData](#cdamagetyperulesetdata) |
| `B21E82E4` | [CFSMData](#cfsmdata) |
| `88C3A263` | [CSeaLionControllerData](#csealioncontrollerdata) |
| `7B03BE87` | [CSeaLionRuleSetData](#csealionrulesetdata) |
| `FE4E1F23` | [CSplineTrackerData](#csplinetrackerdata) |
| `9A3BD099` | [CAnimationControllerData](#canimationcontrollerdata) |
| `C31654A8` | [CAnimationGridDriverData](#canimationgriddriverdata) |
| `C3C999C6` | [CMovementConfiguration](#cmovementconfiguration) |
| `ADA6B7DB` | [CRenderAnimatedModel](#crenderanimatedmodel) |
| `13F5701A` | [CRenderStaticModel](#crenderstaticmodel) |
| `B5F34BD6` | [COffsetPositionBehaviorData](#coffsetpositionbehaviordata) |
| `F598B4B0` | [CPrimaryTargetTrackingBehaviorData](#cprimarytargettrackingbehaviordata) |
| `26BE03FA` | [CRenderStaticModelArray](#crenderstaticmodelarray) |
| `A0460EC5` | [CTerrainAlignmentData](#cterrainalignmentdata) |
| `6D77535C` | [CBopJumpSequenceTargetPlayer](#cbopjumpsequencetargetplayer) |
| `D3519979` | [CNormalBopJumpSequence](#cnormalbopjumpsequence) |
| `07A96601` | [CRandomBopJumpSequence](#crandombopjumpsequence) |
| `9B395543` | [CSidescrollerTrackingBehaviorData](#csidescrollertrackingbehaviordata) |
| `435C7F1C` | [CPIDConvergenceData](#cpidconvergencedata) |
| `FCE7C683` | [CProportionalConvergenceData](#cproportionalconvergencedata) |
| `66596967` | [CSpringConvergenceData](#cspringconvergencedata) |
| `C538D36F` | [CVelocityConvergenceData](#cvelocityconvergencedata) |
| `BB84C366` | [CSimpleMotionBehaviorData](#csimplemotionbehaviordata) |
| `198CB0A2` | [CScaleSplineControl](#cscalesplinecontrol) |
| `52245677` | [CHorizontalLeadPositionBehaviorData](#chorizontalleadpositionbehaviordata) |
| `AF1299BD` | [CFrameGroundPositionBehaviorData](#cframegroundpositionbehaviordata) |
| `775EA30A` | [CSidescrollPositionBehaviorData](#csidescrollpositionbehaviordata) |
| `895340AC` | [CCameraTargetOrientationBehaviorData](#ccameratargetorientationbehaviordata) |
| `D9286FE9` | [CPathPositionBehaviorData](#cpathpositionbehaviordata) |
| `80DA4F71` | [CAABoxShapeData](#caaboxshapedata) |
| `6EDE23E6` | [CSphereShapeData](#csphereshapedata) |
| `53649072` | [CPlayerModuleControllerData](#cplayermodulecontrollerdata) |
| `0AD85D5E` | [CPlayerModuleCharacterMovementData](#cplayermodulecharactermovementdata) |
| `CDE16E50` | [CPlayerModuleHealthData](#cplayermodulehealthdata) |
| `F467A1DE` | [CPlayerModuleSplineAdvancementData](#cplayermodulesplineadvancementdata) |
| `962B3C01` | [CPlayerModuleJumpData](#cplayermodulejumpdata) |
| `CADD5210` | [CPlayerModuleTerrainAlignmentData](#cplayermoduleterrainalignmentdata) |
| `444E223D` | [CPlayerModuleMountData](#cplayermodulemountdata) |
| `CA8EA08B` | [CPlayerModuleSlaveData](#cplayermoduleslavedata) |
| `F33110A4` | [CPlayerModuleTireData](#cplayermoduletiredata) |
| `AED0EBD9` | [CPlayerModuleBarrelCannonData](#cplayermodulebarrelcannondata) |
| `4111D77A` | [CPlayerModuleKnockbackData](#cplayermoduleknockbackdata) |
| `4EF61C34` | [CPlayerModuleJumpUpLedgeData](#cplayermodulejumpupledgedata) |
| `75733E90` | [CPlayerModuleGroundPoundData](#cplayermodulegroundpounddata) |
| `5DBF3B02` | [CPlayerModuleRollData](#cplayermodulerolldata) |
| `CF776D98` | [CPlayerModuleCrouchData](#cplayermodulecrouchdata) |
| `B708DE94` | [CPlayerModuleAnimationData](#cplayermoduleanimationdata) |
| `D830FA25` | [CPlayerModuleClingData](#cplayermoduleclingdata) |
| `4DD9BDC0` | [CPlayerModuleRocketBarrelData](#cplayermodulerocketbarreldata) |
| `C18B8E7F` | [CPlayerModuleBasicMovementData](#cplayermodulebasicmovementdata) |
| `20073581` | [CProjectileMotionPhysics](#cprojectilemotionphysics) |
| `E888BD6D` | [CProjectileMotionHomingMissile](#cprojectilemotionhomingmissile) |
| `2DC4D32B` | [CProjectileMotionSpline](#cprojectilemotionspline) |
| `346ED8EF` | [CProjectileMotionTargetedPhysics](#cprojectilemotiontargetedphysics) |
| `2BFBE0B6` | [CProjectileMotionTargetedSpline](#cprojectilemotiontargetedspline) |
| `0096A13B` | [CProjectileMotionTerrainMovement](#cprojectilemotionterrainmovement) |
| `FD6DE071` | [CProjectileMotionWaypointFollower](#cprojectilemotionwaypointfollower) |
| `DA0EFBE3` | [CPlayerModulePeanutGunData](#cplayermodulepeanutgundata) |
| `D685F811` | [CPlayerModuleStalledDescentData](#cplayermodulestalleddescentdata) |
| `21B01969` | [CBopJumpNormalJumpTypeData](#cbopjumpnormaljumptypedata) |
| `E8BDC1C0` | [CBopJumpPeriodicJumpTypeData](#cbopjumpperiodicjumptypedata) |
| `DCF70286` | [CBopJumpReactiveJumpTypeData](#cbopjumpreactivejumptypedata) |
| `3D11A970` | [CBopJumpNoneDirectionalControlData](#cbopjumpnonedirectionalcontroldata) |
| `0F4F1A72` | [CBopJumpPingPongDirectionalControlData](#cbopjumppingpongdirectionalcontroldata) |
| `1156A20B` | [CBopJumpRandomDirectionalControlData](#cbopjumprandomdirectionalcontroldata) |
| `171D65C6` | [CBopJumpSeekPlayerDirectionalControlData](#cbopjumpseekplayerdirectionalcontroldata) |
| `F3C39F26` | [CPlayerModuleMineCartData](#cplayermoduleminecartdata) |
| `F5B3C068` | [CFlyerMovementConfiguration](#cflyermovementconfiguration) |
| `7C11F87A` | [CDynamicPullbackBehaviorData](#cdynamicpullbackbehaviordata) |
| `F8C942CB` | [CPullbackMotionBehaviorData](#cpullbackmotionbehaviordata) |
| `CDFF2FC1` | [CPlayerModuleMeleeData](#cplayermodulemeleedata) |
| `6BC66310` | [CPlayerModuleGrabData](#cplayermodulegrabdata) |
| `7903190B` | [CPlayerModuleTeleportData](#cplayermoduleteleportdata) |
| `967C95E5` | [CPlayerModuleOffscreenIndicatorData](#cplayermoduleoffscreenindicatordata) |
| `035B57ED` | [CPlayerModuleSpecialContactDamageData](#cplayermodulespecialcontactdamagedata) |
| `57D3F424` | [CPlayerModuleActionHintData](#cplayermoduleactionhintdata) |
| `99350C3B` | [CXYZPositionSplineControl](#cxyzpositionsplinecontrol) |
| `CEF3FCF1` | [COBBoxShapeData](#cobboxshapedata) |
| `67435036` | [CBehaviorFlipData](#cbehaviorflipdata) |
| `7762AE26` | [CBehaviorGrabbedData](#cbehaviorgrabbeddata) |
| `9B0A3187` | [CProjectileCollisionPrimitiveAABox](#cprojectilecollisionprimitiveaabox) |
| `3A83ACE2` | [CProjectileCollisionPrimitiveModelBounds](#cprojectilecollisionprimitivemodelbounds) |
| `55F4331A` | [CProjectileCollisionPrimitiveSphere](#cprojectilecollisionprimitivesphere) |
| `3BD9445E` | [CThrownLandingConfiguration](#cthrownlandingconfiguration) |
| `CD9AB7CE` | [CPlayerModuleSwingData](#cplayermoduleswingdata) |
| `061B8FB8` | [CAdoptCameraStateBehaviorData](#cadoptcamerastatebehaviordata) |
| `FD88E4B4` | [CTargetSelector](#ctargetselector) |
| `2D85F0CF` | [CBehaviorProjectileAttackData](#cbehaviorprojectileattackdata) |
| `27BE9018` | [CBehaviorTargetedWanderData](#cbehaviortargetedwanderdata) |
| `F380D4A8` | [CFrameTargetsPositionBehaviorData](#cframetargetspositionbehaviordata) |
| `6375DDB0` | [CProjectileAttackActionSequence](#cprojectileattackactionsequence) |
| `BE429906` | [CProjectileAttackActionSequenceRandom](#cprojectileattackactionsequencerandom) |
| `A16F825F` | [CProjectileAttackActionFireProjectile](#cprojectileattackactionfireprojectile) |
| `3035B9D5` | [CProjectileAttackActionPause](#cprojectileattackactionpause) |
| `FBD5A2D2` | [CProjectileAttackWeightedAction](#cprojectileattackweightedaction) |
| `395C01B3` | [CPlayerModuleSlideData](#cplayermoduleslidedata) |
| `0711F9C9` | [CPlayerModuleMultiKillRewardData](#cplayermodulemultikillrewarddata) |
| `0E3F140F` | [CPlayerModulePeriodicAdditiveAnimationData](#cplayermoduleperiodicadditiveanimationdata) |
| `AF4DA930` | [CBehaviorLinearProjectileData](#cbehaviorlinearprojectiledata) |
| `5C2DCE7A` | [CCharacterPrimitivesData](#ccharacterprimitivesdata) |
| `CE1E3F13` | [CTargetSelectorOffScreen](#ctargetselectoroffscreen) |
| `9CEC0655` | [CPlayerModuleHeadTrackingData](#cplayermoduleheadtrackingdata) |
| `DAD45A03` | [CBehaviorChangePostureData](#cbehaviorchangeposturedata) |
| `E95B5297` | [CPlayerModuleSwimmingData](#cplayermoduleswimmingdata) |
| `D7FB24A7` | [CWeaponData](#cweapondata) |
| `26D83772` | [CVerticalLeadPositionBehaviorData](#cverticalleadpositionbehaviordata) |
| `3BB8618F` | [CPolarBearDelayedSlam](#cpolarbeardelayedslam) |
| `D5F36803` | [CPolarBearIcyCharge](#cpolarbearicycharge) |
| `2EF2CCB4` | [CPolarBearMegaLeap](#cpolarbearmegaleap) |
| `EBE25678` | [CPolarBearSlammerTime](#cpolarbearslammertime) |
| `9567BB7D` | [CSeaLionBellyFlop](#csealionbellyflop) |
| `C39C100A` | [CSeaLionBreach](#csealionbreach) |
| `F8361C0C` | [CSeaLionHandStand](#csealionhandstand) |
| `C5ED45B3` | [CSeaLionLowRoller](#csealionlowroller) |
| `C1FBC4E4` | [CSeaLionSlipNFlip](#csealionslipnflip) |
| `DA549D10` | [CSeaLionSlipNStop](#csealionslipnstop) |
| `1F3F19DB` | [CSeaLionTossAttack](#csealiontossattack) |
| `42A3C71F` | [CSeaLionTurboSlide](#csealionturboslide) |
| `CBA8CF68` | [CSeaLionWheel](#csealionwheel) |
| `B14AFFEA` | [CWarusKingAvalanche](#cwaruskingavalanche) |
| `23A25963` | [CWarusKingBullCharge](#cwaruskingbullcharge) |
| `DD179C3F` | [CWarusKingIceStorm](#cwaruskingicestorm) |
| `D944E256` | [CWarusKingIcyBlast](#cwaruskingicyblast) |
| `AAB5288F` | [CWarusKingMegaQuake](#cwaruskingmegaquake) |
| `351309D1` | [CWarusKingRageStomp](#cwaruskingragestomp) |
| `CB037320` | [CWarusKingRoyalRumble](#cwaruskingroyalrumble) |
| `F2A13028` | [CWarusKingRoyalStomp](#cwaruskingroyalstomp) |
| `5A17D1AE` | [CWarusKingSiegeHorn](#cwaruskingsiegehorn) |
| `F5B5EA5B` | [CActorActionPlaylistConditional](#cactoractionplaylistconditional) |
| `F6715DBA` | [CActorActionPlaylistSequential](#cactoractionplaylistsequential) |
| `C289CE38` | [CPlayerModuleFlutterJumpData](#cplayermoduleflutterjumpdata) |
| `7A1B7177` | [CBehaviorFollowPathProceduralData](#cbehaviorfollowpathproceduraldata) |
| `3E8B1E74` | [CAnimationMovementConfiguration](#canimationmovementconfiguration) |
| `E6302896` | [CPlayerModuleZiplineData](#cplayermoduleziplinedata) |
| `10125C1B` | [CFollowDynamicPathJump](#cfollowdynamicpathjump) |
| `27158137` | [CFollowDynamicPathSpline](#cfollowdynamicpathspline) |
| `B04DBF28` | [CDirectionalForceField](#cdirectionalforcefield) |
| `6AD00A54` | [CProgressiveForceField](#cprogressiveforcefield) |
| `7D79DA81` | [CPlayerModuleRambiControllerData](#cplayermodulerambicontrollerdata) |
| `48A0CE9E` | [CBehaviorExplodeReactionData](#cbehaviorexplodereactiondata) |
| `816AAB4A` | [CBehaviorSlaveControllerData](#cbehaviorslavecontrollerdata) |
| `BA667A7D` | [CFramingEnforcementBehaviorData](#cframingenforcementbehaviordata) |
| `6BCA7772` | [CBehaviorGridAttackData](#cbehaviorgridattackdata) |
| `83E1C6BC` | [CBehaviorFollowSurfaceData](#cbehaviorfollowsurfacedata) |
| `4D4DA6D3` | [CPolarBearControllerData](#cpolarbearcontrollerdata) |
| `6F11FE10` | [CPlayerModuleSwimmingBreastStrokeData](#cplayermoduleswimmingbreaststrokedata) |
| `EDC8C9E5` | [CPlayerModuleSwimmingPropellerData](#cplayermoduleswimmingpropellerdata) |
| `FB9BEC8C` | [CPlayerModuleSwimmingJetBoostData](#cplayermoduleswimmingjetboostdata) |
| `5FCD8979` | [CBehaviorMeleeAttackData](#cbehaviormeleeattackdata) |
| `44A7D1AA` | [COrientationPathBehaviorData](#corientationpathbehaviordata) |
| `086CB093` | [CBehaviorPolarBearDelayedSlamData](#cbehaviorpolarbeardelayedslamdata) |
| `4FCD32AB` | [CPlayerModuleSwimmingSpinData](#cplayermoduleswimmingspindata) |
| `B8D845E8` | [CBehaviorPolarBearMegaLeapData](#cbehaviorpolarbearmegaleapdata) |
| `F5BD278D` | [CAnimatedCameraBehaviorData](#canimatedcamerabehaviordata) |
| `EC84080B` | [CBehaviorSwimPathProceduralData](#cbehaviorswimpathproceduraldata) |
| `B518A4A2` | [CPlayerModulePogoStickData](#cplayermodulepogostickdata) |
| `30C95BCF` | [CTargetSelectorRaycast](#ctargetselectorraycast) |
| `9B96C025` | [CBehaviorIceCubeData](#cbehavioricecubedata) |
| `21168134` | [CBehaviorPolarBearCubeSlingData](#cbehaviorpolarbearcubeslingdata) |
| `88AF7E8D` | [CPolarBearCubeSling](#cpolarbearcubesling) |
| `02447210` | [CBehaviorKnockbackProceduralData](#cbehaviorknockbackproceduraldata) |
| `B9DE571F` | [CBehaviorSwoopAttackData](#cbehaviorswoopattackdata) |
| `97C29C6C` | [CBehaviorSeekerData](#cbehaviorseekerdata) |
| `DB847D64` | [CBopJumpOnPlayerJumpedJumpTypeData](#cbopjumponplayerjumpedjumptypedata) |
| `BD507A04` | [COwlControllerData](#cowlcontrollerdata) |
| `51F13BD8` | [COwlSwoop](#cowlswoop) |
| `4E5CBC16` | [COwlEggToss](#cowleggtoss) |
| `AC35B106` | [COwlMegaEggToss](#cowlmegaeggtoss) |
| `06C46949` | [COwlFeatherFan](#cowlfeatherfan) |
| `D115EFC2` | [CSurfaceFollowerMovementConfiguration](#csurfacefollowermovementconfiguration) |
| `95CD27B0` | [CBehaviorPolarBearIcyRoarData](#cbehaviorpolarbearicyroardata) |
| `A59F9BF3` | [CPolarBearIcyRoar](#cpolarbearicyroar) |
| `FD1C46D2` | [CStackData](#cstackdata) |
| `F193195D` | [CFollowerDriverData](#cfollowerdriverdata) |
| `996ADDA9` | [CBehaviorPolarBearIcyChargeData](#cbehaviorpolarbearicychargedata) |
| `6E042E77` | [CBehaviorDespawnData](#cbehaviordespawndata) |
| `B30CA466` | [CAlternateDamageInfoData](#calternatedamageinfodata) |
| `755342C6` | [CTargetSelectorLinked](#ctargetselectorlinked) |
| `B41D8C82` | [CBehaviorSwimSurfaceData](#cbehaviorswimsurfacedata) |
| `74EF81D9` | [CWarusKingControllerData](#cwaruskingcontrollerdata) |
| `E61EC703` | [CBehaviorPolarBearMegaSlamData](#cbehaviorpolarbearmegaslamdata) |
| `89E1641B` | [CPolarBearMegaSlam](#cpolarbearmegaslam) |
| `229564E1` | [CPlayerModuleRiseFromTheGraveData](#cplayermodulerisefromthegravedata) |
| `BA393D16` | [CPositionAtTimeSplineControl](#cpositionattimesplinecontrol) |
| `D09B6EAE` | [CWaypointSpeedControl](#cwaypointspeedcontrol) |
| `3EAEC1EC` | [CBaboonControllerData](#cbabooncontrollerdata) |
| `38F3119D` | [CTargetedWanderSplineLengthTargeting](#ctargetedwandersplinelengthtargeting) |
| `358C6A49` | [CTargetedWanderTargetSelectorTargeting](#ctargetedwandertargetselectortargeting) |
| `FC55408A` | [CBaboonVineSwing](#cbaboonvineswing) |
| `6E8C7501` | [CBaboonMultiRoll](#cbaboonmultiroll) |
| `97DB37A4` | [COwlFeatherBlast](#cowlfeatherblast) |
| `3AC27231` | [CBehaviorBreachJumpData](#cbehaviorbreachjumpdata) |
| `1B4CC816` | [CBehaviorVolumeTargetingData](#cbehaviorvolumetargetingdata) |
| `905F5667` | [CBehaviorTeleportData](#cbehaviorteleportdata) |
| `59EF0C61` | [CBaboonBombToss](#cbaboonbombtoss) |
| `00577BA6` | [COwlWindStorm](#cowlwindstorm) |
| `E4189741` | [COwlRockRoll](#cowlrockroll) |
| `ADB9DC50` | [CGenericActorSCAHandler](#cgenericactorscahandler) |
| `270B7359` | [CPlayerModuleSuperCombinedAbilityData](#cplayermodulesupercombinedabilitydata) |
| `0B7108DA` | [CBaboonDropJump](#cbaboondropjump) |
| `7962AED5` | [CPufferFishControllerData](#cpufferfishcontrollerdata) |
| `F79FB36B` | [CPufferFishExhale](#cpufferfishexhale) |
| `9DEAEBF8` | [CPufferFishInhale](#cpufferfishinhale) |
| `FF765539` | [COwlFormation](#cowlformation) |
| `4DA620E0` | [CBehaviorStationaryData](#cbehaviorstationarydata) |
| `10847910` | [CPufferFishBounceAnimDriven](#cpufferfishbounceanimdriven) |
| `1E7F244A` | [CPufferFishBounceSeekPlayer](#cpufferfishbounceseekplayer) |
| `64599C00` | [CPufferFishSwimSeekPlayer](#cpufferfishswimseekplayer) |
| `922549B2` | [CBehaviorScriptedOneShotAnimationData](#cbehaviorscriptedoneshotanimationdata) |
| `389C33F5` | [CPlayerModuleSwimmingStaticSpinData](#cplayermoduleswimmingstaticspindata) |
| `96F675DB` | [CBaboonMultiSwing](#cbaboonmultiswing) |
| `DE9DD46F` | [CPufferFishMegaRoll](#cpufferfishmegaroll) |
| `36442275` | [CCreatureSCAHandler](#ccreaturescahandler) |
| `3F9FB43B` | [CBaboonBombSwing](#cbaboonbombswing) |
| `6BF80D35` | [CBaboonRollJump](#cbaboonrolljump) |
| `6D97B328` | [COwlBarrelSmash](#cowlbarrelsmash) |
| `36A72920` | [CBehaviorGlideJumpData](#cbehaviorglidejumpdata) |
| `7F776039` | [CPufferFishWallSlam](#cpufferfishwallslam) |
| `74F8410A` | [CTransformCameraHintBehaviorData](#ctransformcamerahintbehaviordata) |
| `18B4B4BA` | [CPlayerModuleShieldData](#cplayermoduleshielddata) |
| `1A23A873` | [CPlayerLedgeAvoidanceForce](#cplayerledgeavoidanceforce) |
| `E44C0927` | [CBehaviorSecondaryProjectileAttackData](#cbehaviorsecondaryprojectileattackdata) |
| `982529A5` | [CGameSurfacePlane](#cgamesurfaceplane) |
| `CD2EA58D` | [CPolarBearSummersaultSlam](#cpolarbearsummersaultslam) |
| `0C8FB845` | [CBehaviorPolarBearSummersaultSlamData](#cbehaviorpolarbearsummersaultslamdata) |
| `F5828B90` | [CSurfaceInputBehaviorData](#csurfaceinputbehaviordata) |
| `B4F0A604` | [CDisplacementFromCameraDataInput](#cdisplacementfromcameradatainput) |
| `EB849EE6` | [CDelayDecreaseCameraDataInput](#cdelaydecreasecameradatainput) |
| `8633A644` | [CTargetBoundingBoxSizeCameraDataInput](#ctargetboundingboxsizecameradatainput) |
| `782D4103` | [CGameSurfaceTrapezoid](#cgamesurfacetrapezoid) |
| `6F0CA389` | [CPendulumJumpMomentumOverride](#cpendulumjumpmomentumoverride) |
| `44D912A5` | [CSplineMotionTimeJumpMomentumOverride](#csplinemotiontimejumpmomentumoverride) |
| `B48588A6` | [COwlEggDrop](#cowleggdrop) |
| `A9D05B27` | [COwlDoubleMegaEgg](#cowldoublemegaegg) |
| `772A651D` | [CPufferFishSwimCharge](#cpufferfishswimcharge) |
| `A6E3C129` | [CHurlPlayerForceField](#churlplayerforcefield) |
| `80ACB657` | [CAnimationGridDriverSeaLionToss](#canimationgriddriversealiontoss) |
| `8E6D260A` | [CPufferFishSpitObjects](#cpufferfishspitobjects) |
| `FE714AC1` | [CAnimGridDriverTrackObject](#canimgriddrivertrackobject) |
| `87F050BC` | [CPlayerModuleGreenBalloonData](#cplayermodulegreenballoondata) |
| `244C1936` | [CRestrictPositionCameraBehaviorData](#crestrictpositioncamerabehaviordata) |
| `E0368B3F` | [CSurfacePositionBehaviorData](#csurfacepositionbehaviordata) |
| `246FCDE4` | [CProjectileMotionWaterCurrent](#cprojectilemotionwatercurrent) |
| `D59638AF` | [CLoopedMotionBehaviorData](#cloopedmotionbehaviordata) |
| `1C8A8B6C` | [CConstantSpeedSplineControl](#cconstantspeedsplinecontrol) |
| `C79BA739` | [CControllerCameraDataInput](#ccontrollercameradatainput) |
| `B9A3AE53` | [CGameSurfaceSphere](#cgamesurfacesphere) |
| `332EAF7B` | [CFOVInputBehaviorData](#cfovinputbehaviordata) |
| `1F4760D7` | [CBarrelCannonOrientationControl](#cbarrelcannonorientationcontrol) |
| `EB22236C` | [CPolarBearRandomAction](#cpolarbearrandomaction) |
| `28C6D69A` | [CResetDetectionCameraBehaviorData](#cresetdetectioncamerabehaviordata) |
| `C2FCDC9B` | [CWarusKingSupportObjectMovementConfiguration](#cwaruskingsupportobjectmovementconfiguration) |
| `91F17031` | [CRenderMethodGameMode](#crendermethodgamemode) |
| `62C17F60` | [CAiNonDamagingSCAHandler](#cainondamagingscahandler) |

## CCircle

## CRectangle

## CMotionSplineControl

## CEulerOrientationSplineControl

## CTargetOrientationSplineControl

## CAdoptSplineOrientationSplineControl

## CAutoDestructTypeLandCounter

## CAutoDestructTypeTimer

## CTargetingData

## CBehaviorAutoDestructData

## CBlinkAnimationData

## CBehaviorBopJumpData

## CBehaviorBopJumpProceduralData

## CBehaviorHitReactionData

## CBehaviorFallData

## CBehaviorFollowDynamicPathData

## CBehaviorFollowPathData

## CBehaviorSeaLionPainguinData

## CBehaviorSeaLionRingData

## CBehaviorStunReactionData

## CBehaviorHurlReactionData

## CBehaviorContactReactionData

## CBehaviorKnockbackReactionData

## CBehaviorSpawnData

## CBehaviorWanderData

## CBehaviorWanderProceduralData

## CCollisionData

## CHealthData

## CBehaviorKnockbackStunReactionData

## CMovementData

## CCreatureRuleSetData

## CDamageTypeRuleSetData

## CFSMData

## CSeaLionControllerData

## CSeaLionRuleSetData

## CSplineTrackerData

## CAnimationControllerData

## CAnimationGridDriverData

## CMovementConfiguration

## CRenderAnimatedModel

## CRenderStaticModel
| Type | Description |
| --- | --- |
| [SLdrRenderStaticModel](structs.md#sldrrenderstaticmodel) | Loader struct |
| NBakedLighting::SDIMScriptData | DIM script data |

## COffsetPositionBehaviorData

## CPrimaryTargetTrackingBehaviorData

## CRenderStaticModelArray

## CTerrainAlignmentData

## CBopJumpSequenceTargetPlayer

## CNormalBopJumpSequence

## CRandomBopJumpSequence

## CSidescrollerTrackingBehaviorData

## CPIDConvergenceData

## CProportionalConvergenceData

## CSpringConvergenceData

## CVelocityConvergenceData

## CSimpleMotionBehaviorData

## CScaleSplineControl

## CHorizontalLeadPositionBehaviorData

## CFrameGroundPositionBehaviorData

## CSidescrollPositionBehaviorData

## CCameraTargetOrientationBehaviorData

## CPathPositionBehaviorData

## CAABoxShapeData

## CSphereShapeData

## CPlayerModuleControllerData

## CPlayerModuleCharacterMovementData

## CPlayerModuleHealthData

## CPlayerModuleSplineAdvancementData

## CPlayerModuleJumpData

## CPlayerModuleTerrainAlignmentData

## CPlayerModuleMountData

## CPlayerModuleSlaveData

## CPlayerModuleTireData

## CPlayerModuleBarrelCannonData

## CPlayerModuleKnockbackData

## CPlayerModuleJumpUpLedgeData

## CPlayerModuleGroundPoundData

## CPlayerModuleRollData

## CPlayerModuleCrouchData

## CPlayerModuleAnimationData

## CPlayerModuleClingData

## CPlayerModuleRocketBarrelData

## CPlayerModuleBasicMovementData

## CProjectileMotionPhysics

## CProjectileMotionHomingMissile

## CProjectileMotionSpline

## CProjectileMotionTargetedPhysics

## CProjectileMotionTargetedSpline

## CProjectileMotionTerrainMovement

## CProjectileMotionWaypointFollower

## CPlayerModulePeanutGunData

## CPlayerModuleStalledDescentData

## CBopJumpNormalJumpTypeData

## CBopJumpPeriodicJumpTypeData

## CBopJumpReactiveJumpTypeData

## CBopJumpNoneDirectionalControlData

## CBopJumpPingPongDirectionalControlData

## CBopJumpRandomDirectionalControlData

## CBopJumpSeekPlayerDirectionalControlData

## CPlayerModuleMineCartData

## CFlyerMovementConfiguration

## CDynamicPullbackBehaviorData

## CPullbackMotionBehaviorData

## CPlayerModuleMeleeData

## CPlayerModuleGrabData

## CPlayerModuleTeleportData

## CPlayerModuleOffscreenIndicatorData

## CPlayerModuleSpecialContactDamageData

## CPlayerModuleActionHintData

## CXYZPositionSplineControl

## COBBoxShapeData

## CBehaviorFlipData

## CBehaviorGrabbedData

## CProjectileCollisionPrimitiveAABox

## CProjectileCollisionPrimitiveModelBounds

## CProjectileCollisionPrimitiveSphere

## CThrownLandingConfiguration

## CPlayerModuleSwingData

## CAdoptCameraStateBehaviorData

## CTargetSelector

## CBehaviorProjectileAttackData

## CBehaviorTargetedWanderData

## CFrameTargetsPositionBehaviorData

## CProjectileAttackActionSequence

## CProjectileAttackActionSequenceRandom

## CProjectileAttackActionFireProjectile

## CProjectileAttackActionPause

## CProjectileAttackWeightedAction

## CPlayerModuleSlideData

## CPlayerModuleMultiKillRewardData

## CPlayerModulePeriodicAdditiveAnimationData

## CBehaviorLinearProjectileData

## CCharacterPrimitivesData

## CTargetSelectorOffScreen

## CPlayerModuleHeadTrackingData

## CBehaviorChangePostureData

## CPlayerModuleSwimmingData

## CWeaponData

## CVerticalLeadPositionBehaviorData

## CPolarBearDelayedSlam

## CPolarBearIcyCharge

## CPolarBearMegaLeap

## CPolarBearSlammerTime

## CSeaLionBellyFlop

## CSeaLionBreach

## CSeaLionHandStand

## CSeaLionLowRoller

## CSeaLionSlipNFlip

## CSeaLionSlipNStop

## CSeaLionTossAttack

## CSeaLionTurboSlide

## CSeaLionWheel

## CWarusKingAvalanche

## CWarusKingBullCharge

## CWarusKingIceStorm

## CWarusKingIcyBlast

## CWarusKingMegaQuake

## CWarusKingRageStomp

## CWarusKingRoyalRumble

## CWarusKingRoyalStomp

## CWarusKingSiegeHorn

## CActorActionPlaylistConditional

## CActorActionPlaylistSequential

## CPlayerModuleFlutterJumpData

## CBehaviorFollowPathProceduralData

## CAnimationMovementConfiguration

## CPlayerModuleZiplineData

## CFollowDynamicPathJump

## CFollowDynamicPathSpline

## CDirectionalForceField

## CProgressiveForceField

## CPlayerModuleRambiControllerData

## CBehaviorExplodeReactionData

## CBehaviorSlaveControllerData

## CFramingEnforcementBehaviorData

## CBehaviorGridAttackData

## CBehaviorFollowSurfaceData

## CPolarBearControllerData

## CPlayerModuleSwimmingBreastStrokeData

## CPlayerModuleSwimmingPropellerData

## CPlayerModuleSwimmingJetBoostData

## CBehaviorMeleeAttackData

## COrientationPathBehaviorData

## CBehaviorPolarBearDelayedSlamData

## CPlayerModuleSwimmingSpinData

## CBehaviorPolarBearMegaLeapData

## CAnimatedCameraBehaviorData

## CBehaviorSwimPathProceduralData

## CPlayerModulePogoStickData

## CTargetSelectorRaycast

## CBehaviorIceCubeData

## CBehaviorPolarBearCubeSlingData

## CPolarBearCubeSling

## CBehaviorKnockbackProceduralData

## CBehaviorSwoopAttackData

## CBehaviorSeekerData

## CBopJumpOnPlayerJumpedJumpTypeData

## COwlControllerData

## COwlSwoop

## COwlEggToss

## COwlMegaEggToss

## COwlFeatherFan

## CSurfaceFollowerMovementConfiguration

## CBehaviorPolarBearIcyRoarData

## CPolarBearIcyRoar

## CStackData

## CFollowerDriverData

## CBehaviorPolarBearIcyChargeData

## CBehaviorDespawnData

## CAlternateDamageInfoData

## CTargetSelectorLinked

## CBehaviorSwimSurfaceData

## CWarusKingControllerData

## CBehaviorPolarBearMegaSlamData

## CPolarBearMegaSlam

## CPlayerModuleRiseFromTheGraveData

## CPositionAtTimeSplineControl

## CWaypointSpeedControl

## CBaboonControllerData

## CTargetedWanderSplineLengthTargeting

## CTargetedWanderTargetSelectorTargeting

## CBaboonVineSwing

## CBaboonMultiRoll

## COwlFeatherBlast

## CBehaviorBreachJumpData

## CBehaviorVolumeTargetingData

## CBehaviorTeleportData

## CBaboonBombToss

## COwlWindStorm

## COwlRockRoll

## CGenericActorSCAHandler

## CPlayerModuleSuperCombinedAbilityData

## CBaboonDropJump

## CPufferFishControllerData

## CPufferFishExhale

## CPufferFishInhale

## COwlFormation

## CBehaviorStationaryData

## CPufferFishBounceAnimDriven

## CPufferFishBounceSeekPlayer

## CPufferFishSwimSeekPlayer

## CBehaviorScriptedOneShotAnimationData

## CPlayerModuleSwimmingStaticSpinData

## CBaboonMultiSwing

## CPufferFishMegaRoll

## CCreatureSCAHandler

## CBaboonBombSwing

## CBaboonRollJump

## COwlBarrelSmash

## CBehaviorGlideJumpData

## CPufferFishWallSlam

## CTransformCameraHintBehaviorData

## CPlayerModuleShieldData

## CPlayerLedgeAvoidanceForce

## CBehaviorSecondaryProjectileAttackData

## CGameSurfacePlane

## CPolarBearSummersaultSlam

## CBehaviorPolarBearSummersaultSlamData

## CSurfaceInputBehaviorData

## CDisplacementFromCameraDataInput

## CDelayDecreaseCameraDataInput

## CTargetBoundingBoxSizeCameraDataInput

## CGameSurfaceTrapezoid

## CPendulumJumpMomentumOverride

## CSplineMotionTimeJumpMomentumOverride

## COwlEggDrop

## COwlDoubleMegaEgg

## CPufferFishSwimCharge

## CHurlPlayerForceField

## CAnimationGridDriverSeaLionToss

## CPufferFishSpitObjects

## CAnimGridDriverTrackObject

## CPlayerModuleGreenBalloonData

## CRestrictPositionCameraBehaviorData

## CSurfacePositionBehaviorData

## CProjectileMotionWaterCurrent

## CLoopedMotionBehaviorData

## CConstantSpeedSplineControl

## CControllerCameraDataInput

## CGameSurfaceSphere

## CFOVInputBehaviorData

## CBarrelCannonOrientationControl

## CPolarBearRandomAction

## CResetDetectionCameraBehaviorData

## CWarusKingSupportObjectMovementConfiguration

## CRenderMethodGameMode

## CAiNonDamagingSCAHandler

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CAssetHeader]: types.md#cassetheader
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CGuid]: types.md#cguid
[CAABox]: types.md#caabox
[CVector3f]: types.md#cvector3f
[Property]: #property-format