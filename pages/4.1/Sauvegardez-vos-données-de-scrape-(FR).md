---
layout: page
title: Sauvegardez vos données de scrape (FR)
wikiPageName: Sauvegardez-vos-données-de-scrape-(FR)
menu: wiki
---

**- Pour sauvegarder** votre scrape de jeux tu dois avec l'accès root [a root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29).   
<br>
Tu dois créer un dossier :

`mkdir /recalbox/share/system/backup_scrape/`

Ensuite, utilise cette commande pour sauvegarde tes différentes dossiers de scrape placés sur la partition partagé (share)

`cp -r /root/.emulationstation/downloaded_images /recalbox/share/system/backup_scrape/downloaded_images && cp -r /root/.emulationstation/gamelists /recalbox/share/system/backup_scrape/`

Donc maintenant rends toi vers le dossier partagé `system` sur le réseau et sauvegarde le dossier `backup_scrape` sur ton PC.
<br>
<br>
<br>
<br>
**- Pour restaurer** cette sauvegarde sur ta recalbox, ajoute ton dossier sauvegardé dans le dossier partagé `system` shared sur le réseau et utilise cette commande 

`cp -r /recalbox/share/system/backup_scrape/downloaded_images /root/.emulationstation/ && cp -r /recalbox/share/system/backup_scrape/gamelists /root/.emulationstation/`

Une fois la copie faite, redémarre ta recalbox et joue.
