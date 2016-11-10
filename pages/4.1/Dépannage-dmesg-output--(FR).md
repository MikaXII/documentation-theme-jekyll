---
layout: page
title: Dépannage dmesg output  (FR)
wikiPageName: Dépannage-dmesg-output--(FR)
menu: wiki
---

1. Premièrement [[obtenir un accès root | accès root sur-Terminal- (FR)]]
2. Débrancher votre périphérique usb 
3. exécuter `dmesg` (ce souvenir de la dernière ligne)
4. Brancher votre périphérique usb 
5. exécuter `dmesg`  une nouvelle fois
6. maintenant copier/coller les informations sur le forum ou ouvrer une discussion sur github issue



Voici un exemple d'un Dongle Wifi:

     [    2.817251] usb 1-1.4: new high-speed USB device number 5 using dwc_otg
     [    2.918993] usb 1-1.4: New USB device found, idVendor=7392, idProduct=7811
     [    2.919019] usb 1-1.4: New USB device strings: Mfr=1, Product=2, SerialNumber=3
     [    2.919030] usb 1-1.4: Product: 802.11n WLAN Adapter
     [    2.919041] usb 1-1.4: Manufacturer: Realtek
     [    2.919052] usb 1-1.4: SerialNumber: 00e04c000001



`     

Voici un exemple avec un Dongle Bluetooth ayant un firmware manquant : 


[  194.192286] usb 1-1.4: new full-speed USB device number 4 using dwc_otg

[  194.297324] usb 1-1.4: New USB device found, idVendor=0cf3, idProduct=3000 

[  194.297350] usb 1-1.4: New USB device strings: Mfr=0, Product=0, SerialNumber=0 

[  194.303210] usb 1-1.4: Direct firmware load for ath3k-1.fw failed with error -2 

[  194.303265] Bluetooth: Firmware file "ath3k-1.fw" not found 

[  194.303307] ath3k: probe of 1-1.4:1.0 failed with error -2
 
