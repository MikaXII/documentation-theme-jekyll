---
layout: page
title: Overscan Einstellungen (DE)
wikiPageName: Overscan-Einstellungen-(DE)
menu: wiki
---

Die Overscan Option kann aktiviert werden, wenn ein schwarzer Rand um das angezeigte Bild zu sehen ist, oder ein abgeschnittenes Bild angezeigt wird.

Der Overscan lässt sich aus EmulationStation heraus aktivieren und befindet sich im Menü unter „UI Einstellungen“.  
Die Änderung wird erst nach einem Neustart des RPi wirksam.

Die Overscan Optionen wurden von NOOBS bei der Erstinstallation gesetzt. Wenn die gesetzten Werte jedoch nicht dem Bildschirm entsprechen, können die Werte in der [config.txt](https://github.com/recalbox/recalbox-os/wiki/Ändern-der-config.txt-Datei-%28DE%29) geändert werden.

`disable_overscan=0`                                                
`overscan_left=24`                               
`overscan_right=24`      
`overscan_top=24`   
`overscan_bottom=24`

Der Wert gibt die Anzahl der zu überspringenden Pixel am Bildschirmrand an.

 Der Wert muss verringert werden, wenn ein schwarzer Rand zu sehen ist.                                
 Der Wert muss erhöht werden, wenn das Bild abgeschnitten (zu groß) ist.
