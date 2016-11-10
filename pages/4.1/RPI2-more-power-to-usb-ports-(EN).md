---
layout: page
title: RPI2 more power to usb ports (EN)
wikiPageName: RPI2-more-power-to-usb-ports-(EN)
menu: wiki
---

With the default settings, the Raspberry Pi 2 limits the current to 600mA for all four USB ports. The software changes proposed here will expand this limit to 1200mA.   
   
###Notes importantes : 
* This change is not only intended to RecalBox.   
* This change is reversible.   
* Using a supply of 2000mA is always recommended, whatever the use of Raspberry Pi 2.   
* The maximum current admissible by the Raspberry Pi 2 is 2000mA.   


### Reason to make this change:
Need to connect without using a self-powered USB hub should not exceed the new maximum current of 1200mA on 4 USB ports.    
For example: A hard drive self-powered USB 2.5 inch.   


###Exemple d'utilisation : 
* Using a USB SSD self powered to store all roms, bios and backups.   
* USB Wifi gourmet   
* Reload / Use multiple USB controllers simultaneously   

###How :
* [Edit config.txt file](https://github.com/recalbox/recalbox-os/wiki/Edit-the-config.txt-file-%28EN%29)
* Find line "`max_usb_current=...`"
* AAdd this line "`max_usb_current=1`" or modify line if exists.
* Save config.txt file.
* Reboot Raspberry Pi 2




