---
layout: page
title: Contrôleur Gamecon (FR)
wikiPageName: Contrôleur-Gamecon-(FR)
menu: wiki
---

# 1 - Intro

Le pilote est conçu pour être utilisé avec les manettes de jeux rétro connectés aux GPIO du Raspberry Pi. Jusqu'à 4 manettes peuvent-être utilisés en même temps s'ils sont du type suivant :
* Manette NES
* Manette SNES
* Manette PSX / PS2
* Manette N64
* Manette Gamecube


Le pilote est basé sur celui de Gamecon mais il utilise des paramètres et des sorties (pinout) différents. Il n'y a donc aucune garantie que cela fonctionne et vous le faites à vos risques et périls.

# 2 - Connecter les manettes
Les PINS P1-01 et P1-06 sont utilisés pour l'alimentation en 3.3V et la masse. Elles sont communes à l'ensemble des manettes connectées sur GPIO. Même si les manettes SNES / NES fonctionnent en 5V de manière nominale, elles devraient fonctionner en 3.3V. Il n'y a donc PAS besoin d'utiliser un convertisseur sur les PINS de données. L'intensité maximale (50mA) du Raspberry devrait être suffisante pour alimenter 4 manettes sur GPIO. Cependant vous devez utiliser une alimentation pour Raspberry performante (type 2.1A) pour éviter toute chute de tension non voulue.



Les PINS de données P1-03,05,07,26 (GPIO0, GPIO1, GPIO4 and GPIO7) sont indépendantes les unes des autres et chaque manette en utilise une PIN unique.

NOTE: Les PINS P1-03 & P1-05 correspondent à GPIO2 & GPIO3 sur les cartes rev.2. Cela doit être pris en compte pendant le chargement du module comme expliqué dans la section 3.



Les PINS P1-19 & P1-23 (GPIO10 & 11) sont les PINS de signal communes à toutes les manettes NES / SNES.
Les PINS P1-08, P1-10 & P1-12 (GPIO14, 15 & 18) sont les PINS de signal communes à toutes les manettes PSX / PS2.

## 2.1 Manettes NES / SNES
| PIN RASPBERRY | PIN manette SNES| PIN manette NES  |
| -------------- |:-------------------:|:------------------:|
| P1-01 (3.3V)   | 1 (power - 5V)      | 1 (power - 5V)     |
| GPIO10	 | 2 (clock)           | 5 (clock)          |
| GPIO11         | 3 (latch)           | 6 (latch)          |
| GPIOXX         | 4 (data)            | 7 (data)           |
| P1-06 (GND)    | 7 (ground)          | 4 (ground)         |
<br>
**PINOUT NES et SNES**

![snes nes pinout](https://i.warosu.org/data/vr/img/0027/22/1444150264652.png)


Les GPIOXX sont les PIN de données indépendantes. Voir la section 3 pour selectionner le bon GPIO à utiliser.

## 2.2 Manettes N64
![](http://s.hswstatic.com/gif/n64-pinout.gif)

## 2.3 Manettes Gamecube
| PIN RASPBERRY        | PIN manette GAMECUBE  |
| -------------- |:------------------------:|
| P1-01 (3.3V)   | 6 (power/3.43V)          |
| GPIOXX         | 3 (data)                 |
| P1-06 (GND)    | 2&5 (gnd)                |

Les GPIOXX sont les PIN de données indépendantes. Voir la section 3 pour selectionner le bon GPIO à utiliser.

## 2.4 Manettes PSX / PS2
| PIN RASPBERRY        | PIN manette PSX / PS2    |
| -------------------- |:------------------------:|
| P1-01 (3.3V)         | 5 (VCC)                  |
| GPIO14               | 2 (Command)              |
| GPIO15               | 6 (ATT)                  |
| GPIO18               | 7 (CLK)                  |
| GPIOXX               | 1 (Data)                 |
| P1-06 (GND)          | 4 (ground)               |

Les GPIOXX sont les PIN de données indépendantes. Voir la section 3 pour selectionner le bon GPIO à utiliser.

![](http://www.geocities.ws/digitan000/Hardware/22/pinout.gif)

# 3 Configurer le pilote
## 3.1 Configurer les manettes
Activer le pilote Gamecon dans le fichier "recalbox.conf [[recalbox.conf|recalbox.conf-(FR)]] en mettant `controllers.gamecon.enabled=1` (si elle existe, la modifier, sinon la créer).

Utilisez l'index des manettes suivant pour configurer le paramètre `controllers.gamecon.args` :
`map=<pad1/GPIO0>,<pad2/GPIO1>,<pad3/GPIO4>,<pad4/GPIO7>,<pad5/GPIO2>,<pad6/GPIO3>` 

Où <pad...> est le numéro définissant le type de manette :
* 0 = pas de connexion
* 1 = manette SNES 
* 2 = manette NES
* 3 = manette Gamecube
* 6 = manette N64
* 7 = manette PSX/PS2 
* 8 = manette PSX DDR
* 9 = souris SNES

Par exemple, si une manete SNES est connectée au GPIO4 et une manette N64 sur le GPIO7, le mappage sera `map=0,0,1,6`.

**NOTE**: 
* pad1 & pad2 sont uniquement utilisés avec une carte rev.1
* pad5 & pad6 sont uniquemnet utilisés avec une carte rev.2

Donc si vous avez une carte rev.2, pad1 & pad2 doivent être paramétré à 0.

L'index final des manettes (utilisé par les programmes) est assigné séquentiellement pour les manettes connectées en démarrant par 0. Donc dans l'exemple précédent, la manette SNES aurait un index égal à 0 et la manette N64 un index égal à 1.

Utilisez la commande suivante pour vérifier que le module s'est chargé avec succès : `tail /var/log/kern.log`

## 3.2 Tester les manettes
Testez votre joystick avec [[jstest|https://github.com/recalbox/recalbox-os/wiki/Testez-votre-joystick-avec-jstest-%28FR%29]].

## 3.3 Calibrer l'axe analogique d'une manette N64
Pour chaque manette N64, executez la commande suivante :
```
jscal -s 4,1,0,0,0,6972137,6972137,1,0,0,0,6547006,6468127,1,0,0,0,536854528,536854528,1,0,0,0,536854528,536854528 /dev/input/jsX
```

## 3.4 Configurer le temps de réponse pour les manettes PSX
Le temps de réponse pour les manettes PSX est de 10µs ce qui minimise le retard induit par le pilote. Cependant dans quelques rares cas cela n'est pas suffisant pour avoir une entrée stable. Si vous avez des problèmes lors de la lecture des manettes PSX, augmentez le délais en suivant le paramètre "extra modbprobe" :  "psx_delay=<delay>" où "delay" est la valeur en µs comprise entre 1 et 50.

#5 Pour aller plus loin
En anglais uniquement : [Multi-console gamepad driver for GPIO|https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=15787]

Merci à "marqs" pour le pilote et pour nous permettre d'utiliser ton "README" dans le WIKI de recalbox.
