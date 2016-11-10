---
layout: page
title: Connectez bluetooth commande avec hcitool et hidd commande manuelle (FR)
wikiPageName: Connectez-bluetooth-commande-avec-hcitool-et-hidd-commande-manuelle-(FR)
menu: wiki
---

Vous pouvez connecter votre contrôleur Bluetooth manuellement.

Vous aurez besoin de [obtenir un accès root] (https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29)

Mettez votre contrôleur Bluetooth en mode d'association, et le type:

`hcitool scan` 

En retour vous obtenez l'adresse mac du contrôleur:

`aa:bb:cc:dd:ee:ff Nom:Bluetooth HID`

Ensuite, créez la connexion au contrôleur:

`hidd --connect aa:bb:cc:dd:ee:ff`

Et redémarrer emulationstation:

`/etc/init.d/S31emulationstation restart`
