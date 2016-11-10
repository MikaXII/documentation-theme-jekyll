---
layout: page
title: RPi2 : Augmenter le courant disponible sur les ports USB
wikiPageName: RPi2-:-Augmenter-le-courant-disponible-sur-les-ports-USB
menu: wiki
---


Avec les réglages par défaut, le Raspberry Pi 2 limite le courant à 600mA pour l'ensemble des 4 ports USB.
La modification logicielle qui est proposée ici va étendre cette limite à 1200mA.



###Notes importantes : 
* Cette modification n'est pas uniquement destinée à RecalBox.
* Cette modification est réversible.
* L'utilisation d'une alimentation de 2000mA est toujours préconisée, quelque soit l'usage du Raspberry Pi 2.
* Le courant maximal admissible par le Raspberry Pi 2 est de 2000mA.



###Raison d'effectuer cette modification :
Avoir besoin de connecter, sans utiliser un concentrateur USB autoalimenté, de périphériques USB gourmands, sans dépasser la nouveau courant maximal de 1200mA sur les 4 ports USB.
Par exemple : Un disque dur 2.5 pouces USB autoalimenté.



###Exemple d'utilisation : 
* Utilisation d'un disque SSD USB autoalimenté afin de stocker l'ensemble des roms, des bios et des sauvegardes.
* Clé USB Wifi gourmande
* Recharger/Utiliser plusieurs manettes USB simultanément




###Comment faire :
* [Editer le fichier config.txt](https://github.com/digitalLumberjack/recalbox-os/wiki/Editer-le-fichier-config.txt-%28FR%29)
* Rechercher la présence éventuelle de la ligne "`max_usb_current=...`"
* Ajouter la ligne suivante "`max_usb_current=1`" ou modifier sa valeur à 1 si elle existe déjà.
* Enregistrer le fichier config.txt
* Redémarrer le Raspberry Pi 2



