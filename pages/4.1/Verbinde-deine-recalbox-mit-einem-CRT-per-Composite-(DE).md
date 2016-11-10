---
layout: page
title: Verbinde deine recalbox mit einem CRT per Composite (DE)
wikiPageName: Verbinde-deine-recalbox-mit-einem-CRT-per-Composite-(DE)
menu: wiki
---

Wenn die _**recalbox**_ mit einem CRT verbunden werden soll, benötigt man ein Mini-Klinke -> Cinch Kabel.

![](https://cloud.githubusercontent.com/assets/21189571/18264283/a0b38416-740f-11e6-8710-7090e0304784.png)

Beachtet, dass bei Kabeln von Videokameras der Video-Ausgang auf dem rechten Audio-Stecker sein könnte (rot).

[Bearbeitet die config.txt Datei.](https://github.com/recalbox/recalbox-os/wiki/Ändern-der-config.txt-Datei-%28DE%29) Es müssen alle Zeilen die mit  `hdmi_` beginnen, kommentiert werden ( `hdmi_` -> `#hdmi_`) und anschließend muss ein `sdtv_mode` hinzugefügt werden.

Zur Verfügung stehen:

```
sdtv_mode=0      Normales NTSC 
sdtv_mode=1      Japanische Version von NTSC (kein Pedestal)       
sdtv_mode=2      Normales PAL
sdtv_mode=3      Brasilianische Version von PAL – 525/60 anstelle von 625/50, anderer Subcarrier
``` 

Zum Schluss noch `hdmi_ignore_hotplug=1` eintragen, um Composite zu erzwingen.

Die [config.txt](https://github.com/recalbox/recalbox-os/wiki/Ändern-der-config.txt-Datei-%28DE%29) für normales PAL würde dann wie folgt aussehen:

```
sdtv_mode=2
hdmi_ignore_hotplug=1
```

Dann die `recalbox.conf` bearbeiten um den `global.videomode` auf Standard (default) zu setzen.

`global.videomode=default`

Wer in den Genuss der früheren Originalgrafik kommen möchte, muss den „Smooth Filter“ und alle „shader“ ausschalten.
Dies geschieht im EmulationStation Menü unter (START -> Spieleinstellungen).
