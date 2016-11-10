---
layout: page
title: Load your roms from a network shared folder (EN)
wikiPageName: Load-your-roms-from-a-network-shared-folder-(EN)
menu: wiki
---

You can have your Roms on a NAS or a shared folder on your PC to have much more space than on a SD Card.
This is a compilation of forum users (thanks to @nesousx, @kevean, @FunkyBeef and @Acris for your solutions !)
 
**First on the NAS** _(tested on a Synology NAS, but it will be the same on other)_ : 
* Create a shared folder (for exemple call it "/roms/")
* Create a user with write/read rights on this folder (or have a user who have it)
* Recreate the same folder as the Roms recalbox folder (with SMB network, FTP, or with your little finger if you want ;) The aim is to have the exact same folder, one by emulator.

Option :

_You can do the same thing on a PC, the problem is you need to turn on your PC to access the roms._

**Now on Recalbox** 

With a terminal or via SSH ([See the Tuto](https://github.com/recalbox/recalbox-os/wiki/Network-access-with-WinSCP-%28EN%29))

For V4.0.0 only: Before editing fstab write this: 

> mount -o remount,rw /

edit **fstab**

> nano /etc/fstab

add this line (all on the same line, no carrier return): 

```//IP_NAS/SHARED_FOLDER /recalbox/share/roms cifs user=XXX,password=YYY,uid=0,gid=0,rw 0 0```

With : 
* IP_NAS : the IP adress (_exemple : 192.168.0.1_)
* SHARED_FOLDER : the folder you just make (_exemple roms_)
* XXX : User name
* YYY : User Password

```
Exemple : 
//192.168.0.1/roms /recalbox/share/roms cifs user=recalbox,password=recalbox,uid=0,gid=0,rw 0 0
```

Quit & Save : 
* CTRL+X
* Y
* ENTER

Now edit **S31emulationstation**

> nano /etc/init.d/S31emulationstation

Add _mount -a_ just after

> case "$1" in

> start)

> **mount -a**

Quit & Save : 
* CTRL+X
* Y
* ENTER

Now you need to move S31emulationstation after the network start : 

> cd /etc/init.d/

> mv S31emulationstation S92emulationstation

restart recalbox : 

> reboot

Tadaa, you have all your roms from the NAS.

Warning : 

If you update Recalbox, a new S31emulationstation will be created. So restart from : Now edit **S31emulationstation**
