---
layout: page
title: Sicherungskopie deiner Scrapes (DE)
wikiPageName: Sicherungskopie-deiner-Scrapes-(DE)
menu: wiki
---

Um ein **Backup**, oder eine **Wiederherstellung**, deiner Scrapes zu machen, brauchst du zuerst [Root-Zugang](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29) auf deiner ***recalbox***.  
Windows-Benutzer können dazu [Putty](http://www.putty.org/) und [WinSCP](https://winscp.net/eng/download.php) benutzen.  

##Backup

1. Erstelle ein Backup-Verzeichnis auf deiner ***recalbox*** mit folgendem Befehl:

`mkdir /recalbox/share/system/backup_scrape/` 
   
2. Benutze den folgenden Befehl um deine Scrape-Verzeichnisse in die _share_-Partition deiner ***recalbox*** zu kopieren:

`cp -r /root/.emulationstation/downloaded_images /recalbox/share/system/backup_scrape/ && cp -r /root/.emulationstation/gamelists /recalbox/share/system/backup_scrape/`  
  
**Hinweis:** Abhängig von der Menge der Scrapes die Du gemacht hast, kann es einige Zeit dauern bis alles kopiert wurde. Bitte sei deshalb geduldig und warte bis der Vorgang erfolgreich abgeschlossen wurde.  
  
3. Navigiere nun auf deiner ***recalbox*** in das `backup_scrape`-Verzeichnis im `system`-Ordner und kopiere den Inhalt auf deinen Computer, oder auf ein Speichermedium deiner Wahl.  
  
##Wiederherstellung

1. Um das Backup deiner Scrapes auf deiner ***recalbox*** **wiederherzustellen**, kopiere dein lokales Backup in das `backup_scrape`-Verzeichnis im `system`-Ordner auf deiner ***recalbox***. Führe dann folgenden Befehl aus:  
  
`cp -r /recalbox/share/system/backup_scrape/downloaded_images /root/.emulationstation/ && cp -r /recalbox/share/system/backup_scrape/gamelists /root/.emulationstation/`  
  
**Hinweis:** Abhängig von der Menge der Scrapes die Du gemacht hast, kann es einige Zeit dauern bis alles kopiert wurde. Bitte sei deshalb geduldig und warte bis der Vorgang erfolgreich abgeschlossen wurde.  
  
2. Starte deine ***recalbox*** neu sobald der Kopiervorgang beendet wurde. Deine Scrapes sollten nun erscheinen.  
