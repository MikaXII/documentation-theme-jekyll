---
layout: page
title: Créer une configuration custom par emulateur (FR)
wikiPageName: Créer-une-configuration-custom-par-emulateur-(FR)
menu: wiki
---

Vous avez la possibilité de créer votre propre configuration custom par chaque émulateur sur RecalBox.

### I - Retroarch
La configuration de RetroArch peut être créer à la main en appuyant votre propre configuration sur le standard [retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg) ou en l'éditant dans le menu de RetroArch. Vous devrez alors créer une nouvelle configuration, et paramétré le nouveau fichier de config afin qu'il soit chargé par votre émulateur [[recalbox.conf|recalbox.conf-(FR)]]

#### En utilisant le menu de RetroArch 

Partons sur l'exemple de créer un fichier de config spécifique pour la **neogeo**.

**1)** Lancer un jeu de l'émulateur que vous souhaitez personnaliser (ici neogeo) 

**2)** Entrer dans le menu de retroarch (_hotkey_ + _b_)

**3)** modifier toutes les configurations comme vous le souhaitez

**4)** retourner dans la première entrée du menu de RetroArch, ensuite faites ***Save new config*** (le nom du fichier de config devra ressembler à _fba_libretro.cfg_, avec le nom du core que vous être en train d'utiliser)

**5)** [[accès root sur Terminal|accès root sur Terminal  (FR)]] :  
Modifiez le nom du fichier de config pour quelque chose de plus simple à rappeler. Exemple : 
`mv /recalbox/share/system/configs/retroarch/fba_libretro.cfg /recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`  

**6)** Ajoutez la ligne suivante à [[recalbox.conf|recalbox.conf-(FR)]] :  
`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`  

##### Inputs

[See this page.](Custom controller mapping for specific system)

### II - piFBA

