---
layout: page
title: Troubleshooting recalbox.log (EN)
wikiPageName: Troubleshooting-recalbox.log-(EN)
menu: wiki
---

1. First get root access (see [[Link|Root-access-on-terminal-(EN)]])
2. to get the last 100 lines from the recalbox.log execute `tail -100 /root/recalbox.log`


Here a sample an recalbox.log output with the last 10 lines:

     # tail -100 /root/recalbox.log
     ---- recalbox-config.sh ----
     wlan0 be used as wifi interface
     starting wifi
     udhcpc (v1.23.1) started
     Sending discover...
     Sending select for 192.168.12.182...
     Lease of 192.168.12.182 obtained, lease time 259200
     deleting routers
     adding dns 192.168.12.4
               inet addr:192.168.12.182  Bcast:192.168.12.255  Mask:255.255.255.0

