---
layout: page
title: Jouer avec deux GameBoy (FR)
wikiPageName: Jouer-avec-deux-GameBoy-(FR)
menu: wiki
---

Il est possible de jouer à deux joueurs avec deux GameBoy sur Recalbox.  

Editez le fichier [[recalbox.conf|recalbox.conf-(FR)]] pour remplacer l'émulateur GameBoy par `tgbdual`
```
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
gb.core=tgbdual ;GameBoy
gb.ratio=custom
gbc.core=tgbdual ;GameBoyColor
gbc.ratio=custom
```

Enregistrez puis redémarrez proprement votre Recalbox.

Lancez un jeu GameBoy comme Ballon Kid par exemple. Ouvrez le menu Retroarch avec le bouton Hotkey et le bouton B. Changez les paramètres suivants:
```
Setting / Configuration / Save Configuration On Exit : ON
Quick menu / Core Options / GB Link Enable (restart) : enabled
Quick menu / Core Options / Screen placement (restart) : horizontal
Quick menu / Core Options / Switch player screens : normal ; joueur 1 à gauche et joueur 2 à droite
Quick menu / Core Options / Show player screens : both players
Settings / Video / Aspect Ratio Index : 20:9 (1:1 PAR) ; 100% conforme ratio GB
Quick menu / Restart Content
```
Vous pouvez remettre Save Configuration On Exit sur OFF après avoir redémarré le jeu.

Pensez que si votre TV n'est pas réglée en 16/9 - si le menu de Recalbox n'occupe pas l'intégralité de l'écran- alors le ratio ne sera pas bon.
Notez aussi que les jeux mono-joueurs vont aussi êtres doublés. Deux GB côte à côte, bien pour un duel de speed run, inutile sinon.
Pour éviter trop de manipulations, vous pouvez n'appliquer tous ces paramètres que sur GB ou que sur GBC.
