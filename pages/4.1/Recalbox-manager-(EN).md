---
layout: page
title: Recalbox manager (EN)
wikiPageName: Recalbox-manager-(EN)
menu: wiki
---

The new feature [recalbox-manager](https://github.com/sveetch/recalbox-manager) (since 3.3b12), is a web interface to manage your recalbox.
It's created to give at all users (beginners or not) a better way to configure the Recalbox.

How to use it :
- Open your favorite browser
- go to : `http://[ip of the recalbox]`
- And you are on the main page of the manager

The most common configuration of routers, you must find your recalbox between 
`192.168.1.2` and `192.168.1.254`

When you are on the main page you can navigate with the following menus :

- Editing recalbox.conf
- Upload/Delete bios
- upload/Delete roms 
- See log

By default the manager start automatically at startup. If you want you can disable it in recalbox.conf
```
## Recalbox Manager (http manager)
system.manager.enabled=1
```
