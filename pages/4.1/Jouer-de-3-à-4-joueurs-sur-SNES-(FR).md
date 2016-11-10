---
layout: page
title: Jouer de 3 à 4 joueurs sur SNES (FR)
wikiPageName: Jouer-de-3-à-4-joueurs-sur-SNES-(FR)
menu: wiki
---

Il est possible de jouer jusqu’à 4 sur l'émulateur SNES sur Recalbox.  
Si vous souhaitez pouvoir profiter du multijoueur sur SNES, vous aurez besoin d'une manette par joueur, correctement configurée. 

Editez le fichier [[recalbox.conf|recalbox.conf-(FR)]] pour remplacer l'émulateur SNES par `snes9x_next`
```
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
snes.core=snes9x_next
```

Enregistrez puis redémarrez proprement votre Recalbox.

Lancez un jeu SNES, comme Micro Machines par exemple. Ouvrez le menu Retroarch avec le bouton Hotkey et le bouton B. Changez les paramètres suivants:
```
Setting / Configuration / Save Configuration On Exit : ON
Setting / Input / User 2 Device Type / Multitap
Quick menu / Restart Content
```
Vous pouvez remettre Save Configuration On Exit sur OFF après avoir redémarré le jeu.

Et voilà. Le jeu fonctionne, et vous êtes le roi de la soirée ! 
