---
layout: page
title: Shaders configuration (FR)
wikiPageName: Shaders-configuration-(FR)
menu: wiki
---

Vous pouvez facilement configurer les *shaders* pour vos systèmes.  

### I - Sets de shaders
Avec *shader sets*, vous pouvez configurer les shaders sur tous vos systèmes avec une seule option.  

Les *sets* sont créés par la communauté, et seront optimisés lors de chaque nouvelle version de recalbox.  

Les *sets* disponibles : 
- **scanlines** : active les scanlines sur tous les emulateurs.
- **retro** : sélectionne le "meilleur" shader pour chaque système, choisi par la communauté. Il vous apportera l'expérience dce jeu la plus proche de l'expérience originale.
- **none** : aucun shaders   

Vous pouvez définir le **set de shaders** que vous souhaitez activer dans le menu "OPTIONS JEUX" de EmulationStation, ou directement dans [[recalbox.conf|recalbox.conf-(FR)]] avec l'option `global.shaderset`.   

### II - Shaders personnalisés
Vous pouvez combiner la force des **sets de shaders** avec la flexibilité de recalbox.conf
L'option `global.shaderset` peut définir un shader de base pour chaque émulateur. Puis vous pouvez modifier le shader d'un système précis avec l'option `systemname.shader`.   

Par exemple, si je veux les meilleurs shaders sur tous les systèmes, mais aucun shader pour ma gameboy, et un shader spécifique pour ma snes : 
```
# Set the retro shader set for all emulators, now i know that i have the best selection
global.shaderset=retro
# But my gameboy seem better for me with no shaders
gb.shaders=
# And i want to apply my own shader preset on snes
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```

Vous pouvez aussi changer de *shader* en plein jeu, en utilisant votre manette. Utilisez les [Commandes spéciales](#duringgame-special) Hotkey + R2 ou Hotkey + L2 pour voir s'afficher le shader suivant ou précédent.  

### III - Captures d'écran
Aucun shader :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-no-filter.png)

Avec le set retro activé :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-caligari-115.png)
