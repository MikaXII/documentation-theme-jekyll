---
layout: page
title: Xin mo (FR)
wikiPageName: Xin-mo-(FR)
menu: wiki
---

Les interfaces USB Xin Mo fonctionnent en natif avec Recalbox.

L'interface gère 2 joueurs **depuis recalbox version 3.3.0 uniquement**.

### Pinout ###
Prenons comme exemple un panel à 6 boutons + stick + 1 bouton crédit(select) + 1 bouton start (généralement bouton 1 player et 2 player) avec cette disposition pour chaque joueur :

     ↑   Ⓨ Ⓧ Ⓛ  
    ← →	 Ⓑ Ⓐ Ⓡ    ($) (1P)
     ↓  

Il est préférable de rajouter un bouton hotkey dédié :
Ⓗ

Il faut ***absolument*** mapper les deux joueurs de la même manière, donc par exemple :

![XinMo pinout](https://github.com/digitalLumberjack/recalbox-os/wiki/images/XinMo_Arcade_Recalbox.jpg)

### Configuration ###

Ensuite il suffit de faire ***seulement*** la configuration du joueur 1 directement dans Emulationstation. La configuration du joueur 2 devrai fonctionner si le mappage est bien le même. N’essayez pas configurer le joueur 2, ça va écraser la config du joueur 1.
