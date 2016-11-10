---
layout: page
title: Know IP reseau (FR)
wikiPageName: Know-IP-reseau-(FR)
menu: wiki
---

### Prérequis
* Assurez-vous que votre recalbox est bien lancée et connectée au réseau via un cable ethernet ou un dongle wifi.

> Vous avez un doute et votre réseau à un accès Internet ? Rien de plus simple, rendez-vous dans le menu de recalbox puis sur `METTRE A JOUR LE SYSTEME`. Si une pop-in s'affiche avec le message `Une mise à jour est disponible` ou `Aucune mise à jour de disponible`, alors votre recalbox a bien un accès à Internet et donc, au réseau. Si le message `Veuillez brancher un cable réseau` s'affiche, soit vous n'avez pas Internet sur le réseau ce qui n'est pas problématique, soit vous avez un soucis de configuration sur votre routeur, un cable défectueux ou un dongle wifi qui ne fonctionne pas.

:warning: Attention l'IP n'est pas fixe et est suceptible de changer à chaque redemarrage. Vous pouvez en définir une vous même via le [[mini How-to dédié | Manuel-IP-Paramètres (FR)]]

### Sous Microsoft Windows
* Lancer la commande `Executer`
_Vous ne savez pas ou se trouve la commande exectuer, [Google est votre ami](http://www.laissemoichercherca.com/?q=commande%20executer%20windows%207)_
* Tapez `cmd` et faire `Entrer`
* Puis une fois dans le terminal, tapez `ping recalbox` puis faire `Entrer`
* Vous devriez avoir le message suivant qui s'affiche : 

> Envoi d'une requête 'ping' sur RECALBOX avec 32 octets de données:
Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128
Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128
Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128
Statistiques Ping pour [...]

* Vous avez votre IP.

### Sous Apple OSX
* Lancer le `Terminal`
_Il se trouve dans le dossier `Utilitaires` du dossier `Applications`_
* Tapez-y `arp -a`
* La liste de tous les appareils connectés au réseau, sous forme de liste d'IP, s'affiche.
* L’ip du raspberry est souvent du type `192.168.0.XX`.
* Vous avez votre IP.

### Autres solutions

* Des applications smartphones sont disponibles pour scanner votre réseau. Rendez-vous sur le store de votre appareil pour trouver l'application de votre choix.
* Une autre solution consiste à se rendre dans les paramètres du routeur de votre box Internet. La liste des périhpériques connectés y est répértoriée.
