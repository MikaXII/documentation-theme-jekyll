---
layout: page
title: Mount the remote recalbox share directory on your linux (EN)
wikiPageName: Mount-the-remote-recalbox-share-directory-on-your-linux-(EN)
menu: wiki
---

If you want to mount the recalbox share directory on your computer running a linux distribution, you'll have to follow these steps : 
- in `/etc/nsswitch.conf` : add wins at the end on the "hosts:" line.
- in `/etc/fstab`, add the line : 
```
//RECALBOX/share /mnt/recalbox cifs _netdev,noauto,user,username=root 0 0
```
- create the /mnt/recalbox directory : 
```
mkdir /mnt/recalbox
```

You can then mount the share partition as a user : 
```
mount /mnt/recalbox
```
