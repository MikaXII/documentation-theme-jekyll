---
layout: page
title: Auto mount of usb in place of share partition (EN)
wikiPageName: Auto-mount-of-usb-in-place-of-share-partition-(EN)
menu: wiki
---

You can use an external drive as the SHARE partition. 

This way you can have all roms, media, and custom files on a huge HDD or usb key.

You will need to [get a root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29) and a USB KEY formatted in FAT32.

Use the command `mount` to see mounted volumes : 

```
rootfs on / type rootfs (rw)
/dev/root on / type ext4 (rw,relatime,data=ordered)
devtmpfs on /dev type devtmpfs (rw,relatime,size=242096k,nr_inodes=60524,mode=75 5)
proc on /proc type proc (rw,relatime)
devpts on /dev/pts type devpts (rw,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /dev/shm type tmpfs (rw,relatime,mode=777)
tmpfs on /tmp type tmpfs (rw,relatime)
sysfs on /sys type sysfs (rw,relatime)
/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
/dev/mmcblk0p5 on /boot type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
/dev/sda1 on /media/usb0 type vfat rw,sync,nodev,noexec,noatime,nodiratime,fmas=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro _
```

Search where the key is mounted, it will be a line like that : 

`/dev/sda1 on /media/usb0 type vfat` **<-----**

Copy all data from SHARE partition to USB Key :

`cp -rv /recalbox/share/* /media/usb0/`

It could take a long time depending of the size of your rom collection.

You need to switch the filesystem to RW to edit file /etc/fstab. Write the line:

`mount -o remount,rw /`

Now edit the mount point in the file /etc/fstab :

`vi /etc/fstab`

Push key **i** for edit

Add a # to comment the line :   
```
/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```


Like this :

```
#/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```


And add the new line that will mount your device on /recalbox/share :

`/dev/sda1 /recalbox/share vfat defaults,rw 0 0`


Press **Escape** press key **:** press key **wq** press **Entrer** to save and quit.

You can now **reboot**
