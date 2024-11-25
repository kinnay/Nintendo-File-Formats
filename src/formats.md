# File Formats

## Misc
The BYAML file format has been seen in various game engines, including AL, LunchPack and ModuleSystem.

* [BYAML files (binary yaml)](libs/common/byaml.md)

## AAL
This is a first-party audio framework that uses [nw::snd / nn::atk](#nw) internally.

* [BARSLIST files (audio resource lists)](libs/aal/barslist.md)
* [BARS files (audio resources)](libs/aal/bars.md)
* [BAMETA files (audio metadata)](libs/aal/bameta.md)
* [BAATN files (audio attenuators)](libs/aal/baatn.md)
* [BAROC files (roll off curves)](libs/aal/baroc.md)
* [BACTC files (custom curves)](libs/aal/bactc.md)
* [BAUDC files (unit distance curves)](libs/aal/baudc.md)
* [BAACL files (attenuation culling)](libs/aal/baacl.md)
* [BAGST files (audio group settings)](libs/aal/bagst.md)
* [BLAL files (loop asset list)](libs/aal/blal.md)
* [BWAV files (wave sounds)](libs/aal/bwav.md)

## AGL
This is a first-party library that mostly deals with shaders and textures.
* [PMAA files (graphics parameters)](libs/agl/pmaa.md)
* [SHARCFB files (binary shader archives)](libs/agl/sharcfb.md)
* SHARC files (shader archives)

The PMAA file format covers many different extensions such as `.baglenv` and `.bagldof`.

## GFD
This is a tiny Wii U library that loads textures and shaders from gtx/gsh files.
* [Gfx2 files (shaders and textures)](libs/gfd/gfx2.md)

## LMS
LibMessageStudio is a tiny library that loads message files.
* [Overview](libs/lms/overview.md)
* [MSBT files (messages)](libs/lms/msbt.md)
* [MSBP files (projects)](libs/lms/msbp.md)
* [MSBF files (flow charts)](libs/lms/msbf.md)

## NW
NintendoWare is a middleware library for audio, ui, and model rendering.

`nw::eft` / `nn::vfx`:
* [PTCL files (particle effects)](libs/nw/ptcl.md)

`nw::g3d` / `nn::g3d`:
* [BFRES files (model archives)](libs/nw/bfres.md)

`nw::lyt` / `nn::ui2d`:
* [BFFNT files (fonts)](libs/nw/bffnt.md)
* BFLYT files (layouts) 
* [BFLIM files (layout images)](libs/nw/bflim.md)
* BFLAN files (layout animations) 

`nw::snd` / `nn::atk`:
* [Overview](libs/nw/sound.md)
* [BFSAR files (sound archives)](libs/nw/bfsar.md)
* [BFGRP files (sound groups)](libs/nw/bfgrp.md)
* [BFBNK files (instrument banks)](libs/nw/bfbnk.md)
* [BFWAR files (wave archives)](libs/nw/bfwar.md)
* [BFWAV files (wave files)](libs/nw/bfwav.md)
* [BFWSD files (wave sounds)](libs/nw/bfwsd.md)
* [BFSEQ files (sequence sounds)](libs/nw/bfseq.md)
* [BFSTM files (stream sounds)](libs/nw/bfstm.md)
* [BFSTP files (stream sound prefetch)](libs/nw/bfstp.md)

`nn::bezel`:
* [BEA files (bezel archives)](libs/nw/bea.md)

## SEAD
This is Nintendo's private standard library. This library is used by many first-party games like Mario and Splatoon, and most other first-party libraries (like [AAL](#aal)) use this library internally as well.

* [SARC files (archives)](libs/sead/sarc.md)
* [SZS files (yaz0 compression)](libs/sead/yaz0.md)

## XLINK
ELINK and SLINK were first-party libraries that control particle and sound effects respectively. Later, these libraries were merged into a single library called XLINK.

The libraries use [AAL](#aal) and [nw::eft / nn::vfx](#nw) internally.

* [ELINK files (effect links)](libs/xlink/elink.md)
* [SLINK files (sound links)](libs/xlink/slink.md)
* [XLINK files (sound / effect links)](libs/xlink/xlink.md)

XLINK files have the file extension `.bslnk` or `.belnk`.

## Animal Crossing: New Horizons {#acnh}
* [BCSV files](games/acnh/bcsv.md)

## Donkey Kong Country: Tropical Freeze (Wii U) {#dkctf}
* [PAK files (archives)](games/dkctf/pak.md)
* [ROOM files (game areas)](games/dkctf/room.md)
* [CMDL files (models)](games/dkctf/model.md)
* [SMDL files (skinned models)](games/dkctf/model.md)
* [WMDL files (world models)](games/dkctf/model.md)
* [CHAR files (characters)](games/dkctf/char.md)
* [TXTR files (textures)](games/dkctf/txtr.md)
* [MTRL files (materials)](games/dkctf/mtrl.md)
* [LDTA files (loose data)](games/dkctf/ldta.md)
* [Super guide / replay files](games/dkctf/replay.md)

## Mario Kart 8 (Wii U) {#mk8}
* [Replay files](games/mk8/replay.md)
* BSIS files (random audio id set)

## New Super Mario Bros. U {#nsmbu}
* [Level files](games/nsmbu/level.md)
* [Tileset files](games/nsmbu/tileset.md)
* [Save data (rp_savedata.dat)](games/nsmbu/savedata.md)

## Super Mario Maker 2 {#smm2}
* [Level files](games/smm2/level.md)
* [Ninji ghost files](games/smm2/ghost.md)

## SNES - Nintendo Switch Online {#snes-nso}
* [ROM files](games/snes-nso/rom.md)
* [Break files](games/snes-nso/break.md)
