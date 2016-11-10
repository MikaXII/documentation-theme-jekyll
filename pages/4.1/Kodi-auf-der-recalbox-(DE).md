---
layout: page
title: Kodi auf der recalbox (DE)
wikiPageName: Kodi-auf-der-recalbox-(DE)
menu: wiki
---

Kodi ist ein Media Center welches in _**recalbox**_ integriert wurde.

## Allgemein:

Hauptsächlich übernimmt Kodi die Aufgabe, die beim Nutzer vorliegenden Mediendateien zu katalogisieren, organisieren, optisch ansprechend darzustellen und auszugeben bzw. abzuspielen.
Im Unterschied zu einem reinen Mediaplayer nutzt Kodi „zusätzliche Inhalte“ aus dem Internet, um dem Nutzer einen Mehrwert zur klassischen reinen Abspielfunktionalität zu bieten:
Das Programm kann unter anderem Filmposter, Darstellerlisten, Untertitel oder Trailer abrufen.
Grundlage dafür ist die Erweiterungsmöglichkeit von Kodi mittels herunterladbarer Plugins, die von Drittanbietern zur Verfügung gestellt werden. So werden u.a. Internet-Videoportale wie YouTube, Hulu oder Veoh, ebenso die Mediatheken der ARD und des ZDF über Kodi abrufbar. Auch die Integration von Video-on-Demand-Diensten ist inzwischen durch zusätzliche Plugins möglich.

Informationen zu den einzelnen Einstellungen und Funktionen finden sich im Kodi-Wiki (englisch): [Kodi-Wiki](http://kodi.wiki)

## Kodi starten, beenden und ausblenden:

Kodi kann innerhalb der EmulationStation mit drücken der X-Taste gestartet werden.

![kodi starten_41p](https://cloud.githubusercontent.com/assets/21189571/19234422/e2638234-8eeb-11e6-94fe-23aa2ad9cbcf.png)

Die X-Taste muss nicht der X-Knopf auf dem Controller sein. Es kommt lediglich darauf an, welche Taste bei der Controller Konfiguration für das X zugewiesen wurde.

![kodi_controller_config_30p](https://cloud.githubusercontent.com/assets/21189571/19234240/9179d324-8eea-11e6-9974-620802654a8e.png)

Alternativ dazu geht es auch mit START + Auswahl des ersten Eintrags im Menü (KODI MEDIA CENTER).

![hauptmenu es kodi_36p](https://cloud.githubusercontent.com/assets/21189571/19234400/a60754fa-8eeb-11e6-8716-e20e6a51f818.png)

Zum Beenden von Kodi drückt man im Hauptmenü auf das Power-Symbol in der unteren linken Ecke.
Mit „Verlassen“ kehrt man in das EmulationStation Menü zurück.

![neu_screenshot11_30p](https://cloud.githubusercontent.com/assets/21189571/19234532/86f62bb2-8eec-11e6-8be6-6b3ae6affa5a.png)

![kodi power_112p](https://cloud.githubusercontent.com/assets/21189571/19234682/6b0dbf0e-8eed-11e6-9ecf-dbc840f10af7.png)

Falls man die Funktion der X-Taste nicht benötigt, kann man diese in den Systemeinstellungen deaktivieren.

![1 systemeinstellungen_kodi einstellungen_36p](https://cloud.githubusercontent.com/assets/21189571/19312799/47eb0218-9094-11e6-9171-91f9b18d0bd6.png)

![1 kodi mit x starten_36p](https://cloud.githubusercontent.com/assets/21189571/19312877/a14a3680-9094-11e6-9be1-848c27f6f2cd.png)

Wenn das Kodi Media Center nicht benötigt wird, kann man es auch vollständig aus dem Menü nehmen lassen. 

![1 kodi aktivieren_36p](https://cloud.githubusercontent.com/assets/21189571/19312966/0b6bc740-9095-11e6-97df-18dcb057205f.png)

## Controller-Konfiguration:

Die Zuordnung der Tasten und den Kodi-Aktionen können in dieser Datei angepasst werden:

`/recalbox/share/system/.kodi/userdata/keymaps/recalbox.xml`

Die aktuelle Standard-Konfiguration sieht wie folgt aus (auch hier gilt die jeweilige Controller-Konfiguration):

* a: Auswählen
* b: Zurück
* x: Stop
* y: Menü
* start: Pause
* select: Kontextmenü
* pageup: Nichts
* pagedown: Nichts
* l2: Nichts
* r2: Nichts
* up: Hoch
* down: Runter
* right: Rechts
* left: Links
* joystick1up: Lautstärke erhöhen
* joystick1down: Lautstärke verringern
* joystick1left: Lautstärke verringern
* joystick1right: Lautstärke erhöhen
* joystick2up: Hoch
* joystick2down: Runter
* joystick2left: Links
* joystick2right: Rechts
* hotkey: Nichts

Die vollständigen Aktionen können aus dem Kodi-Wiki entnommen werden (englisch):
[Kodi-Wiki](http://kodi.wiki/view/Keymap#Commands)

## CEC-Funktion:

Durch die Unterstützung der CEC-Funktion ist es möglich, Kodi mittels einer vorhandenen TV Fernbedienung zu bedienen.

Hier können verschiedene CEC-Funktionen konfiguriert werden:
Optionen -> Einstellungen -> System -> Eingabegeräte -> rechts auf Geräte -> CEC Adapter auswählen

![neu_screenshot6_40p](https://cloud.githubusercontent.com/assets/21189571/19235481/393744fa-8ef2-11e6-84f2-b6d8b6e0e60f.png)

![neu_screenshot7_40p](https://cloud.githubusercontent.com/assets/21189571/19235528/78015a5e-8ef2-11e6-877b-fffe337cd826.png)

![neu_cut1_60p](https://cloud.githubusercontent.com/assets/21189571/19235569/c5e357b8-8ef2-11e6-8aaa-4993257814b4.png)

![neu_cut2_60p](https://cloud.githubusercontent.com/assets/21189571/19235620/1fd37992-8ef3-11e6-9ba7-072458364456.png)

![neu_cut3_60p](https://cloud.githubusercontent.com/assets/21189571/19235691/80ba0a00-8ef3-11e6-94e7-8c14b421cdd9.png)

Näheres zu CEC findet man ebenfalls im Kodi-Wiki (englisch): [Kodi-Wiki CEC](http://kodi.wiki/view/CEC)
