---
layout: page
title: Changer l'ordre des consoles dans EmulationStation (FR)
wikiPageName: Changer-l'ordre-des-consoles-dans-EmulationStation-(FR)
menu: wiki
---

# Etapes
* Se connecter en SSH à votre Recalbox
* Se rendre dans le dossier d'EmulationStation dans le répertoire share_init > `cd /recalbox/share_init/system/.emulationstation`
* Stopper EmulationStation > `/etc/init.d/S31emulationstation stop`
* Editer le fichier `es_system.cfg` > `nano es_system.cfg`
* Dans ce fichier, vous trouverez toutes les entrées des consoles que Recalbox supporte. Changer juste l'ordre des entrées telles que vous souhaitez les voir apparaître dans EmulationStation
* Sauvegardez vos modifications
* Démarrer EmulationStation > `/etc/init.d/S31emulationstation start`
* Done !

# Remarques
Malheureusement, ce n'est pas possible à l'heure actuelle de rendre l'entrée "Favorites" en première position.
