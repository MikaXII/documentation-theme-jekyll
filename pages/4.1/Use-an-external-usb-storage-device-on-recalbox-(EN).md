---
layout: page
title: Use an external usb storage device on recalbox (EN)
wikiPageName: Use-an-external-usb-storage-device-on-recalbox-(EN)
menu: wiki
---

You can easily use an external USB storage device to stock your roms, user data etc...

# Introduction
* First you must use a storage device (usb key, HDD with its own external power supply etc...) using one of these file system : **FAT32** , EXT4 or NTFS (the transfer rates may be low on NTS). 
Be sure to use a file system compatible with your PC's OS.
_**The system won't format your device, only create new files on it.**_

# Optionnal : Sync your USB key with your SD
Recalbox can manually synchronize your USB key with your SD. This step is optional but must be done before setting your storage device to your USB key. Here are the steps :

1. Start your Recalbox
2. Plugin the USB key whenever you want
3. SSH to your pi, or open a terminal on it
4. `cd /recalbox/scripts`
5. `./recalbox-sync.sh list` will show the available devices. For example :
```
# ./recalbox-sync.sh list
INTERNAL
DEV A80A-27A5 NO_NAME
```
So my USB key 's name is NO_NAME, it's device id is A80A-27A5. Now i can sync it
6. 
```
# ./recalbox-sync.sh sync A80A-27A5
sending incremental file list
./
.keep
bios/
bios/lisez-moi.txt
bios/readme.txt

...


sent 111,817,693 bytes  received 8,256 bytes  9,723,995.57 bytes/sec
total size is 111,758,686  speedup is 1.00
rsync error: some files/attrs were not transferred (see previous errors) (code 23) at main.c(1178) [sender=3.1.2]
```
You're done ! Don't worry about the errors ! Now your USB key is the copy of your data from your SD. You can go on with the next part

# Setup Recalbox to use your USB key
* Plug your USB device to your recalbox, then power on your recalbox. Once on the recalbox's frontend, press the **start button** to open the options menu, go to **system settings** and **storage device list**. Now, select your USB device in this list. The system will now reboot after the choice done.
During this reboot, recalboxOS will create on your USB device, a new folder called `recalbox` which will contain the `/share` partition of your recalbox.

* So to add your roms files, user data (save games, scrapes data, bios files etc...), you have to poweroff your recalbox. Then unplug your USB device from it, and plug it on your PC.
Now you have just to copy/paste all your file directly from your from computer to your USB device without using your local network to transfer files.
Once done, replug your USB device to your recalbox, power it on, and play.

With this method, system (on SD card) and share (on USB device) partitions are separated.
So if you have to reinstall your system, you'll keep your user data. You'll have just to select your USB device in the recalbox, and your recalbox will be ready to play.

