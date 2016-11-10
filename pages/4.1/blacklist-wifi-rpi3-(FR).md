---
layout: page
title: blacklist wifi rpi3 (FR)
wikiPageName: blacklist-wifi-rpi3-(FR)
menu: wiki
---

Déçu par le débit du wifi intégré du raspberry pi 3, tu souhaites le désactiver.   
    
Voici comment faire : 

Connecte toi en [ssh via putty ou winscp](https://github.com/recalbox/recalbox-os/wiki/acces-via-WinSCP-%28FR%29)

Monter la partition en écriture :   
`mount -o remount,rw /`   
    

Edit le fichier suivant : 
   
`nano /etc/modprobe.d/blacklist.conf `
    
Ajoute cette ligne :    

`blacklist brcmfmac`   

Enregistre `ctrl+x` + `Y` puis `reboot`

Branche ton dongle wifi et teste.
