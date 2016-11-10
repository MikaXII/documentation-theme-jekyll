---
layout: page
title: Recalbox manager (FR)
wikiPageName: Recalbox-manager-(FR)
menu: wiki
---

La nouvelle fonctionnalité [recalbox-manager] (https://github.com/sveetch/recalbox-manager) (depuis 3.3b12), est une interface web pour gérer votre recalbox.
L'interface a été créée pour donner à tous les utilisateurs (débutants ou non) une meilleure façon de configurer la Recalbox.

Comment l'utiliser :
- Ouvrez votre navigateur préféré
- Aller à: `http://[IP de la recalbox]`
- Et vous êtes sur la page principale du gestionnaire

la plus part des routeurs sont configurés de tel que vous devriez trouver votre recalbox entre
`192.168.1.254` et `192.168.1.2`

Lorsque vous êtes sur la page principale, vous pouvez naviguer entre les menus suivants:

- Éditer le fichier recalbox.conf
- Ajouter/Supprimer des bios
- Ajouter/Supprimer des roms
- Consulter les log

Par défaut, le gestionnaire démarre automatiquement. Si vous voulez, vous pouvez le désactiver dans recalbox.conf
```
## Recalbox Manager (gestionnaire de http)
system.manager.enabled = 1
```
