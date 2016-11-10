---
layout: page
title: Configuration recalbox pour Bartop Born Arcade (FR)
wikiPageName: Configuration-recalbox-pour-Bartop-Born-Arcade-(FR)
menu: wiki
---

Si vous voulez utiliser un Raspberry Pi avec recalbox pour créer un "**Bartop**" ou une **borne d'arcade**, vous pouvez facilement configurer recalbox pour répondre à votre besoin.

### A - GPIO
Vous pouvez configurer le pilote GPIO de la recalbox dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29). Ce pilote crée deux joysticks sur le système et directement contrôlés par les PINS GPIO du Raspberry Pi.

Pour cela vous n'avez pas besoin d'un hub USB car vous connecterez vos boutons directement sur les [GPIO](https://github.com/recalbox/recalbox-os/wiki/GPIO-controllers-%28FR%29).

### B - Configuration vidéo
Beaucoup de "bartops" utilisent un vieil écran LCD ou des écrans de télévision CRT utilisant une des connexions suivante : 
* **Ecran VGA** : vous aurez besoin d'un convertisseur HDMI / VGA (convertisseur actif) coûtant dans les 10€. Si vous êtes sur un écran 4/3 vous aurez besoin de changer le mode vidéo pour le passer à `global.videomode=default` pour tout vos émulateurs dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29).
* **Ecran DVI** : vous aurez besoin d'un adaptateur HDMI / DVI (convertisseur passif). Vous aurez probablement besoin de modifier votre fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29) en vous basant basant sur le [Mini HowTo - Connectez votre recalbox à un écran DVI](https://github.com/recalbox/recalbox-os/wiki/Connectez-votre-recalbox-%C3%A0-un-%C3%A9cran-DVI-%28FR%29).
* **Ecran CRT** : Vous aurez besoin d'une prise jack vers RCA avec un câble vidéo. Vous devez changer le mode vidéo pour le positionner sur `global.videomode=default` pour tous vos jeux dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29) et modifier les paramètres décris dans [HowTo - Connectez votre recalbox à un écran CRT en utilisant le composite](https://github.com/recalbox/recalbox-os/wiki/Connectez-votre-recalbox-%C3%A0-un-CRT-avec-composite--%28FR%29)

### C - Configuration audio
Vous pouvez sélectionner le périphérique de sortie audio dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29) : 
* Utilisez `audio.device=jack` si vous voulez forcer la sortie audio sur la prise jack
* Utilisez `audio.device=hdmi` si vous voulez forcer la sortie audio sur le HDMI

#### D - Configuration du menu
Vous pouvez désactiver Kodi dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29) en positionnant le paramètre suivant `kodi.enable=0`dans le but de supprimer le raccourci affecté au bouton "X". Cela supprimera aussi l'entrée Kodi dans le menu d'Emulationstation.

Vous pouvez aussi vouloir changer les réglages du menu : 
- Pour ES : 
 - En positionnant `system.es.menu=bartop`, vous aurez accès à un minimum d'options quand vous presserez le bouton "start" sous Emulationstation
 - En positionnant `system.es.menu=none`, seul le menu de sélection du jeu (bouton select) sera disponible
- Pour les émulateurs : 
 - En positionnant `system.emulators.specialkey` sur `nomenu` vous désactiverez les menus dans les emulateurs.
 - En positionnant `system.emulators.specialkey` sur `none` vous desactiverez les menus et toutes les fonctions spéciales dans les émulateurs. Sauf la combinaison pour sortir d'un jeu bien entendu.
