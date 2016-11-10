---
layout: page
title: recalboxOS detailed (EN)
wikiPageName: recalboxOS-detailed-(EN)
menu: wiki
---

**recalboxOS** is an open source operating system. It's a linux based distribution, optimized for the ARM processor of the RaspberryPI.

## Buildroot
**recalboxOS** is compiled with buildroot.

Buildroot is a simple, efficient and easy-to-use tool to generate embedded Linux systems through cross-compilation. It compiles all recalboxOS system and software from source, and creates the archives that will be copied to your SD file at the installation.

It creates a minimal embedded linux system, corresponding exactly to what is needed on your system.
This is why you have no package manager on recalboxOS, no compilator, no headers etc...

## Projects
**recalboxOS** is the main project, that aggregates the sub-projects composing of the system :

- **recalbox-buildroot** :
https://github.com/digitalLumberjack/recalbox-buildroot (branch unified)
The recalbox-buildroot project is the buildroot system. It create the whole linux os that will run on the recalbox.
You can compile this project, then copy output files to a manually formatted SD card to run the system on a raspberryPi. But there is a better way, called recalbox-rescue.

- **recalbox-rescue** :
https://github.com/digitalLumberjack/recalbox-rescue (branch dual)
Based on the awesome NOOBS distro from rpi team, the recalbox rescue allows you to easily install recalboxOS and have a rescue partition on your SD card. It's another minimal OS, that will download recalboxOS, format your SD card, and install the system for you.
It will check if a new version is available from the net before installing SD card version. 

- **recalbox-emulationstation** :
https://github.com/digitalLumberjack/recalbox-emulationstation/tree/recalbox-buildroot
Based on the awesome Aloshi emulationstation 2, the frontend has been a little modified to have ogg bg music, language selection, update support and controller configuration.

- **recalbox-configgen** :
https://github.com/digitalLumberjack/recalbox-configgen
The automatic emulator configuration tool.

If you want to go deeper, and learn how to compile and modify recalboxOS, jump to [[Compilation & Modifications|Compilation-&-Modifications-(EN)]]

## Partitions
The recalboxOS is set up to run on 3 partitions :
- The first partition of type FAT32, named BOOT, mounted on /boot on the system, contains all boot files
- The second partition of type EXT4, named root, mounted on / on the system, contains all the system
- The third partition of type FAT32, named SHARE, mounted on /recalbox/share on the system, contains all roms, bios, saves and screenshots.

## User directory
User data is explained here : [[Customizing-System-directory-(EN)]]
