---
layout: page
title: Recalbox development   basics (EN)
wikiPageName: Recalbox-development---basics-(EN)
menu: wiki
---

# Introduction
You want to contribute to Recalbox ?

Find here the basis to know to understand how to compile sources, how sources are organized, how to send your patches.
Recalbox is based on a tool made to build linux distribution from scratch : Buildroot.

There are about 300 projects composing Recalbox : Linux, Retroarch, Kodi, openssl, nano, nodejs, lirc, ffmpeg, and the list continues.
The Recalbox project is mainly a way to describe how to download, configure and compile each of these programs (most of the job is done by the Buildroot project), and to add an overlay around that to tell what to start at the boot, etc.

# Recalbox main projects base
## EmulationStation (es)
EmulationStation is the main Recalbox user interface. It displays all available games available on your Recalbox, allows to configure your Recalbox.

## Retroarch and other Emulators
When you start a game in Recalbox, it starts an emulator. For example, Retroarch for the Super Nintendo. There are some other emulators for systems not supported by Retroarch or with less performances : Mupen64 (Nintendo64), Reicast (Dreamcast), Moonlight (streaming games from a pc)...

## Configgen
Configgen is a tool made for the Recalbox distribution. When you have a gamepad that is not supported by the Recalbox, you configure it one time in EmulationStation. When you start a game, configgen does the work to configure the configuration file of the emulator according to your pad. Configgen does more, but it's the main visible part.
When you start a game from es, es calls configgen that calls the emulator.

## Kodi
Kodi is a media center.

# Get and compile sources
## Requirements
To work on the Recalbox project, you need a linux box, generally, Ubuntu is used.

## Get sources and compile

### Classic method

At the time of this writting, the Recalbox current development version is 4.1. Use git branch to list branches to work on the most recent branch.

The lines above compile for the rpi2, but you can change it and get the list of available configs in configs/recalbox-*

```
sudo apt-get install build-essential git libncurses5-dev qt5-default qttools5-dev-tools mercurial libdbus-glib-1-dev texinfo zip default-jre imagemagick
git clone https://github.com/recalbox/recalbox-buildroot.git
cd recalbox-buildroot
git checkout origin/rb-4.1.X
make recalbox-rpi2_defconfig
make # takes between 3 and 5 hours
```

### With docker
You can also download and work with the [official docker image](https://github.com/recalbox/recalbox-docker-build)

## Install your sources on an sd card
The result in an image in output/images/recalbox.img that you can copy using :
```
sudo dd if=output/images/recalbox/recalbox.img of=/dev/mmcblk0 bs=40M
```
If you build for rpi, you can build the sd card manually : start gparted, remove all partitions, and create 2 partitions : 1st partition is FAT32, 60M ; 2nd partition is ext4, 1.2G ; let the rest of the sd card empty.
Then, untar output/images/recalbox/boot.tar.xz on the 1st partition and output/images/recalbox/root.tar.xz on the 2nd one.

## Recalbox partitions
Recalbox uses 3 partitions.
* The first one is fat32 and is used for the boot, read only.
* The second is ext4 and is used for the system, read only.
* The third partition is created automatically on first Recalbox boot. It is ext4 and is used for user data.

# Source organisation

## configs
This directory contains one file by image to build :
  - recalbox-odroidxu4_defconfig for the Odroid XU4 build
  - recalbox-rpi1_defconfig for the Raspberry1 build
and so on.

To build one target, you do : make recalbox-rpi1 (without_defconfig)

Each file is a text file and contains the specificities of the build.
For example BR2_PACKAGE_RETROARCH=y if your build include the retroarch package.

## packages
The package directory contains one directory by package.
For example, the package retroarch.
Each package contains at least 2 files : <package>.mk and Config.in
and is referenced in packages/Config.in

The file Config.in describes the packages and how to select it in buildroot (description, requirements)

The file <package>.mk describes how to build the package (download, extract, configure, make, make install steps)

## output/build
This directory contains the downloaded sources. One by package to build.
You can run make source to download all the sources without building.

## output/build
This directory contains one directory by built package.
It contains extracted sources and compiled files.

Just remove one built package directory and rerun make to rebuild the package.


