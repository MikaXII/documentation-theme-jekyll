---
layout: page
title: Audio HiFiBerry (DE)
wikiPageName: Audio-HiFiBerry-(DE)
menu: wiki
---

# Allgemein  
Um dem Raspberry Pi ein hochwertiges Audiosignal zu entnehmen, kann eine HiFiBerry DAC (Digital-Analog-Converter) Audiocard verwendet werden. Die DACs werden in verschiedenen Versionen angeboten:

**Raspberry Pi A+, B+, 2 und 3**
- DAC+ Light
- DAC+ Standard RCA
- DAC+ Standard Phone
- DAC+ Pro

**Raspberry Pi A und B**
- DAC Standard version with RCA connectors

Die Eigenschaften der verschiedenen Versionen können unter **[hifiberry.com](http://www.hifiberry.com)** nachgeschaut werden.
Die DAC+ Boards können ohne weiteren Aufwand direkt auf die GPIO Pins gesteckt werden. Diejenigen Pins, die nicht vom DAC+ benötigt werden, können weiterhin für andere Anwendungen benutzt werden. Dazu müssen auf dem DAC+ Board weitere Header angelötet werden. In der Abbildung unten ist ersichtlich welche GPIOs benötigt werden.

![hifiberry](https://cloud.githubusercontent.com/assets/17233889/16976447/3755fcc8-4e4f-11e6-847b-1233d687ffd7.png)

Die DAC Version für die Raspberry Modelle A und B hingegen werden auf den P5 Header gesteckt. Dazu muss aber zusätzlich ein 8-Pin Header auf dem Board angelötet werden.
Sobald das DAC Board montiert ist, müssen ein paar wenige Einstellungen in der Software vorgenommen werden, damit alles wie gewünscht funktioniert.

# Device-Tree und Config
Mit Linux 3.18 (oder höher) gibt es eine neue Art Geräte-Treiber zu laden: «device tree overlay». Dies spielt eine grosse Rolle für die Konfiguration der HiFiBerry DAC Boards. Hierzu muss lediglich die _/boot/config.txt_ bearbeitet und folgende Zeile hinzugefügt (an einer beliebigen Stelle), oder abgeändert werden: 

**DAC/DAC+ Light**
- `dtoverlay=hifiberry-dac`

**DAC+ Standard/Pro**
- `dtoverlay=hifiberry-dacplus`

Anschließend muss die **_default_** Soundkarte noch ausgewählt werden. Dazu muss die Datei _/etc/asound.conf_ mit folgendem Inhalt erstellt werden:

`pcm.!default {`  
`type hw card 0`  
` } `  
`ctl.!default {`  
`type hw card 0`  
` } `  

Führe danach einen Neustart durch. 

Nun sollte das HiFiBerry als Standard Soundkarte ausgewählt sein und du darfst endlich guten Stereosound aus deiner Raspberry-Pi Audiobuchse geniessen.

**WICHTIG:** Die Audiolautstärke kann danach **NICHT** mehr über das EmulationStation Menü verändert werden. Das geht nur noch über _Alsamixer/Amixer_.

# Alsamixer/Amixer
ALSA-Soundkarten, wie das HiFiBerry, können über die beiden Werkzeuge Alsamixer und Amixer angesteuert werden. Während Alsamixer dem Benutzer eine graphische Oberfläche zur Verfügung stellt, auf der sich die verschiedenen Regler der Soundkarte schnell und einfach bedienen lassen, ist Amixer ein textbasiertes Werkzeug mit dem sich sehr gut eigene Skripte schreiben lassen.

Da in Recalbox **alsa-utils** bereits installiert ist, lässt sich das HiFiBerry ohne weiteren Aufwand damit konfigurieren.

**WICHTIG:** Das DAC+ Light Board sowie die alten DAC besitzen **KEINE** ALSA mixer controls. 

Mit dem Befehl `amixer` zeigt dir die Konsole alle verfügbaren Regler an, die das HiFiBerry besitzt. Um die Lautstärke zu ändern wird am besten der Master-Control (Gesamtlautstärke) verändert. Dieser heisst je nach HiFiBerry Board anders: ‘PCM’, ‘Digital’, ‘Master’ (Einfach ausprobieren, oder mit Alsamixer von Hand die verfügbaren Regler verstellen bis der Master gefunden ist).

Über das Terminal kann dann die Lautstärke folgendermassen geändert werden:

- `amixer sset ‘Master’ -- 90%` (in Prozent, funktioniert nicht gut da die Lautstärkeskala logarithmisch ist und die Prozent gaukeln etwas Lineares vor -> nicht zu empfehlen) oder
- `amixer sset ‘Master’ -- -3dB` (in Dezibel, dB ist die sinnvollste Einheit für Audio -> empfohlen) oder
- `amixer sset ‘Master’ – 2000` (fixe Hardwarewerte, jeder Regler hat einheitslose Limits (je nach Reglertyp verschieden) mit denen ebenfalls gearbeitet werden kann -> nicht zu empfehlen.

Daneben gibt es natürlich noch viele weitere Befehle um mit den verschiedenen Regler zu arbeiten. Mehr Infos gibt es bei Google unter **amixer**, **alsamixer** 

Um in einem eigenen Skript die Lautstärke zu verändern, kann das folgendermassen gelöst werden (Es gibt auch viele andere Lösungen, aber dieser funktioniert zuverlässig):

Zuerst importiere call von subprocess:  
`from subprocess import call`

Danach rufe den folgenden Befehl auf (hier wird mit dB gearbeitet, der Master ist hier _«Digital»_)  
`call(["amixer", "sset", "Digital", "--", str(Deine Gewünschte Lautstärke )+"dB"])`

Diese Skript-Zeile kann nun z.B. in Verbindung mit GPIO Eingängen verwendet werden um die Lautstärke per Knopfdruck zu verstellen.
   
   
**Hier noch eine Zusammenfassung verschiedener Angaben für diverse Steuerungselemente (Kommandozeilen-Befehle):**
 
- `amixer sset 'PCM' 70%` (Prozentangaben)
- `amixer sset 'Master' 3dB` (Dezibel-Angaben)
- `amixer sset 'Mic' 4` (Fixe Hardware-Werte (ergeben sich aus den Limits))
- `amixer sset 'PCM' 10%+` (Relative Angaben mit + und - als Suffix zu den Prozent-, dB- oder Hardwarewerten)
- `amixer sset 'Line' cap` (Aufnahme an/aus: cap, nocap)
- `amixer sset 'Mic' mute`  (Wiedergabe an/aus: mute, unmute)
- `amixer sset 'Master' off` (An/Aus: on/off)
- `amixer sset 'Mic Select' 'Mic1'` (Gerätenamen (ergeben sich aus den items))

Siehe auch: **[wiki.ubuntuusers.de/amixer](https://wiki.ubuntuusers.de/amixer/)**
