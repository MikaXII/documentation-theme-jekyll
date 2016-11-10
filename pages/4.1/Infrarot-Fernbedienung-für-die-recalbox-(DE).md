---
layout: page
title: Infrarot Fernbedienung für die recalbox (DE)
wikiPageName: Infrarot-Fernbedienung-für-die-recalbox-(DE)
menu: wiki
---

Die _**recalbox**_ kann mit fast jeder Infrarot-Fernbedienung gesteuert werden. Diese Funktion ist für das Kodi Media Center gedacht.

**Achtung:** Erfordert _**recalbox**_ 4.0.0, oder höher.

# I. Was wird benötigt?

## A - IR-Empfänger

In erster Linie benötigt man einen IR-Empfänger: ein 38KHz TSOP4838 Modul (es funktioniert auch mit einigen anderen Modulen).

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/tsop.jpg)

## B - Jumperkabel weiblich/weiblich
Um den IR-Empfänger auf einfache Weise anschließen zu können, benötigt man noch 3 Jumperkabel.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/jumpers.jpg)

## C - Schema

Wie man den IR-Empfänger und die Jumperkabel mit dem RPI verbinden muss, zeigt das folgende Schema:

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/schema.png)

Am Ende könnte es z.B. so aussehen:

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/montage.jpg)

## D - Fernbedienung

Fast jede Fernbedienung wird unterstützt, solange sie den Standards entspricht.
Hier ein paar getestete Fernbedienungen:

- Fernbedienung einer Philips Hifi-Anlage.
- Fernbedienung eines Samsung Videorecorders.
- eine Universal-Fernbedienung.
- Fernbedienung eines Apple Computer.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/remotes.jpg)

# II. Konfiguration

## A - config.txt

Die config.txt kann wahlweise im Root der SD Karte, oder per SSH unter `/boot/config.txt` geöffnet werden.

In der config.txt sucht man folgende Zeile

`#dtoverlay = lirc-rpi` 

und entfernt die Raute (#). Danach sollte die Zeile wie folgt aussehen:

`dtoverlay = lirc-rpi`

Anschließend Speichern und das System neu starten.

## B - Konfiguration der Fernbedienung

### 1. IR Ereignisüberprüfung

Nach Prüfung, ob die Fernbedienung grundsätzlich funktioniert, wird eine Verbindung zur _**recalbox**_ hergestellt [(entweder über SSH oder direkt im Terminal)](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29).

Nun führt folgenden Befehl aus:

`lsmod`

Hier wird dann geprüft, ob folgendes Modul vorhanden ist:

`lirc_rpi`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/lsmod.png)

Nun muss der folgende Befehl ausgeführt werden:

`mode2 -d /dev/lirc0 -r -m`

Jedes Mal, wenn eine Taste auf der Fernbedienung gedrückt wird, erscheinen Zahlen auf dem Bildschirm. 

Zum Beenden drückt man: Strg+C

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/mode2.png)

### 2. Fernbedienung aufnehmen

Mit folgendem Befehl zeichnet man die IR Codes der Fernbedienung auf:

`irrecord -H default /tmp/custom.conf`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord1.png)

Die Eingabetaste zum Fortsetzen drücken

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord2.png)

Nun drückt man jeweils für etwa eine Sekunde die Tasten auf der Fernbedienung

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord3.png)

Den Namen der jeweiligen Taste der Fernbedienung gibt man anhand der unten angegebenen Namen ein und betätigt die entsprechende Taste an der Fernbedienung.

- KEY_LEFT (links)
- KEY_RIGHT (rechts)
- KEY_UP (hoch)
- KEY_DOWN (runter)
- KEY_OK (ok)
- KEY_EXIT (zurück/beenden)
- KEY_PLAY (abspielen und pause)
- KEY_STOP (stop)
- KEY_VOLUMEUP (Lautstärke erhöhen)
- KEY_VOLUMEDOWN (Lautstärke verringern)
- KEY_INFO (Anzeige von Information der aktuellen Wiedergabe)
- KEY_MUTE (Lautstärke stumm stellen)
- KEY_POWER (beenden)
- KEY_MENU (Menü)

und eventuell noch diese:

- KEY_ENTER
- KEY_DELETE
- KEY_MEDIA
- KEY_RECORD
- KEY_PAUSE
- KEY_FASTFORWARD
- KEY_REWIND
- KEY_CHANNELUP
- KEY_CHANNELDOWN
- KEY_NEXT
- KEY_PREVIOUS
- KEY_EPG
- KEY_SUBTITLE
- KEY_LANGUAGE
- KEY_ZOOM
- KEY_VIDEO
- KEY_AUDIO
- KEY_NUMERIC_1
- KEY_NUMERIC_2
- KEY_NUMERIC_3
- KEY_NUMERIC_4
- KEY_NUMERIC_5
- KEY_NUMERIC_6
- KEY_NUMERIC_7
- KEY_NUMERIC_8
- KEY_NUMERIC_9
- KEY_NUMERIC_0
- KEY_RED
- KEY_GREEN
- KEY_YELLOW
- KEY_BLUE
- KEY_PVR
- KEY_RADIO

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord4.png)

Dies kann man für alle Tasten machen oder nur für die, die man benötigt.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord5.png)

Wenn alle Tasten registriert sind, drückt man die Eingabetaste zum Fortfahren. Jetzt nimmt man eine beliebige Taste und drückt nur diese wiederholt so schnell wie möglich.

**Es muss sichergestellt sein, das die Taste nicht gedrückt gehalten wird.**

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord6.png)

Zum Schluss wird das Programm automatisch beendet.

Falls etwas schiefgelaufen ist und der Vorgang wiederholt werden muss, entfernt man die Datei mit dem Befehl

`rm /tmp/custom.conf` 

und startet dann mit 

`irrecord -H default /tmp/custom.conf`

erneut.

### 3. Konfigurationsdatei

Bearbeiten kann man die Datei via SSH mit dem Befehl

`nano /tmp/custom.conf`

und ersetzt die Zeile

`name /tmp/custom.conf`

durch

 `name customremote`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/customremote.png)

Mit folgendem Befehl wird die Datei an einen anderen Ort bewegt:

`mv /tmp/custom.conf /recalbox/share/system/.config/lirc/lircd.conf`

Nun muss _**recalbox**_, oder der lircd Dienst neu gestartet werden.

Der lircd Dienst kann mit folgendem Befehl neu gestartet werden:

`/etc/init.d/S25lircd restart`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/keeprestart.png)

### 4. Überprüfen der benutzerdefinierten Ereignisse der Fernbedienung

Mit folgendem Befehl startet man die Überprüfung:

`irw`

Wenn jetzt eine Taste auf der Fernbedienung gedrückt wird, ist eine Zeile mit dem Namen der Schaltfläche zu sehen.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irw.png)

Zum Beenden drückt man „CTRL+C“

Nun startet man Kodi und testet, ob Alles funktioniert.

# III - Erweiterte Konfiguration

## A - Lircmap.xml

Durch die Bearbeitung folgender Datei kann man das Fernbedienungs-Mapping anpassen:

`/recalbox/share/system/.kodi/userdata/Lircmap.xml`

**Achtung:** Wenn man manuell das `~/.kodi` Verzeichnis gelöscht hat und Kodi neu startet, ohne zuvor _**recalbox**_ neu zu starten, sind keine _**recalbox**_ Kodi Anpassungen, einschließlich der Lircmap.xml enthalten.

In Erwägung ziehen kann man das Kopieren der Datei von 

`/recalbox/share_init/system/.kodi/userdata/Lircmap.xml`

nach

`/recalbox/share/system/.kodi/userdata/Lircmap.xml`

## B - remote.xml

Die Zuordnung der Tasten und den Kodi-Aktionen können in dieser Datei angepasst werden:

`/recalbox/share/system/.kodi/userdata/keymaps/remote.xml`

## C - Beenden - Stop

In Kodi kann man mit „Back“ bzw. „zurück“ keinen Film anhalten. Wenn das jedoch gewünscht ist, kann man in der Datei remote.xml folgenden Abschnitt anpassen:

`"<FullscreenVideo>", "<back>Back</back>"`

ändern in 

`"<FullscreenVideo>", "<back>Stop</back>"`

## D - Lautstärke erhöhen/verringern

Dieser Punkt ist für CEC Fernbedienungen.

Falls man mit der CEC Fernbedienung die Lautstärke nicht erhöhen/verringern kann, versucht man z.B. mit folgender Anpassung in der remote.xml die Lösung zu erreichen:

`<skipplus>SkipNext</skipplus>`
`<skipminus>SkipPrevious</skipminus>`

ändern in 

`<skipplus>VolumeUp</skipplus>`
`<skipminus>VolumeDown</skipminus>`

## E - Pause auf der OK Taste

In bestimmten Skins kann es nützlich sein, die Pause Funktion „einfacher“ zu gestalten, vor Allem, wenn man eine Apple Fernbedienung nutzt:

Man öffnet folgende Datei
`~/.kodi/addons/skin.refocus/720p/VideoOSD.xml`

und sucht die folgende Zeile
`<defaultcontrol always=„true">700</defaultcontrol>`

und ändert diese in 
`<defaultcontrol always="true">705</defaultcontrol>`
