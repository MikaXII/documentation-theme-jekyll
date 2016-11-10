---
layout: page
title: Releases (DE)
wikiPageName: Releases-(DE)
menu: wiki
---

## Verzweigungen
Die recalbox-buildroot git Verzweigungen sind folgendermassen aufgebaut:
- Der **unstable**-Zweig für eine Version ist die aktuellste Version: _recalbox-unstable-build-XXX/_. Der neue Code wird auf diesen Zweig geschoben.
- Wenn eine Version Beta oder Stable – Status bekommt, wird sie in das jeweilige Verzeichnis verschoben und bekommt eine neue Bezeichnung z.B. _4.0.0-beta3/_.

## Versionen und Veröffentlichungen
- Die **_unstable_**-Versionen (Instabil) werden jede Nacht auf dem aktuellen _unstable_ Zweig erzeugt.
- Die **_beta_**-Abbilder (Beta) werden mit der aktuellsten _unstable_ Version erzeugt, welche getestet wurden und funktionsfähig sind.
- Die **_stable_**-Abbilder (Stabil) werden mit einem _beta_-Abbild erzeugt, welches ein geeigneter Kandidat für eine stabile Veröffentlichung ist.

## Recalbox-Updates
Die Updates für das recalboxOS können über eine von drei Ebenen vorgenommen werden. Dazu muss der Parameter `updates.type` der `recalbox.conf` – Datei folgendermassen konfiguriert werden:
- `stable`, 
- `beta` oder
- `unstable`

## Recalbox-Archiv
Das Archiv http://archive.recalbox.com/4/ enthält die folgenden Dateien:

- rpi1/
    - stable/
        - last -> Link zur aktuellen Stabil-Veröffentlichung
    - beta/
        - last -> Link zur aktuellen Beta-Veröffentlichung
    - unstable/
        - last -> Link zur aktuellen Instabil-Veröffentlichung
        - recalbox-unstable-build-XXX/ -> Link zu den täglichen Instabil-Versionen (Siehe Datum).
- rpi2/
    - stable/
        - last -> Link zur aktuellen Stabil-Veröffentlichung
    - beta/
        - last -> Link zur aktuellen Beta-Veröffentlichung
    - unstable/
        - last -> Link zur aktuellen Instabil-Veröffentlichung
        - recalbox-unstable-build-XXX/ -> Link zu den täglichen Instabil-Versionen (Siehe Datum).
- rpi3/
    - stable/
        - last -> Link zur aktuellen Stabil-Veröffentlichung
    - beta/
        - last -> Link zur aktuellen Beta-Veröffentlichung
    - unstable/
        - last -> Link zur aktuellen Instabil-Veröffentlichung
        - recalbox-unstable-build-XXX/ -> Link zu den täglichen Instabil-Versionen (Siehe Datum).

Der Parameter `system.updates.version` definiert den Verzeichnispfad in dem das Update gesucht wird. Danach wird die `recalbox.version` – Datei in jedem Verzeichnis verglichen mit der lokalen (Auf deiner recalbox) `recalbox.version` - Datei.
