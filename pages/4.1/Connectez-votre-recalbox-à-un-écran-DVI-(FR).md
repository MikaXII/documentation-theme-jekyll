---
layout: page
title: Connectez votre recalbox à un écran DVI (FR)
wikiPageName: Connectez-votre-recalbox-à-un-écran-DVI-(FR)
menu: wiki
---

Vous devez connecter votre recalbox sur un écran DVI mais vous obtenez un écran noir ?

Alors [[éditez le fichier config.txt|Editer-le-fichier-config.txt-(FR)]], et commentez la ligne   
`hdmi_drive=2`  
avec un # :  
`#hdmi_drive=2`


Depuis recalbox v4.0.0, la partition `/boot` est en **read-only** (lecture seule).   
Donc, avant de pouvoir éditer le fichier `config.txt`, vous devez monter la partition `/boot` avec des droits de lecture-écriture.  
Connectez-vous en [accès root](https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29), puis saisissez la commande suivante : `mount -o remount, rw /boot`
