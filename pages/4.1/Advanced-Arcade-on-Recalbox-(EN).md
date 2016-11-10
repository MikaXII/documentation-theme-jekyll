---
layout: page
title: Advanced Arcade on Recalbox (EN)
wikiPageName: Advanced-Arcade-on-Recalbox-(EN)
menu: wiki
---

This page is the follow-up to [[Easy Arcade on Recalbox|Easy Arcade on Recalbox (EN)]]

## BestArcade4Recalbox 

You can find here a list of the most important mame games and their working status on mame and fba_libretro :
[BestArcade4Recalbox-3.3.0b16_v1.1](https://docs.google.com/spreadsheets/d/1F5tBguhRxpj1AQcnDWF6AVSx4av_Gm3cDQedQB7IECk/edit#gid=131171669&vpid=A179)

## ClrMamePro

In order to verify the roms your have, you can use clrmamepro, and use the [[clrmamepro tutorial|Check-your-roms-version-with-clrmamepro-(EN)]]

## All the arcade systems on the Recalbox

> You have now access to up to 4 systems in last version of Recalbox (mame, imame4all, piFba, fba libretro) and one "fake" system Neogeo. You can chose the core you want to use in [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29)

#### piFBA
_Recalbox (all versions)_
* piFBA is the most optimized FBA emulator on recalbox.  
* It uses the FBA romset version : **FBA 0.2.96.71** which is based on MAME 0.114 (April 2007)
 * Size : 3.62GB
 * Romsets emulated : 684 (no clones in this)
* _roms folder :_ fba
*    You can find the list of compatible games in your recalbox at [/recalbox/share/roms/fba/clrmamepro/piFBA_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba/clrmamepro/piFBA_gamelist.txt)
*    You can find the .dat file with rom checksum for clrmamepro at [/recalbox/share/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat)

#### imame4all
_Recalbox (all versions)_
* imame4all is recommended for older games that does not run in piFBA
* It uses the mame romset version : **0.37b5** (July 2000)
 * Size : 1.86GB
 * Romsets emulated : 2 270 (includes clones etc...)
 * Active Sets 2241/2241
 * ·Parents 560/560
 * ·Clones 990/990
 * ·Others 690/690
 * ·BIOS 1/1
 * _(If one game doesn't work on romset 0.37b5, you can try the romset mame 0.81 version)_
* _roms folder :_ mame
* You can find the list of compatible games in your recalbox at  [/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all_gamelist.txt)
* You can find the .dat file with rom checksum for clrmamepro at [/recalbox/share/roms/mame/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all.dat)

#### lr-mame2003
_Recalbox (since v3.3.0-beta-11)_
* lr-mame2003 is more recent mame emulator than imame4all. It brings new games compatibility and is only available on RPI2
* It uses the mame romset version : **0.78** (December 2003)
 * Size : 8.09GB
 * Romsets emulated : 4 705 (includes clones etc...)
 * Active Sets 4705/4705
 * ·Parents 1042/1042
 * ·Clones 2039/2039
 * ·Others 1624/1624
 * ·BIOS 1/1
* _roms folder :_ mame
* You can find the list of compatible games in your recalbox at _(coming soon)_
* You can find the .dat file with rom checksum for clrmamepro at [/recalbox/recalbox-os/master/wiki/dat/mame2003.dat](https://raw.githubusercontent.com/recalbox/recalbox-os/master/wiki/dat/mame2003.dat)

#### libretro FBA  
*  libretro FBA is a libretro version of FBA. It brings new games compatibility and is only available on RPI2. For exemple, it's the only one can lauch capcom [CPSIII](https://en.wikipedia.org/wiki/CP_System_III#List_of_games) games.

_Recalbox (v3.2.11)_
* It uses the FBA romset version : *FBA 0.2.97.30** which is based on MAME 0.154 (Jul 2014)
 * Size : 9.15GB
 * Romsets emulated : 3 369 (includes clones etc...)
 * Active Sets 3369/3369
 * ·Parents 710/710
 * ·Clones 2146/2146
 * ·Others 508/508
 * ·BIOS 5/5  
* _roms folder :_ fba_libretro
* You can find the list of compatible games in your recalbox at  [/recalbox/board/recalbox/share/roms/fba_libretro/fba_libretro_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba_libretro/fba_libretro_gamelist.txt)
* You can find the .dat file with rom checksum for clrmamepro at [/recalbox/share/roms/fba_libretro/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba_libretro/clrmamepro/fbalibretro.dat)

_Recalbox (v3.3.0-b7 to v3.3.0-b14)_
* It uses the FBA romset version : *FBA 0.2.97.36* which is based on MAME 0.161(April 2015)
 * Romsets emulated : 3 743 (includes clones etc...)
 * Active Sets 3743/3743
 * ·Parents 802/802
 * ·Clones 2408/2408
 * ·Others 533/533
 * ·BIOS 6/6  

_Recalbox (since v3.3.0-b15)_
* It uses the FBA romset version : *FBA 0.2.97.37* which is based on MAME 0.167(November 2015)
* You can find the changelog at [fbalpha changelog](http://www.fbalpha.com/view/227/)
* You can find the list of compatible games in your recalbox at [/libretro/libretro-fba/blob/master/gamelist.txt](https://github.com/libretro/libretro-fba/blob/master/gamelist.txt)
* You can find the .dat file with rom checksum for clrmamepro at [/recalbox/recalbox-os/master/wiki/dat/fba_0.2.97.37.dat](https://raw.githubusercontent.com/recalbox/recalbox-os/master/wiki/dat/fba_0.2.97.37.dat)


##### Neogeo system    
The Neogeo  system is not an emulator itself. You need to configure the core to use in [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29). This will allow you to visually separate the NeoGeo games from the other arcade games, they will appear as a dedicated system in Emulation Station
