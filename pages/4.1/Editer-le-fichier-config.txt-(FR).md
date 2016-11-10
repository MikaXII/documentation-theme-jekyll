---
layout: page
title: Editer le fichier config.txt (FR)
wikiPageName: Editer-le-fichier-config.txt-(FR)
menu: wiki
---

Il y a deux façons de modifier le fichier config.txt:
- **SSH**  
[Se connecter avec ssh] (https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29) et utiliser nano pour éditer le fichier /boot/config.txt

 `nano /boot/config.txt`

- **Noobs**  
Branchez un clavier USB et appuyez sur **Maj** durant le boot de recalbox pour accéder au menu de Recovery.
Ensuite, appuyez sur "e" pour obtenir le menu édition, et vous pourrez effectuer des modifications directement sur le fichier. 
Vous pouvez changer la langue du clavier en appuyant sur "l" et "k".

- **Partition**   
Passer [Passer la partition de boot en écriture](https://github.com/recalbox/recalbox-os/wiki/partition-en-ecriture-(FR)) uniquement en version 4.0.0
