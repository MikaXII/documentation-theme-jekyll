---
layout: page
title: Backup your scrape (EN)
wikiPageName: Backup-your-scrape-(EN)
menu: wiki
---

**Only until Recalbox 3.3.0 beta 17**

**- To backup** your scrape you must have [root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29).  For Windows users, using [WinSCP] (https://winscp.net/eng/download.php) can be a huge help.   
<br>
Create this needed directory :

`mkdir /recalbox/share/system/backup_scrape/`

Use the following command to backup your scrape directories to the share partition.

`cp -r /root/.emulationstation/downloaded_images /recalbox/share/system/backup_scrape/ && cp -r /root/.emulationstation/gamelists /recalbox/share/system/backup_scrape/`

***Depending of the total amount of scrapes you have collected can delay the appearance that the backups completed.  Please be patient.***

Next go to the 'backup_scrape' directory in `system` then copy the contents of the 'backup_scrape' to your PC or local storage.
<br>
<br>
<br>
<br>
**- To restore** this backup on your recalbox's system, add your backup in the 'backup_scrape' directory in the `system` folder then use the following command.

`cp -r /recalbox/share/system/backup_scrape/downloaded_images /root/.emulationstation/ && cp -r /recalbox/share/system/backup_scrape/gamelists /root/.emulationstation/`

Once the copy is done, reboot your recalbox, and your scrapes will appear.
