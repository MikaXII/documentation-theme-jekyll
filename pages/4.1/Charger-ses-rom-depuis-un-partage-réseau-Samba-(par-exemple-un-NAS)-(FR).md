---
layout: page
title: Charger ses rom depuis un partage réseau Samba (par exemple un NAS) (FR)
wikiPageName: Charger-ses-rom-depuis-un-partage-réseau-Samba-(par-exemple-un-NAS)-(FR)
menu: wiki
---

Pour pouvoir stocker ses Roms sur un NAS et donc pouvoir en stocker beaucoup plus que sur une carte SD, je me suis permis de compiler des astuces trouvé sur le forum (merci à @nesousx, @kevean, @FunkyBeef et @Acris pour vos solutions !)
 
**Tout d'abord le NAS** _(testé sur un Synology, mais le fonctionnement est identique un peu partout)_ : 
* Créez un répertoire partagé (appelons le "/roms/")
* Créez un utilisateur avec les droits d’écriture/lecture sur ce répertoire. (ou réutiliser un utilisateur avec ces droits)
* Recréez l'architecture du répertoire Roms de la recalbox (via le partage réseau, via ftp, ou à la main si vous voulez ;) l'important est d'avoir la même architecture, c'est à dire un répertoire par machines émulées.

Option :

_Il est tout à fait possible de faire la même chose depuis le disque dur de votre PC. Sous Windows, vous pouvez créer un répertoire partagé et le monter de la même manière sur la recalbox. Seul inconvénient : Le PC doit être allumé pour accéder aux Roms depuis la recalbox._

**Maintenant sur la Recalbox** 

depuis un terminal ou depuis une connexion SSH ([Voir le Tuto pour se connecter en SSH](https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29))

Pour V4.0.0 seulement : Avant d'éditer le fstab écrivez ceci :

> mount -o remount,rw /

editez le **fstab**

> nano /etc/fstab

dans le fichier fstab, ajoutez la ligne suivante : 

```
//IP_NAS/REPERTOIRE_PARTAGE  /recalbox/share/roms cifs user=XXX,password=YYY,uid=0,gid=0,rw 0 0
```

Avec bien sur : 
* IP_NAS : l'ip de votre NAS (_exemple : 192.168.0.1_)
* REPERTOIRE_PARTAGE : le repertoire que vous venez de créer (_exemple roms_)
* Remplacer XXX : par le nom de l'utilisateur de votre NAS
* Remplacer YYY : par le mot de passe de l'utilisateur de votre NAS

```
Exemple : 
//192.168.0.1/roms  /recalbox/share/roms cifs user=recalbox,password=recalbox,uid=0,gid=0,rw 0 0
```

Quittez et sauvegardez : 
* CTRL+X
* Y
* ENTER

maintenant éditez le fichier **S31emulationstation**

> nano /etc/init.d/S31emulationstation

ajoutez _mount -a_ juste après

> case "$1" in

> start)

> **mount -a**

Quittez et sauvegardez : 
* CTRL+X
* Y
* ENTER

Il ne reste plus qu' à déplacer S31emulationstation pour qu'il démarre après le réseau : 

> mv /etc/init.d/S31emulationstation /etc/init.d/S92emulationstation

Redémarrez enfin la recalbox : 

> reboot

Et vous retrouverez toutes vos Roms depuis le NAS.

Attention:

Si vous mettez à jour Recalbox, un nouveau S31emulationstation sera créé. Ainsi reprennez de : maintenant éditez le fichier **S31emulationstation**
