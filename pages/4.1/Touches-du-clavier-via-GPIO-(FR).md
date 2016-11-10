---
layout: page
title: Touches du clavier via GPIO (FR)
wikiPageName: Touches-du-clavier-via-GPIO-(FR)
menu: wiki
---

Recalbox comporte le module retrogame sous le nom de **recalbox-retrogame** qui se trouve dans `/usr/bin/recalbox-retrogame`.

Ce module va permettre d'utiliser les GPIO afin de reproduire le comportement d'un vrai clavier USB sous Recalbox.

_**Attention : Ne fonctionne que si on retrouve la ligne**_ `controllers.gpio.enabled=0` _**dans recalbox.conf**_

## Exemples

- Si vous voulez intégrer un Raspberry pi dans une vieille console et réutiliser les boutons de la façade (ex: PAUSE/SELECT d'une Atari 7800)
- Câbler sur une borne d'arcade, un bouton  qui aurait le même comportement que la touche Echap d'un clavier
- Ou tout simplement réussir à se passer d'un clavier...

## Pinout

- [Raspberry Pi 2/B+/A+](https://github.com/ian57/Recalbox-Retrogame-2Players-Pi2#pinout-mapping)

## Installation

### Câblage

Il faut utiliser des boutons poussoir (qui remonte après un appui) et relier un borne à une masse (GROUND) et l'autre borne à un GPIO.

### Script

Afin de lancer automatiquement le module au démarrage de Recalbox il est important d'ajouter un script.

1. Créer un ficher texte "S99retrogame" sans extension
2. Ajouter les deux lignes de codes suivantes : 
```   
/usr/bin/recalbox-retrogame
exit 0
```
3. Donner les droits : `chmod 775 /etc/init.d/S99retrogame`
4. Placer le dans : `/etc/init.d/`
5. Rebooter et vérifier en SSH (via Putty par exemple) si le module c'est bien lancé grâce à la commande : `ps aux|grep recalbox-retrogame`. Si la commande retourne un identifiant c'est que vous avez réussi :+1: 
