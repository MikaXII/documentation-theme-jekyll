---
layout: page
title: Home (FR)
wikiPageName: Home-(FR)
menu: wiki
---

# Bienvenue sur le wiki de recalboxOS !

## Introduction

**recalboxOS** est le système d'exploitation du projet recalbox, une console d'émulation prête à l'emploi basée sur le Raspberry Pi. Pour plus d'informations, référez-vous au site http://www.recalbox.com

**recalboxOS** utilise plusieurs éléments existants, comme [EmulationStation2](https://github.com/Aloshi/EmulationStation) en tant qu'interface, [piFBA](https://github.com/digitalLumberjack/pifba) et [RetroArch](https://github.com/libretro/RetroArch) comme émulateurs, [Raspberry Pi NOOBS](https://github.com/raspberrypi/noobs) comme système d'installation/recovery.

**recalboxOS** peut être décrit avec un mot : FACILE. Nous voulons fournir un système qui soit le plus convivial et intuitif possible. Pas besoin de modifier une multitude de fichiers de configuration ou de se connecter en SSH. Il suffit d'installer le système et de jouer.  
La configuration de l'OS se fait via un fichier unique, nommé `recalbox.conf`. Ce dernier permet une configuration fine de tous les émulateurs !

### CARACTÉRISTIQUES ###

- Les systèmes supportés : Atari 2600, Atari 7800, NES, Game Boy, Game Boy color, Game Boy Advance, Super Nintendo, Famicom Disk System, Master System, Megadrive (Genesis), Gamegear, Game and Watch, Lynx, NeoGeo, NeoGeo Pocket, FBA (subset), iMame4all (subset), PCEngine, Supergrafx, MSX1/2, PSX, Sega Cd, Sega 32X, Sega SG1000, Playstation, ScummVM, Vectrex, VirtualBoy, Wonderswan.
- Compilé avec buildroot, ce qui signifie que le système de fichier root ne pèse que 150Mo compressé.
- Le système de secours est basé sur NOOBS : possibilité de réinstaller le système directement depuis la carte SD, ou en obtenant la dernière version sur Internet.
- Support du wifi.
- Mise à jour en ligne.
- Accès via le réseau aux répertoires des roms, captures d'écran et sauvegardes des parties.
- Configuration de votre contrôleur de jeu directement depuis l'interface : une fois la configuration effectuée, elle sera compatible avec tous les émulateurs.
- Musiques de fond sur l'interface.
- Support intégré des manette PS3, Xbox360, 8BitDo et Bluetooth (associez une manette, et jouez !).
- Support en Français, Anglais, Espagnole, Allemand, Italien, Portugais et peu être d'autres à venir si vous participez.
- Interface basée sur EmulationStation2 développé par Aloshi.
- Version de FBA optimisée avec support de 4 joueurs.
- Présence des pilotes GPIO pour utiliser des contrôles arcade ou vos manettes originales Nes, Snes, Megadrive, PSX.
- Support des contrôleurs Xin-Mo 2 joueurs. 
- Gestion des favoris.
- Support de gamepad virtuel [Miroof's Virtual Gamepad](https://github.com/miroof/node-virtual-gamepads) , utilisez votre téléphone comme manette.

Suivant : [[Installation|Installation-(FR)]]
