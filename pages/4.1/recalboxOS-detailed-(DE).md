---
layout: page
title: recalboxOS detailed (DE)
wikiPageName: recalboxOS-detailed-(DE)
menu: wiki
---

**_recalboxOS_** ist ein Open Source Betriebssystem. Es ist eine auf Linux basierende Distribution, optimiert für den ARM Prozessor des Raspberry Pi.

## Buildroot
**_recalboxOS_** ist kompiliert mit Buildroot.

Buildroot ist ein einfaches, effizientes und leicht zu handhabendes Werkzeug, um durch Cross-Kompilierung eingebettete Linux Systeme zu generieren. Es kompiliert alle _**recalboxOS**_ Systeme und Software aus den Quellen und kreiert die Archive, die bei der Installation in Deine SD-Datei kopiert werden.

Es kreiert ein minimales, eingebettetes Linux System, exakt übereinstimmend mit dem was Du auf Deinem System willst.
Aus diesem Grund gibt es keinen Paket-Manager, keinen Kompilierer, keine Headers etc. in recalbox.

## Projekte
**_recalboxOS_** ist das Haupt-Projekt, bestehend aus 3 Unter-Projekten, die das System bilden :

- **_recalbox_-buildroot** :
https://github.com/digitalLumberjack/recalbox-buildroot (branch unified)
Das _**recalbox**_-buildroot Projekt ist ein "Buildroot" System. Es erstellt ein komplettes Linux Betriebssystem, dass auf _**recalbox**_ lauffähig ist. Du kannst dieses Projekt kompilieren, dann die Ausgabe-Dateien auf eine manuell formartierte SD-Karte kopieren, um das System auf einem Raspberry Pi zu starten. Es gibt aber noch einen besseren Weg, das recalbox-rescue System.

- **_recalbox_-rescue** :
https://github.com/digitalLumberjack/recalbox-rescue (branch dual)
Basierend auf dem grandiosen NOOBS vom RPI Team, ermöglicht Dir das _**recalbox**_-rescue System eine einfache Installation von _**RecalboxOS**_ und einer Rettungs-Partition auf Deiner SD-Karte. Es ist ein anderes, kleines Betriebssystem, welches retroboxOS runterlädt, Deine SD-Karte formatiert und das System für Dich installiert.
Bevor die SD-Karten Version installiert wird, wird überprüft, ob eine neue Version im Internet verfügbar ist. 

- **_recalbox_-emulationstation** :
https://github.com/digitalLumberjack/recalbox-emulationstation/tree/recalbox-buildroot
Basierend auf dem grandiosen EmulationStation2 von Aloshi, wurde das Front-End ein wenig modifiziert, um ogg Hintergrundmusik, Sprachauswahl, Update Unterstützung und Controller-Konfiguration zu ermöglichen.

- **_recalbox_-configgen** :
https://github.com/digitalLumberjack/recalbox-configgen
Das automatische Emulator Konfigurations-Werkzeug.

Wenn Du näher darauf eingehen willst und lernen möchtest wie _**recalboxOS**_ kompiliert und modifiziert wird, dann springe zu [[Kompilation & Modifikationen|Kompilation-&-Modifikationen-(DE)]]

## Partitionen
Das _**recalboxOS**_ ist so konfiguriert, um auf 3 Partitionen zu laufen :
- Die 1. Partition vom Typ FAT32, heißt BOOT, mounted in /boot im System, beinhaltet alle Boot-Dateien 
- Die 2. Partition vom Typ EXT4, heißt root, mounted in /System, beinhaltet alle System-Dateien
- Die 3. Partition vom Typ FAT32, heißt SHARE, mounted in /recalbox/share im System, beinhaltet alle Roms, BIOS, Saves, Screenshots etc..
