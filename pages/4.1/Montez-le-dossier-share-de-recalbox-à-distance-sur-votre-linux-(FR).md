---
layout: page
title: Montez le dossier share de recalbox à distance sur votre linux (FR)
wikiPageName: Montez-le-dossier-share-de-recalbox-à-distance-sur-votre-linux-(FR)
menu: wiki
---

Si vous souhaitez monter le répertoire share de votre recalbox sur un ordinateur sous linux, voici la marche à suivre :
- dans `/etc/nsswitch.conf` : ajoutez wins à la fin de ligne "hosts:"
- dans `/etc/fstab`, ajoutez la ligne :
```
//RECALBOX/share /mnt/recalbox cifs _netdev,noauto,user,username=root 0 0
```
- créez le répertoire /mnt/recalbox :
```
mkdir /mnt/recalbox
```

Vous pouvez maintenant monter la partition SHARE en tant qu'utilisateur :
```
mount /mnt/recalbox
```
