---
layout: page
title: Netzwerk Zugriff mit WinSCP (DE)
wikiPageName: Netzwerk-Zugriff-mit-WinSCP-(DE)
menu: wiki
---

##Voraussetzungen
* Stelle sicher, dass deine ***recalbox*** läuft und mit deinem lokalen Netzwerk, entweder via Ethernet-Kabel oder mit WiFi, verbunden ist.  
  
> Du bist nicht sicher ob deine ***recalbox*** mit dem Internet verbunden ist? Das kannst du sehr einfach überprüfen indem du in das HAUPTMENÜ -> NETZWERKEINSTELLUNGEN gehst. Dort wird dir der Internetstatus angezeigt (Verbunden oder Nicht verbunden). Ebenfalls dort siehst du die IP-Adresse deiner ***recalbox***.  
  
* Lade dir WinSCP herunter und installiere es. Wähle bei der Frage zur Benutzerschnittstelle  `Commander` aus. So zeigt dir WinSCP später auf der linken Seite deinen lokalen PC an und auf der rechten das entfernte Remote-Verzeichnis (z.B. deine ***recalbox***).  
  
 - Für [Windows](http://winscp.net/)
 - Für [Mac OS X](http://www.mediafire.com/download/w5d794zbnwv3dkj/WinSCP.zip) (:warning: Sei vorsichtig. Diese Version ist nicht offiziell, sondern eine für OS X abgeänderte Windows-Version von 2011. Eine kommerzielle Software für OS X ist [rbrowser](http://www.rbrowser.com/)).  
  
* Optional: Die IP-Adresse deiner ***recalbox***. Befolge den folgenden Wiki-Artikel, wenn du nicht weisst, wo du die IP-Adresse herbekommst:  [[Erhalte die IP-Adresse deiner recalbox in deinem Netzwerk|https://github.com/recalbox/recalbox-os/wiki/Erhalte-die-IP-deiner-recalbox-in-deinem-Netzwerk-%28DE%29]].  
  
##Konfiguration 
**1.** Starte `WinSCP`  
  
**2.** Falls das «Anmeldung»-Fenster nicht automatische erscheint, klicke auf `Neue Sitzung`  
  
**3.** Tippe die folgenden Informationen ein:  
 - Übertragungsprotokoll `SCP`
 - Rechnername `recalbox` oder die IP-Adresse die du vorhin in Erfahrung gebracht hast. Die Konfiguration muss bei einem Neustart von ***recalbox*** jedes Mal neu vorgenommen werden, wenn du die IP-Adresse eingegeben hast.
 - Port Nummer `22`
 - Benutzername `root`
 - Kennwort `recalboxroot`
 - Speichere nun die Änderungen  
  
**4.** Es öffnet sich ein Fenster wo du deiner Sitzung einen Namen deiner Wahl zuordnen kannst z.B. `Recalbox`. Darunter kannst du noch einen Haken bei `Passwort speichern (nicht empfohlen)` setzen.   

**5.** Die Software ist nun konfiguriert. 
   
**6.** Auf der linken Seite im Fenster siehst du nun alle deine konfigurierten Verbindungen. Wähle deine ***recalbox***-Verbindung an und drücke auf «Verbinden».  
  
**7.** Falls du den Haken bei **Punkt 4** nicht gesetzt hast, öffnet sich ein Infofenster, mit der Meldung `Passwort eingeben`. Gebe hier erneut `recalboxroot` ein und drücke OK.
    
**8.** Du bist jetzt verbunden.  
  
**9.** Navigiere zu `Einstellungen` und danach zu `Listenfenster` und setze einen Haken bei `Versteckte Dateien anzeigen`. Dies ist nützlich um den Ordner `.emulationstation` zu öffnen, um z.B. Themes zu bearbeiten.  

##Benutzung
Die Benutzung von WinSCP ist sehr intuitiv. Standardmässig findest du deinen Computer auf der linken und deine ***recalbox*** auf der rechten Seite (mit der Einstellung `Commander`).  

####Noch ein paar Tipps  
  
* Um einen Ordner zurückzugehen, kannst du oberhalb des Verzeichnisses (blaue Leiste) auf den jeweiligen Ordner drücken um zu dieser Ebene zu gelangen. Befindest du dich z.B. im Verzeichnis `/recalbox/scripts/moonlight` kannst du z.B. auf `recalbox` klicken um zwei Ordnerebenen zurück zu gehen.  

* Du kannst Ordner zwischen dem lokalen und dem remote Verzeichnis per _Drag and Drop_ verschieben.  

* Eigenschaften eines Ordners oder einer Datei kannst du mit Rechtsklick und dann `Eigenschaften` individuell verändern.  
