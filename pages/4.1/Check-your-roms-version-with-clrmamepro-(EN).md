---
layout: page
title: Check your roms version with clrmamepro (EN)
wikiPageName: Check-your-roms-version-with-clrmamepro-(EN)
menu: wiki
---

piFBA, libretro_fba, iMame4all and Mame2003 accept all different roms versions.

In order to know if your roms are compatible, you can use clrmamepro. 

This software will use a .dat file that contains roms informations for a given version, and check if your roms correspond. It uses crc on all files in .zip archives, and will tell you what are missing or not corresponding files.

First get the .dat file corresponding the emulator you want to use :
[wiki Add-arcade-games](https://github.com/recalbox/recalbox-os/wiki/Add-arcade-games-%28EN%29)

Then download and install clrmamepro at [mamedev.emulab.it/clrmamepro/](http://mamedev.emulab.it/clrmamepro/) (works in wine) and load your .dat file in the **Profiler** section.

Go in **Settings** and set the rom path to your roms directory.

Finally, use the **Scanner** to scan your roms directory, and check the logs to see missing files.

> You can find good steep by steep tutorial on google or on youtube if you want.
