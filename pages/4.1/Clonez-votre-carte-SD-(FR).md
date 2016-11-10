---
layout: page
title: Clonez votre carte SD (FR)
wikiPageName: Clonez-votre-carte-SD-(FR)
menu: wiki
---

**Pour cloner** ta carte SD et avoir un backup complet de ta recalbox tu peux utiliser ces logiciels  :

- **Windows** : [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/) avec la fonction READ
- **MacOS x** : ApplePi-Baker
- **Linux** : Utilise la commande DD  dans un terminal (plus d'informations plus loin)

<br>
Branche  ta carte SD dans votre PC utilisant linux.
Déterminer quel périphérique est ta carte SD 

`sudo fdisk -l`

Une fois dans ton dossier de sauvegarde (backup), extrait et compresse ta carte SD avec cette commande :



`sudo dd if=/dev/sdX | gzip -9 > ./recalbox-20150411-sdb.img.gz`   
(la lettre X doit être remplacéE par la lettre déterminéE à la première étape.)
<br>
<br>
<br>
**Pour restaurer** ta sauvegarde, branche ta carte SD formatée en FAT32 dans votre PC et utilise cette commande  ::

`gunzip ./recalbox-20150411-sdb.img.gz | sudo dd of=/dev/sdX`   
(où /dev/sdX est ta carte SD)
<br>
<br>
<br>
_Pour suivre l'avancée du processus `dd`, ouvrez un nouveau terminal et tapez la commande suivante `watch -n 5 sudo pkill -USR1 -n -x dd`_
