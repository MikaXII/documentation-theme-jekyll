---
layout: page
title: Home (EN)
wikiPageName: Home-(EN)
menu: wiki
---

# Welcome to the recalbox-os wiki!

## Introduction
**recalboxOS** is the operating system of the recalbox project, an out-of-the-box emulation console based on the Raspberry Pi. See http://www.recalbox.com for more information.

**recalboxOS** uses many awesome existing components, like [EmulationStation2](https://github.com/Aloshi/EmulationStation) as frontend, [piFBA](https://github.com/digitalLumberjack/pifba) and [Retroarch](https://github.com/libretro/RetroArch) as emulators, [RaspberryPI NOOBS](https://github.com/raspberrypi/noobs) as installation/recovery system.

**recalboxOS** can be resumed to a single word : EASY. We want to provide a very user friendly system. No file configuration, no ssh terminal. Install and play.  
But we also provide an all in one configuration file, named [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29) , that provides fine configuration of all emulators !

### FEATURES ###

- Supports Atari 2600, Atari 7800, NES, Game Boy, Game Boy color, Game Boy Advance, Super Nintendo, Famicom Disk System, Master System, Megadrive (Genesis), Gamegear, Game and Watch, Lynx, NeoGeo, NeoGeo Pocket, FBA (subset), iMame4all (subset), PCEngine, Supergrafx, Amstrad CPC, MSX1/2, ZX Spectrum, PSX, Sega Cd, Sega 32X, Sega SG1000, Playstation, ScummVM, Vectrex, VirtualBoy, Wonderswan
- Build with buildroot, so the root file system is only 150MB compressed.
- Rescue system based on NOOBS : reinstall directly from your SD card or get the last version from the web
- Wifi support
- Online update
- Network access to ROM folder, screenshots, saves, configuration file (via SAMBA and HTTP-Webfrontend)
- Controller configuration in the frontend: configure once, play everywhere
- Built-in controller support for PS3, Xbox360, 8BitDo and Bluetooth (associate a controller and play)
- Packaged GPIO drivers, for arcade controls, or original Nes, Snes, Megadrive, PSX controllers, XinMo 2 players
- [Miroof's Virtual Gamepad](https://github.com/miroof/node-virtual-gamepads) support (use your phone as a controller)
- Frontend based on the great EmulationStation2 by Aloshi
- Background frontend music
- Favorites feature (mark your games as favorites and hide others)
- English, French, Spanish, German, Italian and Portugues, maybe other to come if you participate
- FBA optimized version with 4 player support

Next : [[Installation|Installation-(EN)]]
