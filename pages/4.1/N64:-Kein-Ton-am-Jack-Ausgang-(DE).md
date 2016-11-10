---
layout: page
title: N64: Kein Ton am Jack Ausgang (DE)
wikiPageName: N64:-Kein-Ton-am-Jack-Ausgang-(DE)
menu: wiki
---

Wenn Du den Jack Ausgang (die Ausgabe mit einem Klinkenstecker) des RPi`s verwendest, und kein Ton vorhanden ist, befolge diese Anweisungen.

Du benötigst [Root-Zugriff auf dem Terminal](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29)

Bearbeite die mupen64plus Konfigurationsdatei mit folgendem Befehl:

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Dann diese Zeile ändern

vorher

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 1
```

nachher

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 0
```

Drücke `STRG + X`, um den Editor zu beenden, und dann `Y`, um die Änderungen zu speichern.

Nach einem Neustart des Systems sollte die Tonausgabe nun funktionieren.

