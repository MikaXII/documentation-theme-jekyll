---
layout: page
title: Installation (EN)
wikiPageName: Installation-(EN)
menu: wiki
---

# Simple way with Noobs (rpi only)

You can install the recalboxOS on a fat32 formatted sd card.  
**You must use at least a 8GB micro sd card, and we recommend the Sandisk Ultra series.**  

Use a card formater software from https://www.sdcard.org/downloads/formatter_4/ on Windows and MacOSX, or gparted on linux.

* Start the **SDCard formatter** program and format the whole card in _**FAT32**_.   
   
 * _For information : if you are using a 64Go SDCard, your formater software may force format in exFAT.   
So if you have this problem, you can try [minitool partition wizard ](http://www.partitionwizard.com/free-partition-manager.html) or [guiformat](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) (windows only)_

* Download recalboxOS.zip from the last recalboxOS release at https://github.com/digitalLumberjack/recalbox-os/releases

* Now unzip the _**recalboxOS.zip**_ file directly at the root of your SD card. Delete the zip file in case you copied it to the SD card!

* Put the card in your Raspberry Pi, plug in the hdmi and the power supply.

* The installation starts, **you'll have a recalbox in 5 minutes** ! 

At the end of the install, the Emulationstation screen will show up, and you will have the pleasure to listen to the awesome Zelda theme !

If you are on a RPi 1 model B or B+, you should **really** overclock your RPi to have best performance possible. Go in the **System Setting** menu and change your overclock settings.    
I strongly recommend the highest overclock, "*EXTREM*" setting on all my RPi1, which may void your warranty but is unbelievably smoother in games than any other configuration.

# Burn on a sdcard or an usb key from an image file
1) Download http://recalbox.remix.free.fr/bin/Win32DiskImager-0.9.5-binary.zip

2) Download an image on http://recalbox.remix.free.fr

3) unzip Win32DiskImager-0.9.5-binary.zip and run Win32DiskImager.exe

4) Extract recalbox.img.gz (gz is like zip, ie it's a compressed file)

**Warning** : some browsers like Opera/Safari take the liberty to unzip the file by themself and badly rename them. If the file is more than 1GB, it is already unzipped.

5) Insert a usb key or a sdcard on your computer

6) Select the image and the drive in Win32DiskImager.exe like on the following screenshot and click on Write

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/burn/Win32DiskImager.png)

7) Once finished, go on your usb key/sdcard and check that it looks like this :

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/burn/burn_drive.png)

Next : read the [[Manual|Manual-(EN)]] and the [[Mini How-To|Mini-How-To-(EN)]] 
