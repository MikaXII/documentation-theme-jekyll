---
layout: page
title: recalboxOS détaillé (FR)
wikiPageName: recalboxOS-détaillé-(FR)
menu: wiki
---

**recalboxOS** est un système d'exploitation open source. Il est basé sur une distribution Linux, optimisée pour le processeur ARM du RaspberryPI.

## Buildroot

**recalboxOS** est compilé avec buildroot.

Buildroot est un outil simple, efficace et facile à utiliser pour générer des systèmes Linux embarqués par cross-compilation. Il compile tous les logiciels et le système de recalboxOS, et créé des archives qui seront copiées sur votre carte SD lors de l'installation.

Il crée un système Linux embarqué minimal, correspondant exactement ce que vous voulez sur votre système. C'est pourquoi vous n'avez pas de gestionnaire de paquets sur recalboxOS, aucun compilateur, aucun en-tête etc ...

## Projets

**recalboxOS** est le projet principal, qui regroupe les trois sous-projets qui composent le système:

-**recalbox-buildroot** : https://github.com/digitalLumberjack/recalbox-buildroot (branche recalbox) Le projet recalbox-buildroot est le système de buildroot. Il créé l'ensemble Linux os qui sera exécuté par la recalbox. Vous pouvez compiler ce projet, puis copier les fichiers obtenu sur une carte SD formaté manuellement en fat32 afin démarrer le système sur un raspberrypi. Mais il y a une meilleur façon de faire qui se nome recalbox-rescue.

-**recalbox-rescue** : https://github.com/digitalLumberjack/recalbox-rescue (branche recalbox) 
Basé sur l'impressionnant NOOBS de la team rpi, le projet recal-box permet d'installer facilement **recalboxOS** et d'avoir une partition de secours sur votre carte SD. C'est un autre système d'exploitation minimal, qui téléchargera recalboxOS, formatera votre carte SD et installera le système pour vous. Avant d'installer recalboxOS, il vérifiera sur internet si une nouvelle version est disponible.

-**recalbox-emulationstation** : https://github.com/digitalLumberjack/recalbox-emulationstation/tree/recalbox-buildroot
Basé sur le formidable EmulationStation 2, développé par Aloshi, l'interface a été légèrement modifiée afin d'intégrer des musiques de fond au format ogg, une sélection de la langue, un support des mises à jours en ligne et la configuration des contrôleurs de jeu.

Si vous voulez aller plus loin, et apprendre comment compiler et modifier **recalboxOS**, sautez à Compilation & Modifications (lien à rajouter)

## Partitions

**recalboxOS** est configuré pour fonctionner sur trois partitions :

-La première partition de type FAT32, nommée BOOT, est montée sur le point de montage /boot et contient tous les fichiers de démarrage.

-La seconde partition de type EXT4, nommée root, est montée sur le point de montage / et contient tout le système.

-La troisième partition de type FAT32, nommée SHARE, est montée sur le point de montage /recalbox/share et contient toutes les roms, bios, sauvegardes et captures d'écran.

## Émulateurs

Voici la liste des émulateurs **recalboxOS** avec leurs systèmes:

- **FBA** : piFBA porté sur raspberrypi par Squid (https://code.google.com/p/pifba/) et modifié par digitalLumberjack (https://github.com/digitalLumberjack/pifba)
- retroarch créé par twinaphex (https://github.com/libretro/RetroArch)
- **Atari 2600** : libretro-stella (https://github.com/libretro/stella-libretro)
- **NES** : libretro-fceu-next (https://github.com/libretro/fceu-next)
- **Game Boy/Game Boy color** : libretro-gambatte (https://github.com/libretro/gambatte-libretro)
- **Game Boy Advance** : libretro-gpsp (https://github.com/libretro/gpsp)
- **Super Nintendo** : libretro-pocketsnes (https://github.com/libretro/pocketsnes-libretro)
- **Master System** : libretro-picodrive (https://github.com/libretro/picodrive)
- **Megadrive (Genesis)** : libretro-picodrive (https://github.com/libretro/picodrive)
- **iMame4all** : libretro-imame4all (https://github.com/libretro/imame4all-libretro)
- **PCEngine/PCEngine CD** : libretro-beetle-pce-fast (https://github.com/libretro/beetle-pce-fast-libretro)
- **MSX1/2** : libretro-fmsx (https://github.com/libretro/fmsx-libretro)
- **Playstation** : libretro-pcsx-rearmed (https://github.com/libretro/pcsx_rearmed)
- **Sega SG1000** : libretro-genesis-plus-gx (https://github.com/libretro/Genesis-Plus-GX)
- **Sega CD** : libretro-picodrive (https://github.com/libretro/picodrive)
- **Sega 32x** : libretro-picodrive (https://github.com/libretro/picodrive)
- **Famicom Disk System** : libretro-nestopia (https://github.com/libretro/nestopia)
