---
layout: page
title: Edit the config.txt file (EN)
wikiPageName: Edit-the-config.txt-file-(EN)
menu: wiki
---

The config.txt file is read by the raspberry on boot and contains your rpi specific configuration, like, the overscan settings, overclocking, default video mode etc...

It's located on the filesystem at `/boot/config.txt`

There are two ways to edit the config.txt file : 
- **SSH**  
[Connect with ssh](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29)  
Remount partition on read-write  
```mount -o remount, rw /boot```  
use nano to edit the file located at /boot/config.txt  
```nano /boot/config.txt```  
reboot your Pi

- **Noobs**  
Plug an usb keyboard and press Shift (Maj en français) during the recalbox boot to access recovery menu.
Then press "e" to get the edition menu, and make you changes here. You can switch the language and keyboard mapping by pressing "l" and "k".
