---
layout: page
title: Comment personnaliser mapping manette (FR)
wikiPageName: Comment-personnaliser-mapping-manette-(FR)
menu: wiki
---

Pour ceux qui veulent changer le mapping des boutons suivant les émulateurs du core retroarch:

**1)** lancer un jeu dudit émulateur,

**2)** dans le menu de retroarch (hotkey +b) aller dans « Settings », puis « Input user 1 binds »

**3)** reconfigurer les touches, pensez à avoir un clavier sous la main, car à un moment ca peut coincer, donc finir au clavier ("w" et "x" pour valider et revenir en arriere)  
  
**4)** Aller ensuite dans "Input hotkey binds" et reconfigurer les touches comme vous le souhaitez  

**5)** revenir au premier menu de retroarch et faire « Save new config » (normalement le nom de la configuration est nom_du_core.cfg, par exemple catsfc.cfg si vous êtes sur snes + catsfc)

**6)** se connecter en ssh a la recalbox, et modifier le nom du fichier de configuration pour quelques chose de plus parlant : ici émulateur neogeo  
`mv /recalbox/share/system/configs/retroarch/catsfc.cfg /recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`  

**7)** modifier le fichier recalbox.conf en ajoutant la ligne suivante pour prendre en compte la nouvelle configuration (attention tout les autres parametres sont ceux par defaut, donc pas de shader, cheat, ou autre):  
`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`  
