---
layout: page
title: Copy roms from a Computer to the SD Card using an USB Stick (or External Hard Drive) (EN)
wikiPageName: Copy-roms-from-a-Computer-to-the-SD-Card-using-an-USB-Stick-(or-External-Hard-Drive)-(EN)
menu: wiki
---

If your OS doesn't allow you to directly copy your roms to your SD Card, you can copy them first from your Computer to an USB Stick and then do the same from the USB Stick to your SD Card running RecalboxOS.

To do this, follow this steps:

1. Format your USB Stick to FAT32, NTFS or EXT4. exFAT compatible since Recalbox 4.1.
2. Create a folder on your USB Stick called `share`, one inside the share-folder called `roms` and copy your rom folders (full of roms) from your Computer to the rom folder you just created on the USB Stick.
![folder structure](http://s32.postimg.org/ut0q6mhv9/directory_structure.png)  
3. [Get root access on your Recalbox](https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-(EN))  
4. If you plan to transfer scraped data, stop EmulationStation with the command `/etc/init.d/S31emulationstation stop`
5. List the mounted partitions with the command `df -h`
![USB Stick not plugged in](http://s32.postimg.org/g8ye7b1f9/df_h_without_usb_plugged_in.png)  
6. Plug in your USB Stick into your Raspberry Pi and execute `df -h` again to find the newly mounted partition
![USB Stick plugged in](http://s32.postimg.org/ubpvqb6k5/df_h_with_usb_plugged_in.png)  
In this case, the USB Stick was mounted on `/media/usb0`.  
7. To copy your roms execute the following command:  `cp -rv /media/usb0/share /recalbox/` and wait until is finished.
![cp command](https://s31.postimg.org/kr5z69r4r/copy_command.png)  
Depending on the amount of roms you are copying, it may take a while. You will see the `#` symbol when it's done.  
8. Finally, type `reboot`
