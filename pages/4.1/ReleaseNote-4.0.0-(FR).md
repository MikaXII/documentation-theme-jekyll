---
layout: page
title: ReleaseNote 4.0.0 (FR)
wikiPageName: ReleaseNote-4.0.0-(FR)
menu: wiki
---

Salut à tous!

recalboxOS **v4.0.0** est sur le point de sortir !

## Nouveau board :
* RecalboxOS est compatible Raspberry pi Zero !

## Les nouveaux systèmes : 
* Wonderswan Color
* Lutro : LUA framework
* NeoGeo
* NeoGeo Pocket Color
* Vectrex
* Game And Watch
* Lynx
* PRBoom
* Atari 7800
* Tgbdual
* NXengine - Cavestory
* SuperGrafx
* Moonlight - Streaming nvidia
* mame2003 - utilisé par defaut pour mame
* Atari ST
* Amstrad CPC
* Sinclair ZX Spectrum
* Sinclair ZX 81
* Odyssey 2/Videopac

## Les systèmes mis à jour : 
* libretro-fba 0.2.97.37
* GLideN64 video plugin pour n64
* snes9x (fix the bomberman 5 freeze)
* atari 2600 stella core for 2 players support
* scummvm - passage sous sdl 2 + ajout du support manette
* Kodi - 15.2


## Features : 
* Shadersets - set de shaders automatiquement optimisé pour chaque système
* Favoris - Ajoutez vos jeux en favoris
* Support des manettes dans kodi
* Recalbox Manager - configurez votre recalbox depuis son interface web
* Virtual Gamepad - jouez avec votre smartphone !
* Cheats - trichez !
* Silent Install - installation automatique de recalbox (plus besoin du clavier)
* Retroachievements - débloquez des trophées dans vos jeux retro !
* Configuration automatique de la Nintendo 64 + Support des commandes spéciales
* ReadOnly filesystem - le système est maintenant en lecture seule. Plus de corruption du fs !
* Nouveau thème officiel RECALBOX - + de systèmes, musiques libres de droits !

## Nouveaux drivers :
* driver xbox mis à jour
* driver ps3 mis à jour 
* support des manettes bluetooth
* support des 8bitdo
* support des wiimotes
* support des retrobit controllers
* support des 4NES4SNES controllers
* support des sticks XArcade
* support des encodeurs clavier


## Nouvelles features dans ES : 
* Ecran d’arrêt pour ES
* Select pour éteindre/redémarrer
* Favoris
* Rechargement dynamique de la liste des jeux - plus besoin de redémarrer pour actualiser vos roms
* hidden - cacher les jeux ou bios que vous ne voulez pas voir apparaître
* Support des périphériques externes de stockage


## Nouvelles options dans ES : 
* Hostname
* Bluetooth
* Auto save/load des savestates sous retroarch
* Configuration de retroachievements
* Configuration des emulateur / core pour chaque système
* Configuration des emulateur / core pour chaque jeu !

## Nouvelles langues supportés :
* Chinois
* Basque
* Turque
* Suédois

## Nouveaux switchs dans recalbox.conf :
* Activation/désactivation de samba
* Activation/désactivation de ssh
* Activation/désactivation des virtual gamepads
* Activation/désactivation du recalbox manager
* Activation/désactivation de l'API recalbox
* Activation/désactivation des retroachievements
* Modification des raccourcis disponibles dans es : system.es.menu 
* Modification des raccourcis disponibles dans les ému : system.emulators.specialkeys
* Nouveau système d'updates sur branches (stable, beta, unstable) : updates.type

## Nouveaux outils : 
* recalbox api

## Corrections : 
* Support du custom ratio
