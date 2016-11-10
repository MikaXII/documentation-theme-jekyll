---
layout: page
title: Clone your SD card (EN)
wikiPageName: Clone-your-SD-card-(EN)
menu: wiki
---

**To clone** your SD card and have a full backup of your recalbox you can use this softwares :

- **Windows** : [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/) with the READ function
- **MacOS x** : ApplePi-Baker
- **Linux** : use the DD command in terminal (more information below)

<br>
Plug you SD card to your computer using linux.
Determine which device is your SD card :

`sudo fdisk -l`

Once in your backup directory, extract and compress your SD card with this command:

`sudo dd if=/dev/sdX | gzip -9 > ./recalbox-20150411-sdb.img.gz`   
(the letter X should be replaced by the letter determined in the first step)
<br>
<br>
<br>
**To restore** your backup, plug your SD card formated in FAT32 in your PC and use this command ::

`gunzip ./recalbox-20150411-sdb.img.gz | sudo dd of=/dev/sdX`   
(where /dev/sdX is you SD card)
