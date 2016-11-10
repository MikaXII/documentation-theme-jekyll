---
layout: page
title: Manuel IP Paramètres (FR)
wikiPageName: Manuel-IP-Paramètres-(FR)
menu: wiki
---

Afin de sélectionner une adresse ip fixe pour votre recalbox, vous devrez modifier le fichier `/etc/network/interfaces`.

- [[Obtenez un accès root via Terminal | accès root sur-Terminal- (FR)]] et éditez le fichier avec : `nano /etc/network/interfaces`

Pour une solution permanente vous devez modifier le fichier interfaces.base . Et avant de le modifier, vouis devez monter le ssytème de fichiers en lecture écriture. Essayez les commandes: 
mount -o remount,rw / 
nano /etc/network/interfaces.base

- [Partition en écriture pour Recalbox 4.0.0](https://github.com/recalbox/recalbox-os/wiki/partition-en-ecriture-%28FR%29)   
    

Recherchez la ligne contenant l'interface que vous souhaitez modifier (ethX pour l'éthernet, wlanX pour le wifi) :
```
auto eth0
iface eth0 inet dhcp
```

Modifions l'adresse ip de eth0.     
- Remplacez les paramètres actuels par ceux de l'ip fixe : 
```
auto eth0
iface eth0 inet static
     address 192.168.1.10
     network 192.168.1.0
     netmask 255.255.255.0
     broadcast 192.168.1.255
     gateway 192.168.1.254
```
(dans cet exemple votre réseau local derrière votre box est 192.168.1.x . L’adresse de votre box est 192.168.1.254. Le masque de votre réseau est donc 255.255.255.0. Et vous souhaitez que votre adresse soit 192.168.1.10)

- Rechargez les réglages avec : `ifdown eth0 && ifup eth0`
