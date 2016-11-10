---
layout: page
title: Setup a dual boot raspbian recalboxOS (EN)
wikiPageName: Setup-a-dual-boot-raspbian-recalboxOS-(EN)
menu: wiki
---

Zhitom has shared his experience creating a dualboot Raspbian and Recalbox-OS with Noobs

1. Download Noobs « Offline and network install » (contain the latest Raspbian version) at the following adress : https://www.raspberrypi.org/downloads/

2. Unzip the zip archive and copy all the files at the root of the SD card formated with the SDFormatter software :
   https://www.sdcard.org/downloads/formatter_4/eula_windows/SDFormatterv4.zip

3. Download the latest Recalbox version at the following adress:
   https://github.com/digitalLumberjack/recalbox-os/releases/latest

4. Unzip the archive and copy the folder "recalboxOS-rpi2" ( or "recalboxOS" depending on the version ) located in the folder "os" to copy it in the folder "os" at the root of the SD card.

5. The SD card is ready, you only have to insert it in the Raspberry !

6. At the first boot, after the splashscreen, a window will appear with multiples OS to choose. Check Raspbian and Recalbox then click to "Install" or type i.
   Just wait a dozen minutes for the end of the installation.

7. At the reboot, after the splashscreen, a new window will appear with the choice of the OS to start with. Choose Raspbian or Recalbox and you are done !

By default, timing screen for the OS selection is 10 seconds, after, the system will start the previously os launched.

_For information : When you do a dual boot raspbian/recalbox with a 16Go µsd card, the free space is allocated by defaut like this :  4,1go for raspbian and 3go for recalbox._
