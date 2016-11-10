---
layout: page
title: Eine Partition beschreibbar machen (DE)
wikiPageName: Eine-Partition-beschreibbar-machen-(DE)
menu: wiki
---

Seit _**recalboxOS**_ 4.0.0 ist das System nur lesbar (read-only).

Um trotzdem Änderungen am System machen zu können, gibt man via [SSH](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29) folgendes ein:

Für die Boot-Partition: `mount -o remount,rw /boot`

Für die System-Partition: `mount -o remount,rw /`


Beim nächsten Neustart ist das System erneut nur lesbar (read-only).


### Mit WinSCP:

![winscp_60p](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/WinSCP.PNG)
