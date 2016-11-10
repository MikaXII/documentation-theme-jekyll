---
layout: page
title: Ajouter un bouton on off a votre recalbox (FR)
wikiPageName: Ajouter-un-bouton-on-off-a-votre-recalbox-(FR)
menu: wiki
---

Vous pouvez maintenant ajouter un bouton on/off à votre **recalbox**.  
Le bouton peut être un bouton poussoir, aussi appelé _momentary switch_ ou un bouton _ON/OFF_.  
![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/switch/switch-battle.jpg)

Pour câbler le bouton au GPIO du Raspberry Pi, Connectez une broche au **GPIO3** (le **cinquième** gpio en partant d'en haut à gauche), et l'autre au ground sur sa droite (le **sixème** gpio):  
![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/switch/button-wire.png)


Enfin, vous devez actuver le support du bouton dans le [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29), en ajoutant une de ces lignes :  
- `system.power.switch=PIN56ONOFF` pour un bouton ON/OFF
- `system.power.switch=PIN56PUSH` pour un bouton poussoir

Et vous avez une recalbox qui peut être éteinte/allumée par un simple bouton !

-----------------------------------

Depuis Recalbox 4.0 beta 4, il y a une autre option où vous pouvez rajouter un bouton reset et une LED.

Dans recalbox.conf, ajoutez/décommentez (en enlevant le ; au début de la ligne) la ligne suivante:

- `system.power.switch=PIN356ONOFFRESET`

Pour câbler le bouton reset au GPIO du Raspberry Pi, connectez une broche au **GPIO2** (le **troisième** gpio en partant d'en haut à gauche), et l'autre au même ground que le bouton on/off (le **sixième** gpio).
La LED est connectée au **GPIO14** (le **huitième* gpio) ainsi qu'au ground.

Pour résumer:
- _Power+_ sur **GPIO 3** (**PIN 5**)
- _Reset+_ sur **GPIO 2** (**PIN 3**)
- _LED+_ sur **GPIO 14** (**PIN 8**)
- _Power-_, _Reset-_ et _Led-_ sur **Ground** (**PIN 6**)

Notez que cela ne fonctionne qu'avec un bouton poussoir pour le reset et un bouton ON/OFF pour l'alimentation.
