---
layout: page
title: corruption usb (FR)
wikiPageName: corruption-usb-(FR)
menu: wiki
---


Une astuce qui peut vous aider en cas de corruption de votre support amovible.   

La commande `dmesg` a retourné une belle liste de message d'erreur sur le support amovible en fat32 suite à un débranchement sauvage.    
    
`[  270.403604] FAT-fs (sda5): error, fat_get_cluster: invalid cluster chain (i_pos 1592299) `    
   
Pour la réparer via putty en ssh lancer la commande suivante : 
La clé usb est vu en sda5.   
   

`fsck /dev/sda5`   
   
Choisir 1, et répondre y à la question.   

```   
fsck 1.42.13 (17-May-2015) 
fsck.fat 3.0.28 (2015-05-16) 
0x41: Dirty bit is set. Fs was not properly unmounted and some data may be corrupt. 
1) Remove dirty bit 
2) No action 
? 1 
  Contains a free cluster (2538261). Assuming EOF. 
  File size is 49861 bytes, cluster chain length is 0 bytes. 
  Truncating file to 0 bytes. 
Reclaimed 4 unused clusters (65536 bytes). 
Perform changes ? (y/n) y 
```
rebooter ensuite votre raspberry.
