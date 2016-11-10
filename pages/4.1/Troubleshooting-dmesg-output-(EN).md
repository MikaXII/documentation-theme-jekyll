---
layout: page
title: Troubleshooting dmesg output (EN)
wikiPageName: Troubleshooting-dmesg-output-(EN)
menu: wiki
---

1. First get root access (see [[Link|Root-access-on-terminal-(EN)]])
2. unplug the usb device you have an issue with
3. execute `dmesg` (remember the last line)
4. plug the usb device
5. execute `dmesg` again
6. now you can copy & paste the needed information to the forum post or github issue



Here a sample of a Wifi Dongle:

     [    2.817251] usb 1-1.4: new high-speed USB device number 5 using dwc_otg
     [    2.918993] usb 1-1.4: New USB device found, idVendor=7392, idProduct=7811
     [    2.919019] usb 1-1.4: New USB device strings: Mfr=1, Product=2, SerialNumber=3
     [    2.919030] usb 1-1.4: Product: 802.11n WLAN Adapter
     [    2.919041] usb 1-1.4: Manufacturer: Realtek
     [    2.919052] usb 1-1.4: SerialNumber: 00e04c000001



`     
