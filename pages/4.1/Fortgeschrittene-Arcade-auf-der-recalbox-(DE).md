---
layout: page
title: Fortgeschrittene Arcade auf der recalbox (DE)
wikiPageName: Fortgeschrittene-Arcade-auf-der-recalbox-(DE)
menu: wiki
---

Diese Seite ist eine Weiterführung des Artikels [[Einfache Arcade auf der recalbox|Einfache-Arcade-auf-der-recalbox-(DE)]]

## BestArcade4Recalbox 

Hier findest du eine Liste von den wichtigsten MAME – Spielen und ihrem Funktionsstatus auf MAME und FBA_libretro:
[BestArcade4Recalbox-3.3.0b16_v1.1] (https://docs.google.com/spreadsheets/d/1F5tBguhRxpj1AQcnDWF6AVSx4av_Gm3cDQedQB7IECk/edit#gid=131171669&vpid=A179)

## ClrMamePro

Um die eigenen ROMs zu verifizieren, kann ClrMamePro benutzt werden: [[Anleitung zu clrmamepro|Prüfen-von-ROM-Versionen-mit-clrmamepro-(DE)]]

## Alle Arcade Systeme auf der **_recalbox_**

In der neuesten Version von **_recalbox_** stehen 4 verschiedene Systeme (MAME, imame4all, piFBA, FBA libretro) sowie das "Fake" System NeoGeo zur Verfügung. Das System, das benutzt werden soll, kann ausgewählt werden in [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29)

#### piFBA
**_recalbox_** _(alle Versionen)_
* piFBA ist der am besten optimierte FBA – Emulator in **_recalbox_**.  
* Benutzte FBA ROM - Set Version: **FBA 0.2.96.71** welche auf MAME 0.114 (April 2007) basiert.
 * Grösse: 3.62GB
 * Emulierte ROM - Sets: 684 (Keine Klon – ROMs enthalten)
* _Ordner für die ROMs:_ fba
*    Eine Liste aller kompatiblen Spiele für deine **_recalbox_** kannst du finden unter [/recalbox/share/roms/fba/clrmamepro/piFBA_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba/clrmamepro/piFBA_gamelist.txt)
*    Die .dat - Datei mit den ROM Checksummen der Spiele für ClrMamePro findest du hier: [/recalbox/share/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat)

#### imame4all
**_recalbox_** _(alle Versionen)_
* imame4all wird für ältere Spiele empfohlen, welche nicht mit piFBA funktionieren.
* Benutzte MAME ROM – Set Version: **0.37b5** (Juli 2000)
 * Grösse: 1.86GB
 * Emulierte ROM - Sets: 2 270 (beinhaltet Klone, etc...)
 * Aktive Sets 2241/2241
 * Urheber ROMs 560/560
 * Klon ROMs 990/990
 * Andere 690/690
 * BIOS 1/1
 * (Falls ein Spiel nicht funktioniert mit dem ROM - Set 0.37b5, versuche es mit der MAME Version 0.81)
* _Ordner für die ROMs:_ mame
* Eine Liste aller kompatiblen Spiele für deine **_recalbox_** kannst du finden unter [/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all_gamelist.txt)
* Die .dat - Datei mit den ROM Checksummen der Spiele für ClrMamePro findest du hier: [/recalbox/share/roms/mame/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all.dat)

#### lr-mame2003
**_recalbox_** _(seit v3.3.0-beta-11)_
* lr-mame2003 ist der aktuellere MAME Emulator als imame4all. Auf diesem funktionieren mehr Spiele, ist aber nur auf dem Raspberry Pi 2 verfügbar.
* Benutzte MAME ROM – Set Version: **0.78** (Dezember 2003)
 * Grösse: 8.09GB
 * Emulierte ROM - Sets: 4 705 (beinhaltet Klone, etc...)
 * Aktive Sets 4705/4705
 * Urheber ROMs 1042/1042
 * Klon ROMs 2039/2039
 * Andere 1624/1624
 * BIOS 1/1
* _Ordner für die ROMs:_ mame
* Eine Liste aller kompatiblen Spiele für deine **_recalbox_** kannst du finden unter _(Bald verfügbar)_
* Die .dat - Datei mit den ROM Checksummen der Spiele für ClrMamePro findest du hier: [/recalbox/recalbox-os/master/wiki/dat/mame2003.dat](https://raw.githubusercontent.com/recalbox/recalbox-os/master/wiki/dat/mame2003.dat)

#### libretro FBA  
*  libretro FBA ist eine libretro Version von FBA. Auf diesem funktionieren ebenfalls mehr Spiele, ist aber nur auf dem Raspberry Pi 2 verfügbar. Es ist zum Beispiel die einzige Version auf der capcom funktioniert. [CP System III] (https://en.wikipedia.org/wiki/CP_System_III#List_of_games) Spiele.

**_recalbox_** _(v3.2.11)_
* Benutzte MAME ROM – Set Version: **FBA 0.2.97.30** welche auf MAME 0.154 (Juli 2014) basiert.
 * Grösse: 9.15GB
 * Emulierte ROM - Sets: 3 369 (beinhaltet Klone, etc...)
 * Aktive Sets 3369/3369
 * Urheber ROMs 710/710
 * Klon ROMs 2146/2146
 * Andere 508/508
 * BIOS 5/5  
* _Ordner für die ROMs:_ fba_libretro
* Eine Liste aller kompatiblen Spiele für deine **_recalbox_** kannst du finden unter [/recalbox/board/recalbox/share/roms/fba_libretro/fba_libretro_gamelist.txt](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba_libretro/fba_libretro_gamelist.txt)
* Die .dat - Datei mit den ROM Checksummen der Spiele für ClrMamePro findest du hier: [/recalbox/share/roms/fba_libretro/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-buildroot/recalbox/board/recalbox/share/roms/fba_libretro/clrmamepro/fbalibretro.dat)

**_recalbox_** _(v3.3.0-b7 bis v3.3.0-b14)_
* Benutzte FBA ROM – Set Version: **FBA 0.2.97.36** welche auf MAME 0.161(April 2015) basiert.
 * Emulierte ROM - Sets: 3 743 (beinhaltet Klone, etc...)
 * Aktive Sets 3743/3743
 * Urheber ROMs 802/802
 * Klon ROMs 2408/2408
 * Andere 533/533
 * BIOS 6/6  

**_recalbox_** _(seit v3.3.0-b15)_
* Benutzte FBA ROM – Set Version: **FBA 0.2.97.37** welche auf MAME 0.167(November 2015) basiert.
* Du findest das Änderungsprotokoll hier: [fbalpha Changelog](http://www.fbalpha.com/view/227/)
* Eine Liste aller kompatiblen Spiele für deine **_recalbox_** kannst du finden unter [/libretro/libretro-fba/blob/master/gamelist.txt](https://github.com/libretro/libretro-fba/blob/master/gamelist.txt)
* Die .dat - Datei mit den ROM Checksummen der Spiele für ClrMamePro findest du hier: [/recalbox/recalbox-os/master/wiki/dat/fba_0.2.97.37.dat](https://raw.githubusercontent.com/recalbox/recalbox-os/master/wiki/dat/fba_0.2.97.37.dat)

#### NeoGeo System    
Das NeoGeo System ist im eigentlichen Sinn kein eigener Emulator. Um das System zu benutzen muss der Kern in [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29) bearbeitet werden. Dies erlaubt es dir, die NeoGeo - Spiele visuell von den anderen Arcade – Spielen zu unterscheiden. Sie erscheinen als ein dediziertes System im EmulationStation Frontend.
