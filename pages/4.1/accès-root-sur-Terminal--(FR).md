---
layout: page
title: accès root sur Terminal  (FR)
wikiPageName: accès-root-sur-Terminal--(FR)
menu: wiki
---

Afin d'obtenir un terminal avec un accès root sur la recalbox, vous avez deux options:

- **SSH**
Se connecter via ssh à la recalbox, avec les informations d'identification suivantes: nom d'hôte (recalbox) ou ip, "root" comme login et "recalboxroot" comme mot de passe. Vous pouvez utiliser un terminal à partir d'un Mac, [MobaXterm](http://mobaxterm.mobatek.net/) or [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/) sur Windows, ou un Shell sous linux.  
Tapez : `ssh root@the_recalbox_ip`   
   
Sous Mac si vous obtenez cette erreur :  `Error opening terminal: xterm-256color `   
Solution : dans les préférences Terminal, changer “x-term 256 colors” en “x-term”, et tout fonctionne.   
   

- **Accès direct**
Sur l'interface emulationstation, appuyez sur F4 pour quitter, puis sur Alt + F2 pour obtenir un terminal et utilisez les mêmes identifiants que ci-dessus.

