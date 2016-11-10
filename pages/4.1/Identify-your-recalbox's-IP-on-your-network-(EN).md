---
layout: page
title: Identify your recalbox's IP on your network (EN)
wikiPageName: Identify-your-recalbox's-IP-on-your-network-(EN)
menu: wiki
---

### Recalbox Network Settings

**Since 3.3.0** :  
Press *Start* and go to Network Settings. The current IP is displayed here.

### Prerequisites

* Ensure that your recalbox is running and connected to the LAN with ethernet cable or wifi

> You have a doubt and your network have an access to Internet? Simply go to the menu of your recalbox then on `UPDATE SYSTEM`. If a popup menu display the message `an update is available` or `no update available` then your Recalbox have an access to the Internet and so to the LAN. If the message `Please plug a network cable` is displayed either you have no access to the Internet or you may have a router settings problem, a faulty cable or a non running wifi dongle

:warning: Be careful, the ip adress is not fixed and it may change every boot sequence. You can define one by yourself via the [[Manual IP settings (EN)]]


### with Microsoft Windows
* Launch the command `Run`
* Type `cmd` and Enter
* Once in the terminal, type `ping recalbox` then `Enter`
* You may get the following message: 

> Pinging RECALBOX with 32 bytes of data

> Reply from 192.168.0.XX: Bytes=32 time=1ms TTL=128

> Reply from 192.168.0.XX: Bytes=32 time=1ms TTL=128

> Reply from 192.168.0.XX: Bytes=32 time=1ms TTL=128

> Ping statistics for [...]

* You have your IP adress

### with Apple OSX
* Launch the ‘Terminal'
It is located in the folder ‘Utilities’ of the ‘Applications’ folder
* Type there `arp -a`
* The list of all devices connected to the network in IP list form is displayed
* Raspberry IP is often `192.168.0.X` form
* You have your IP adress

### Others solutions
* Smartphones apps are available to scan your network. Go to the store of your device to find the app of your choice.
* Another solution consist in going to the router settings of your ISP box. The list of connected devices is available.
