---
layout: page
title: Scrapez vos jeux avec votre PC (FR)
wikiPageName: Scrapez-vos-jeux-avec-votre-PC-(FR)
menu: wiki
---

Premièrement, Merci à  [NeB](http://blog.recalbox.com/forums/users/neb/) pour cet how-to!   
Vous trouverez le sujet de discussion sur le [forum](http://blog.recalbox.com/forums/topic/tuto-scraper-ses-jeux-depuis-son-pc-plus-efficacement/).   
<br><br>
Vous pouvez utiliser votre PC pour scrapper vos jeux . Cette méthode utilise les signatures hashes de vos roms et non les noms. Ainsi c'est beaucoup efficace et rapide.

Ce que vous avons besoin : 
- un ordinateur
- des binaires pré-compilés de votre système d'exploitation : https://github.com/sselph/scraper/releases

Ce How-to a été rédigé pour les PC et MAC. Il peut être adapté assez facilement pour linux.


**1ère étape (identique pour PC et MAC):**

Si vous voulez scraper vos roms snes , créez un dossier nommé snes sur votre pc ou votre mac et ajoutez vos romes (format .smc ou zip). Ajoutez lui le fichier `scraper.exe` (pour les PC) ou `scraper` (pour les mac) précédemment téléchargé. 
Maintenant vous êtes prêt à scrapper vos roms snes.

**2nde étape :**

Pour les PC:

Faire  shift+right click sur votre dossier snes et choisir  “ouvrir une invite de commande  ici” 
Une fois dans la fenêtre cmd.exe saisir  :   

`scraper.exe -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375`   
<br>
(replacé “SYSTEM_NAME” par le nom de la console que vous voulez scraper snes, nes, mastersystem, etc...)   
Valider par l touche enter, et patientez ...
<br>
<br>
<br>
Si vous voulez scraper vos roms arcade (**MAME** or **FBA** incluant **NEOGEO**) usez cette commande :

`scraper.exe -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/mame_or_fba_or_neogeo" -no_thumb=true -max_width=375` 
<br>  
(comme précédemment, remplacé  “mame_or_fba_or_neogeo” pour mame ou fba ou neogeo)

Pour les MAC 2 solutions:

- Ouvrir une fenêtre du terminal (Applications/Utilitaires) et glisser/déposer dans le terminal, le dossier snes que vous avez créé précédemment.

ou

Activez l'option « nouveau terminal au dossier ». Vous trouvez cette option dans les préférences du clavier dans l’onglet « Raccourcis clavier «  et dans la colonne de gauche, placez vous sur « Services », naviguez dans la liste pour trouver la ligne « Nouveau terminal au dossier ». Cochez la case qui précède cette ligne. Maintenant, right click sur le dossier snes et choisir « Nouveau terminal au dossier ».
Une fois dans la fenêtre cmd.exe saisir  :

`scraper -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375`   
<br>
(replacé “SYSTEM_NAME” par le nom de la console que vous voulez scraper snes, nes, mastersystem, etc...)   
Valider par l touche enter, et patientez ...
<br>
<br>
<br>
Si vous voulez scraper vos roms arcade (**MAME** or **FBA**) utilisez cette commande :

`scraper -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/mame_or_fba_or_neogeo" -no_thumb=true -max_width=375` 
<br>  
(comme précédemment, remplacé  “mame_or_fba_or_neogeo” pour mame ou fba ou neogeo)

**3ème étape :**

Bien, maintenant que vous avez vos romset et que les fichiers de scrap correspondent, vous pouvez les copier sur votre recalbox.
<br><br>
Il faut au préalable arrêter emulationstation pour vous permettre de remplacer le fichier gamelist. Pour cela exécutez en SSH la commande suivante ````/etc/init.d/S31emulationstation stop````
<br><br>
Donc, allez sur votre recalbox, et rendez vous dans le dossier partagé  `system` sur le réseau , créer une dossier nommé  `backup_scrape` et coller les dossiers `downloaded_images` et `gamelists`
Maintenant vous pouvez suivre les instructions de ce [mini-how-to - section "sauvegarde "](https://github.com/digitalLumberjack/recalbox-os/wiki/Sauvegardez-vos-donn%C3%A9es-de-scrape-%28FR%29).
<br><br>
Une fois terminé, veuillez relancer emulationstation toujours en SSH avec : ````/etc/init.d/S31emulationstation start````
