---
layout: page
title: Sécurité (FR)
wikiPageName: Sécurité-(FR)
menu: wiki
---

La Recalbox n'est pas sécurisée par défaut, au moins pour les versions 4.0.0 et précédentes.
De manière générale:
* Ne connecte pas ta Recalbox directement à Internet
* Ne stocke pas d'informations sensibles/privées sur ta Recalbox
* Fais des sauvegardes régulièrement
* Éteins ta Recalbox entre deux sessions de jeu

# Mot de passe Root

La Recalbox vient avec un mot de passe root (super-utilisateur) par défaut. Jusqu'à la version 4.0.0, il est possible (et fortement recommandé) de changer ce mot de passe en exécutant les commandes suivantes, depuis une invite de commande(1):
* Re-monte la partition / en lecture-écriture

    mount -o remount,rw /

* Change le mot de passe root

    passwd

À noter: il te faudra defaire cette opération après chaque mise à jour, car les mises à jour de la Recalbox écrasent les fichiers existants et remettent donc le mot de passe à sa valeur initiale.
Les versions 4.1 et supérieures devraient proposer une alternative à ce mot de passe par défaut.

(1) Pour ouvrir une invite de commande, réfère-toi à ce [mini-how-to](https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29)

# Services réseau

La Recalbox active plusieurs services réseau par défaut. Bien que très pratiques, ces services sont également des point d'entrée faciles pour des personnes mal intentionnées. Il est de bonne pratique que de désactiver les services que vous n'utilisez pas en éditant la section 'Network' du fichier recalbox.conf (2)

(2) Pour éditer ce fichier, deux solutions:
- Ouvre une invite de commande, et une fois connecté, tape:

    nano recalbox.conf

- Ou bien sur ton ordinateur, ouvre une fenêtre web à l'adresse: http://\<adress-ip-de-ta-recalbox\>/ pour ouvrir le recalbox-manager, et édites la configuration depuis la page correspondante

## Wifi

Si tu n'as pas besoin d'une connexion ou si tu utilises une connexion filaire, désactive le wifi:

    wifi.enabled=0

Attention: la Recalbox stocke le mot de passe de ton réseau wifi dans le champ wifi.key, donc quand tu le désactives, assures-toi d'avoir effacé ce mot de passe.
Les versions 4.1 et ultérieures ne devraient plus stocker le mot de passe wifi en clair.

## Samba

Samba est un service très pratique pour transférer des fichiers depuis un ordinateur. Si tu ne l'utilises pas, désactive-le en configurant:

    system.samba.enabled=0

Les versions 4.1 et ultérieures devraient supporter des partages Samba protégés par un mot de passe.

## Manettes virtuelles

Ce service te permets d'utiliser ton smartphone ou ta tablette en tant que manette. Si tu n'utilises pas de telles manettes, désactive le service en configurant:

    system.virtual-gamepads.enabled=0

# Recalbox Manager

La Recalbox est fournie avec son proper serveur web, écoutant sur le port 80. Ce serveur te permets de charger des roms en faisant du drag-and-drop et aussi de modifier la configuration. Cependant, c'est un point d'accès en or pour une personne cherchant à prendre le contrôle de ton Raspberry.

Donc, si tu n'utilises pas le Recalbox manager (par exemple, parce que tu as déjà toutes les roms de tes rêves sur ton Raspberry, ou bien si tu préfères transferrer tes roms via le service Samba), tu peux le désactiver en configurant:

    system.manager.enabled=0

Ces étapes devrait rendre ta box (et par conséquence tous les appareils connectés à ton réseau) un peu plus sécurisée...
