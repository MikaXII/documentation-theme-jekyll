---
layout: page
title: Einfache Arcade auf der recalbox (DE)
wikiPageName: Einfache-Arcade-auf-der-recalbox-(DE)
menu: wiki
---

## Einleitung (**_recalbox_** 3.3.0b17)

Diese Seite ist Neulingen gewidmet, um ihnen den Einstieg für das Spielen von Arcade – Games auf der **_recalbox_** zu erleichtern.

Arcade war lange Zeit das Komplizierteste in der Welt der Emulation aufgrund der sehr eigenen Arbeitsweise: Arcade – Maschinen benutzen nicht alle dieselbe Hardware. Darum müssen alle Spiele unabhängig voneinander emuliert werden.
Stell dir vor du willst fünf verschiedene Arcade – Games spielen. Du müsstest dazu fünf verschiedene Hardware – Emulatoren benutzen, wobei für das Spielen von fünf verschiedenen SNES – Games lediglich ein einziger SNES – Emulator benötigt wird.
Genau aus diesem Grund wurde MAME entwickelt: MAME ist eine Art Meta – Emulator. Dieser bringt die gesamte emulierte Hardware von Arcade – Maschinen in ein einziges System. Dies macht es einfacher für den Benutzer Arcade – Games zu spielen ohne Grundwissen über die benutzte Arcade – Maschine auf welcher das jeweilige Spiel gestartet wird. Jedoch ist das nicht bloss ein kleines «Feature» und genau deswegen ist MAME etwas kompliziert zu benutzen.




### Allgemeine MAME Grundsätze

Es gibt lediglich zwei Hauptgrundsätze die man wissen muss um ein gutes Verständnis für die Benutzung von MAME auf der **_recalbox_** zu haben: _ROM – Sets_ und _BIOS / Treiber_ – Dateien.

### ROM - Sets

Ein ROM – Set ist ein Set von allen verschiedenen Spielen (ROMs) welche durch eine Version von MAME emuliert werden. 

Ein ROM – Set beinhaltet sogenannte Urheber - ROMs welche der 'Hauptversion' des Spiels entsprechen und sogenannte Klon – ROMs welche eine 'Alternativversion' des Hauptspiels bilden. Wie du dir denken kannst werden wir in den meisten Fällen alle Klon – ROMs entfernen und nur die Haupt- oder Urheberversionen verwenden.

Der meiste Code, der verwendet wird um diese ROMs spielbar zu machen, ist im MAME -Emulator enthalten. Leider bedeutet dies, dass es eine starke und enge Beziehung zwischen einer MAME Version und einer Spiel – ROM Version. Das bedeutet, wenn MAME eine neue Version veröffentlicht müssen die Spiel – ROMs möglicherweise auf die neue Emulator-Version aktualisiert werden.

Um es einfach zu halten: Wenn Sie einen bestimmten MAME -Emulator verwenden, sagen wir Version 0.78, müssen Sie auch explizit die 0.78 -Version des ROM - Sets verwenden. Es ist möglich, dass einige Spiele aus einem anderen ROM - Set mit Ihrer Version funktionieren. **Der einzige Weg aber, um wirklich sicher zu sein, dass die meisten Spiele funktionieren, ist, eine MAME Version in Verbindung mit einem ROM - Set der gleichen Version zu verwenden**.

Für aktuelle Versionen (wie z.B. jene die von fba_libreto benutzt wird, siehe unten) gibt es immer weniger Modifikationen der Spiel - ROMs. So ist es gut möglich, ein älteres ROM – Set zu benutzen und trotzdem sind die meisten Spiele lauffähig. 

### BIOS / Treiber
Gewisse ROMs eines ROM – Sets benötigen zustätzliche BIOS – Dateien. Die meistbekannten Fälle sind NeoGeo – Spiele. Lass uns das als Beispiel etwas näher betrachten:
Falls du NeoGeo – Spiele benutzen willst, ist es wichtig, die benötigte BIOS / Treiber – Datei (in diesem Fall neogeo.zip) in den gleichen Ordner wie das Spiel selber zu kopieren. Das ist alles.
Hast du verschiedene Unterordner für die Spiele erstellt (z.B. nach Genre oder Hardware sortiert), die BIOS / Treiber – Datei muss in jeden Ordner kopiert werden in denen sich Spiele befinden die diese Datei benötigen. **Aufgrund der Tatsache, dass diese Dateien sehr klein sind, empfiehlt es sich alle von ihnen in jeden der Unterordner zu kopieren**.
Wo sind diese BIOS / Treiber – Dateien zu finden? Das ist sehr einfach: Sie sind alle im ROM – Set inbegriffen.
Falls nun ein Spiel nicht startet oder sofort wieder zum EmulationStation Bildschirm zurückkehrt, ist es möglich, dass einfach die BIOS / Treiber – Datei fehlt. Einfach die zum Spiel zugehörige Datei suchen und in den entsprechenden Ordner kopieren.

## Arcade – Emulation auf der **_recalbox_**

Wie die [[Fortgeschrittene Arcade auf der recalbox|Fortgeschrittene-Arcade-auf-der-recalbox-(DE)]] Wikiseite für **_recalbox_** erklärt, sind verschiedene Arcade – Emulatoren im **_recalboxOS_** inbegriffen.
Bereits zwei von ihnen reicht, um die Mehrheit aller Arcade – Spiele auf dem Raspberry Pi zu benutzen.
Diese zwei Systeme sind:

* MAME
  * _MAME/ROM - Set Version:_ 0.78
  * _Ordner für die ROMs:_ mame

* FBA_libretro
  * FBA ist eine Art von alternativer Version von MAME (Es werden weniger Arcade – Maschinen emuliert), verfolgt jedoch exakt die gleichen Grundsätze welche bereits erwähnt wurden.
  * _MAME/ROM – Set Version:_ 0.167
  * _Ordner für die ROMs:_ fba_libretro

Gewisse Spiele auf der **_recalbox_** funktionieren nur mit MAME, andere wiederum nur mit FBA_libretro.

Benutze als Richtlinie bitte das [BestArcade4Recalbox] (https://docs.google.com/spreadsheets/d/1F5tBguhRxpj1AQcnDWF6AVSx4av_Gm3cDQedQB7IECk/edit?usp=sharing) Dokument, um den richtigen Emulator für jedes Spiel zu erhalten.

## Lass uns **_recalbox_** konfigurieren
Lade dir zuerst die ganzen ROM – Sets für beide Emulatoren herunter: ROM – Set 0.78 für MAME und ROM – Set 0.167 für FBA_libretro (Alternativ sollte hier auch 0.161 funktionieren).  
Falls du die benötigten Versionen der ROM – Sets nicht finden kannst, so kannst du eine höhere (neuere) Version herunterladen und mit der folgenden Anleitung “bereinigen”: https://github.com/recalbox/recalbox-os/wiki/Pr%C3%BCfen-von-ROM-Versionen-mit-clrmamepro-%28DE%29   

Du kannst auch alle Spiele einzeln herunterladen, da ganze ROM – Sets ziemlich gross sind. Jedoch ist es nicht einfach einzelne Spiele zu finden und sicher sein, dass diese auch in der richtigen Version sind.
Deshalb die Empfehlung nur ganze ROM – Sets herunterzuladen um Kopfschmerzen zu vermeiden.   

Nun bist du nur noch wenige Schritte davon entfernt, hervorragende Arcade – Games auf deiner **_recalbox_** zu spielen.

### Kopieren von BIOS / Treibern
Zuerst müssen wir noch die BIOS / Treiber – Dateinen von den ROM – Sets kopieren. Im Gegensatz zu anderen Systemen dürfen diese nicht in den BIOS – Ordner kopiert werden sondern in den ROM – Ordner in dem auch die Spiele selber liegen.

* In deinem MAME 0.78 ROM – Set findest du die folgenden BIOS / Treiber – Dateien. Kopiere sie in den MAME ROM – Ordner:   
   
_acpsx.zip, cpzn1.zip, cpzn2.zip, cvs.zip, decocass.zip, konamigx.zip, megaplay.zip, megatech.zip, neogeo.zip, nss.zip, pgm.zip, playch10.zip, skns.zip, stvbios.zip, taitofx1.zip, tps.zip_

* In deinem FBA_libretro 0.167 or 0.161 ROM – Set findest du die folgenden BIOS / Treiber – Dateien. Kopiere sie in den FBA_libretro ROM – Ordner. Es kann sein, dass du nur die zwei folgenden benötigst:   
   
_neogeo.zip_ and _pgm.zip_

### Spiele kopieren

* Überprüfe das Dokument [BestArcade4Recalbox] (https://docs.google.com/spreadsheets/d/1F5tBguhRxpj1AQcnDWF6AVSx4av_Gm3cDQedQB7IECk/edit?usp=sharing) und schaue, welches System sich am besten eignet für das Spiel das du spielen möchtest.
  * Befindet es sich im MAME Tab, so kopiere die ROM – Datei des Spiels von deinem ganzen 0.78 ROM – Set in den MAME ROM – Ordner.
  * Befindet es sich im FBA_libretro Tab, so kopiere die ROM – Datei des Spiels von deinem ganzen 0.167 ROM – Set (oder 0.161 oder ein anderes das ähnlich ist) in den FBA_libretro ROM – Ordner.
  * Befindet es sich im «Nicht gefunden» oder «Funktioniert nicht» Tab, hat sich die Sache leider bereits von alleine erledigt.   

* Zeit um zu spielen! (Oder nicht)

## Weitere Tipps

* Wenn du die BIOS – Dateien in EmultationStation verbergen willst, bearbeite die Metadaten davon im Menü (Select). 
(Dies funktioniert im Moment leider nicht mehr in der Version 4.0.0: Benenne die BIOS – Dateien mit einer .ZIP – Endung (In Grossbuchstaben) und entferne die Benutzung von .ZIP – Dateien für die betroffenen Arcade – Systeme in es_system.cfg.
* Erinnerung: Wenn du Unterordner in deinen ROM – Ordner benutzen willst, kopiere die BIOS / Treiber – Dateien in jeden Unterordner und verschiebe dein Spiel dann ebenfalls in den Unterordner.
* Weitere Infos gibt es hier: [[Fortgeschrittene Arcade auf der recalbox | Fortgeschrittene-Arcade-auf-der-recalbox-(DE)]]
