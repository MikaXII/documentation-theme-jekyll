---
layout: page
title: Mount a remote samba share on system directory (EN)
wikiPageName: Mount-a-remote-samba-share-on-system-directory-(EN)
menu: wiki
---

You can mount a remote directory shared via samba on the recalbox system.

That can be used to mount the SHARE directory from the network.

First you will have to get a root prompt, see [[Root access on terminal|Root-access-on-terminal-(EN)]]


**Manually**   
to mount a remote directory use the command :   
```
mount -t cifs //serverip/directory  /mountpoint -o user=user,password=password,uid=0,gid=0,rw
```  
For a shared directory named roms on the server 192.168.1.10 you want to mount on /media/roms use :   
```
mount -t cifs //192.168.1.10/roms  /media/roms -o user=samba,password=password,uid=0,gid=0,rw
```


**On boot**   
So you want to mount the remote directory on boot, to replace the /recalbox/share directory, you must add a line to `/etc/fstab` :  
```
//192.168.1.10/share /recalbox/share cifs user=samba,password=password,uid=0,gid=0,rw 0 0
```
adapting it to your credentials.

Tip : if you have a space in a name of a directory, replace it with `\040` in fstab.
