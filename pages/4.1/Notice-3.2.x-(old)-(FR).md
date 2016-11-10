---
layout: page
title: Notice 3.2.x (old) (FR)
wikiPageName: Notice-3.2.x-(old)-(FR)
menu: wiki
---

#recalbox 3.3.X
#Notice v1.0.2

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.com

- I - [Première utilisation](#first-use)
- II - [Configuration](#configuration)
 - A - [Manettes](#controllers)
   - 1 - [Manettes PS3](#ps3controllers)
    - 2 - [Manettes XBox 360](#xboxcontrollers)
    - 3 - [Ajouter une manette bluetooth](#btcontrollers)
    - 4 - [Configurer une manette](#configurecontrollers)
    - 5 - [Mapping des boutons](#btnmapping)
    - 6 - [Mapping du clavier](#keyboardmapping)
    - 7 - [Contrôleurs GPIO](#gpiocontrollers)
    - 8 - [Virtual Gamepads](#virtualgamepads)
 - B - [Réglages système](#system-settings)
- III - [EmulationStation](#es)
 - A - [Présentation](#es-pres)
 - B - [Options dans Emulationstion](#es-settings)
   - 1 - [Options système](#es-settings-sys)
    - 2 - [Options des jeux](#es-settings-games)
    - 3 - [Options des manettes](#es-settings-controllers)
    - 4 - [Options de l'interface](#es-settings-ui)
    - 5 - [Options du son](#es-settings-sound)
    - 6 - [Options réseau](#es-settings-network)
 - C - [Contrôles](#controls)
 - D - [Favoris](#favorites)
 - E - [Scraper](#scrapper)
- IV - [Pendant le jeu](#duringgame)
 - A - [Sauvegardes](#duringgame-saves)
 - B - [Commandes spéciales](#duringgame-special)
- V - [Mises à jour](#updates)
- VI - [Fonctionnalités réseau](#network)
 - A - [Ajouter ses propres jeux](#network-add)
 - B - [Jeux Scummvm](#network-scummvm)
 - C - [Captures d’écran](#network-screenshots)
 - D - [Faire une copie de ses sauvegardes](#saves)
- VII - [Kodi Media Center](#kodi)
- VIII - [Dépannage](#trouble)
 - A - [Manettes](#trouble-controllers)
 - B - [Autres problèmes](#trouble-other)
 - C - [Restauration complète de la recalbox](#hard-reset)
 - D - [Accès ROOT](#root-access)
- IX - [recalbox.conf](#recalbox.conf)




## Introduction
La recalbox est un système permettant de retrouver le plaisir de jouer aux jeux retro old school, de façon simple et conviviale.

Elle tourne sur un mini-ordinateur appelé Raspberry Pi, et utilise un ensemble d’émulateurs optimisés pour ce dernier.

## <a name='first-use'></a>I - Première utilisation
Le package de la recalbox contient les éléments suivant :
- Un raspberry Pi 1 ou 2
- Une carte µSD/SD de 16GB ou plus
- Un câble HDMI
- Une alimentation micro USB **>1.5AMP**
- Une manette USB ou Bluetooth

Référez vous à **[recalbox.com/diy](http://www.recalbox.com/diy)** pour plus d'informations à propos de votre première installation.

Une fois [[l'installation|Installation-(FR)]] réalisée, la première chose à faire et de relier la recalbox avec la télévision à l’aide du câble HDMI.

Pour allumer la recalbox, il vous suffit de brancher l'alimentation micro USB sur votre recalbox.
De nombreuses manettes fonctionnent "out the box", mais si vous voulez configurer une manette USB, alors branchez une clavier USB à votre recalbox et regardez [Ajouter une manette USB](#configurecontrollers)

Pour éteindre le système :  pressez le bouton start de la manette et choisissez “Quitter” et “Éteindre le système”
Vous pouvez ensuite débrancher l’alimentation dès que l’écran est en veille.

## <a name='configuration'></a>II - Configuration

### <a name='controllers'></a>A - Manettes
Les contrôlers _PS3 Dualshock_ et _Xbox 360_ sont supportés en mode « sans fil ». De nombreux contrôleurs **USB** and **Bluetooth** sont également supportés. Pour plus d'informations, regardez la [liste des périphériques compatibles.](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29)

#### <a name='ps3controllers'></a>1 – Manettes PS3
Vous devez posséder un dongle bluetooth pour utiliser une manette sans fil PS3.
Il vous est impossible de recharger votre manette via le Rpi, vous devez donc les recharger en utilisant directement l'alimentation USB.
Ne branchez votre manette sur votre recalbox **uniquement** pour l'associer à cette dernière.
Afin d'associer une _manette PS3_, branchez la sur votre recalbox et **attendez 10 secondes**. Ce délai passé, vous pouvez alors la débrancher et appuyer sur le bouton Home.

Concernant les copies asiatiques de manettes PS3 dualshock 3 (GASIA or SHANWAN) regardez [[Pilotes des manettes PS3|PS3-controllers-drivers-(FR)]]

#### <a name='xboxcontrollers'></a>2 – Manettes XBox 360
Les manettes sans fil Xbox 360 nécessitent un dongle spécifique pour fonctionner.
Si vous possèdez une manette Xbox 360 filaire ou sans fil, il vous est conseillé d'activer le [le pilote xboxdrv via recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28FR%29) pour profiter du meilleur support possible de votre manette.

Puis redémarrez votre recalbox avec votre manette ou votre dongle branché.

#### <a name='btcontrollers'></a>3 - Ajouter une manette bluetooth
Pour ajouter une manette bluetooth, réglez votre manette sur le mode appairage.
Puis allez dans le menu avec le bouton start de votre manette ou entrée de votre clavier et sélectionnez ** Options manettes**.

Sélectionnez **Associer une manette bluetooth**:

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair.jpg)

Une liste de manettes détectées apparaît, vous n'avez alors plus qu'à sélectionner votre manette et elle sera appairée ! Maintenant configurez votre manette si elle ne fait pas partie des manettes supportées !

Pour les utilisateurs de **8bitdo**, regardez [[8bitdo et recalbox|8bitdo-on-recalbox-(FR)]]. 

#### <a name='configurecontrollers'></a>4 - Configurer une manette
Il est possible d’ajouter une manette ou un stick arcade en USB sur la recalbox.

La plupart des modèles sont compatibles., regardez la [liste de compatibilitée](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29)

Après avoir branché votre manette/stick USB ou votre manette bluetooth appairée, pressez START sur une manette déjà configurée (ou la touche Entrée de votre clavier), puis allez dans le menu “Configurer les manettes”.

Vous n'avez plus qu'à suivre les instructions.

Le dernier bouton, le **HOTKEY** est un bouton qui va activer les combinaisons de touche, (regardez [Les commandes spéciales](#duringgame-special)). Il est recommandé d'utiliser **L3** (le click du joystick sur une dualshock) ou _**SELECT**_.

Le nom des touches est basé sur les boutons de la Super Nintendo : 

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

Les boutons L et R (avec L2 R2 L3 L3) sont basés sur les manettes Playstation.

Pour passer les boutons que vous n'avez pas, pressez un bouton pendant 2 secondes. La configuration passera automatiquement au bouton suivant.

De retour à l'écran de configuration des manettes, vous pouvez assigner une manette à un joueur. _Votre manette est maintenant configurée !_

#### <a name='btnmapping'></a>5 - Mapping des boutons

Pour les manettes à 6 boutons (snes, psx, arcade etc), les boutons sont mappés pour correspondre à ceux de la manette originale.
Pour les manettes à 2 boutons (nes, pcengine, gameboy etc) les boutons mappés sont B et A.

#### <a name='keyboardmapping'></a>6 - Mapping du clavier

Si vous avez totalement raté la configuration de votre manette ou que vous voulez simplement configurer une manette, vous pouvez brancher un clavier USB sur la recalbox.
Entrée est **START**, Espace est **SELECT**, Q est **RETOUR**, S est **OK**

#### <a name='gpiocontrollers'></a>7 - Contrôleurs GPIO 
Vous pouvez connecter vos boutons et joysticks arcade directement sur les GPIO du Raspberry Pi. Regardez [[Les contrôleurs GPIO |GPIO-controllers-(FR)]]

Vous pouvez également connecter des manettes originales de PSOne, Nes, Snes, Megradrive , etc. Regardez [[Les contrôleurs DB9 et Gamecon|DB9-and-Gamecon-controllers-(FR)]]

#### <a name='virtualgamepads'></a>8 - Virtual Gamepads

Avec le projet de Miroof [Virtual Gamepads](https://github.com/miroof/node-virtual-gamepads) vous pouvez ajouter jusqu'à 4 manettes avec vos smartphones/tablettes !
Démarrez le naviguateur web de votre smartphone, puis tapez l'adresse IP de votre recalbox suivie du port de communication (port=8080). Vous pouvez trouver l'adresse IP de votre recalbox dans le menu [Options réseau](#es-settings-network)

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones-350px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones.png)

Pour plus d'informations, regardez [[Virtual Gamepad|Virtual-Gamepad-(FR)]]

### <a name='system-settings'></a>B - Réglages système
Vous avez deux possibilitées de configurer votre recalbox. L'interface de Emulationstation propose de nombreuses options de configurations. Voir [Options dans Emulationstion](#es-settings)

Mais si vous désirez un réglagler finement chaque émulateur un par un, vous devez regarder **[[recalbox.conf|recalbox.conf-(FR)]]**


## <a name='es'></a>III - EmulationStation

### <a name='es-pres'></a>A - Présentation

Lorsque vous allumez la recalbox, vous accédez à l'interface Emulationstation. Celle-ci vous permet de lancer vos jeux, de régler certaines options ou de mettre à jour la recalbox.

Le premier écran est celui des Systèmes : 

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)


Il liste les consoles et systèmes disponibles. 


### <a name='es-settings'></a>B - OPTIONS dans Emulationstion

En pressant start, vous serez en mesure de modifier certains réglages système.

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings.jpg)

#### <a name='es-settings-sys'></a>1 - OPTIONS SYSTEME
Vous accèderez aux **informations système**, **la sélection de la langue**, **aux réglages de l'overclocking**; **ceux de mise à jour** et **ceux de Kodi**.
Vous pouvez modifier l'overclock de votre RPi1. Le classement des presets d'overclock, par ordre croissant de vitesse, donne : 
*NONE* < *HIGH* < *TURBO* < *EXTREM*
Le réglage Extrem peut annuler la garanti de votre RPi, mais il s'agit **du seul** qui vous donnera de bonnes performance avec tous les émulateurs du RPi1.

Il est également conseiller d'overclocker le RPi2 si vous voulez émuler la N64.

#### <a name='es-settings-games'></a>2 - OPTIONS DES JEUX
Ce menu propose comme réglages :  **format jeux** (16/9, 4/3), **lisser les jeux** et **rembobinage**
L'option **rembobinage** vous authorise à effectuer des retours dans le temps lors de votre partie.

:warning: _Cela peut ralentir certains émulateurs (snes, psx)_ si vous l'activez par défaut. Vous pouvez l'activer que pour certains émulateur via [[recalbox.conf|recalbox.conf-(FR)]].

#### <a name='es-settings-controllers'></a>3 - OPTIONS MANETTES
C'est ici que vous pouvez configurer vos manettes.

#### <a name='es-settings-ui'></a>4 - OPTIONS DE L'INTERFACE
Ce menu propose l'accès aux réglages de l'interface. Si l'image de votre recalbox a des bords noirs ou que l'image est recadrée, vous pouvez alors activer l'option overscan. Pour plus d'informations, regardez [[Overscan settings|Overscan-settings-(FR)]].

#### <a name='es-settings-sound'></a>5 - OPTIONS DU SON
Ce menu propose de désactiver ou activer les **musiques de fond** dans emulationstation, régler le **volume du système** et sélectionner  la **sortie audio** (*auto*, *jack* ou *hdmi*) .
Afin de forcer la sortie analogique, sélectionnez **jack**.

#### <a name='es-settings-network'></a>6 - OPTIONS RESEAU
Ce menu propose d'activer et configurer le **wifi**, le **nom du le réseau** et d'obtenir **l'adresse IP** de votre recalbox.
Saisissez  le SSID et la clé de votre réseau wifi avec un clavier. Une fois les informations validées, le wifi sera activé.

Problème connu : Il est impossible de saisir certains caractères nécessaires à vos informations réseau.
si vous rencontre ce soucis, configurez alors votre accès wifi directement dans le fichier  [[recalbox.conf|recalbox.conf-(FR)]].


### <a name='controls'></a>C - Contrôles

**Les commandes dans l'interface :**

A → Sélectionner
B → Retour  
Y → Favoris  
X → Démarrer Kodi  
Start → Menu  
Select → Options  
R → Page Suivante   
L → Page Précédente 


Lorsque vous sélectionnez un système avec la A, l'écran change et vous accédez à votre liste de jeux disponibles. 

Une fois le jeu lancé, reportez-vous à la section *Pendant le jeu* pour connaître les options disponibles.


### <a name='favorites'></a>D - Favoris

vosu pouvez définir un jeux comme favoris en pressant la touche Y. Le jeu sera alors placé en début de liste avec une ☆ devant son nom.
Le système doit être éteint proprement en utilisant le menu de emulationstation pour que que la liste de jeux en favoris soit sauvegardée et que vous la retrouviez au prochain démarrage.


### <a name='scrapper'></a>E - Scraper

Pour chaque jeu, vous pouvez obtenir des information (pochette, résumé, etc...) qui seront affichées dans le menu de sélection des jeux de emulationstation. Pressez **START** et aller dans **SCRAPER**. Suivez alors les instructions à l'écran.



## <a name='duringgame'></a>IV - Pendant le jeu

### <a name='duringgame-saves'></a>A - Sauvegarde 
Les émulateurs proposent une option très utile : la "save state". C’est une sauvegarde rapide du jeu qui vous permet de le recharger, plus tard, à cet endroit précis.

Avec ce système, plus besoin d’aller chercher un point de sauvegarde ou de recommencer les jeux depuis le début !

Vous pouvez utiliser ce que l’on appelle des "slots" pour sauvegarder plusieurs "save state" pour le même jeu.

Pour effectuer une "save state", faites la combinaison **Hotkey** + **Y** en jeu.


### <a name='duringgame-special'></a>B - Commandes spéciales
Lorsque vous êtes dans le jeu, des commandes spéciales sont disponibles : 

Appuyez en même temps sur le bouton Hotkey et sur un des boutons suivant : 

Y -> Sauvegarder l'état  
X -> Charger l'état  
START -> Quitter  
B -> Menu  
UP -> Sauvegarder dans le Slot -1  
DOWN -> Sauvegarder dans le Slot +1  
L1 -> Screenshot  
RIGHT -> Accélérer le jeu  

Dans FBA et Mame, utilisez la touche SELECT pour ajouter un crédit.
Dans mamen if votre hotkey est définie sur Select, vous devrez quitter le jeu avec **R1 + Start** (afin de pouvoir ajouter des crédit avec Select).

Pour accéder au menu de configuration de retroarch, pressez *Hotkey* + *B*
Si vous désirez configurer retroarch et sauvegarder votre configuration, activez l'option "Save settings on Exit" dans le menu de retroarch. une fois cette option activée, toutes les modification effectuées dans le menu seront sauvegardées.

### <a name='updates'></a>V - Mises à jour
La mise à jour de la recalbox se fait via le menu, accessible en appuyant sur START. Configurez votre wifi ou branchez un câble réseau sur la recalbox, sélectionnez "OPTIONS SYSTEME" “Mettre à jour la recalbox” et "Démarrer la mise à jour".

Le système redémarre après la mise à jour !


## <a name='network'></a>VI - Fonctionnalités réseau
Lorsque vous configurez votre wifi ou branchez un câble réseau sur la recalbox, celle-ci partage automatiquement des dossiers sur le réseau local. Sur votre ordinateur, allez dans l’onglet “Réseau” de l'explorateur Windows et sélectionnez la recalbox :
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1.jpg)

Si vous ne voyez pas votre recalbox sur le réseau, essayez de taper **\\\\RECALBOX** dans la barre d'adresse de explorer. Si cela ne fonctionne toujours pas, aller dans le menu de votre recalbox, __OPTIONS RESEAU__ puis notez votre ip.
Tapez alors votre ip dans la barre d'adresse de explorer (exemple : **\\\\192.168.1.30**)

Vous accédez ensuite aux dossiers partagés par la recalbox :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2.jpg)


### <a name='network-add'></a>A - Ajouter ses propres jeux
Il vous suffit de copier vos fichiers dans le répertoire correspondant. Vous pouvez utiliser soit des **.zip** ou des roms décompressées.

N'hésitez pas à partager votre liste de jeux favoris sur le forum de recalbox !
http://blog.recalbox.fr/forums/

### <a name='network-scummvm'></a>B - Jeux Scummvm
Lorsque vous ajoutez un jeu Scummvm, ce dernier doit être un répertoire décompressé. Dans ce répertoire, vous devrez ajouter un fichier vide, nommé [gameshortname].scummvm

Vous trouverez la liste des "shortnames" des jeux compatibles ici : http://scummvm.org/compatibility/

Par exemple, si vous copiez le répertoire "Broken Sword 1" dans le dossier scummvm. Dans ce répertoire, créez un fichier qui portera le nom sword1.scummvm

Votre jeu apparaîtra alors dans l'interface et vous pourrez alors modifier ses metadata si vous voulez afficher son vrai nom dans emulationstation.

### <a name='network-screenshots'></a>C - Captures d’écran
En appuyant sur Hotkey + L1 dans les émulateurs, vous pourrez faire une capture d’écran. Le fichier png est alors placé dans le dossier “screenshots”, accessible depuis le réseau. 
N’hésitez pas à venir partager sur nos forums vos meilleurs scores et vos meilleurs shots !

### <a name='saves'></a>D - Faire une copie de ses sauvegardes
Sur le réseau, la recalbox partage un dossier “sauvegardes”. Ce dossier vous donne accès à toutes les sauvegardes des émulateurs. Vous pouvez donc transférer vos anciennes sauvegardes ou faire une copie de ce dossier afin d'avoir l'esprit tranquille...

## <a name='kodi'></a>VII - Kodi Media Center
En pressant le bouton X de votre manette, vous pouvez démarrer Kodi Media Center, aka XBMC. Vous pouvez également accéder à Kodi en pressant Start et en le démarrant depuis le menu.

Pour quitter Kodi, sélectionnez "QUIT" dans le programme, et vous serez de retour sous emulationstation.

## <a name='trouble'></a>VIII - Dépannage

### <a name='trouble-controllers'></a>A - Manettes :

- La manette PS3 clignote mais ne se synchronise pas
Branchez la manette et attendez 10 secondes. Débranchez alors la manette, et appuyez sur le bouton HOME.

- La manette PS3 semble morte
Il faut réinitialiser la manette. Utilisez un trombone pour appuyer sur le bouton situé derrière la manette, à l'intérieur du petit trou, à droite de la visse du milieu. 

### <a name='trouble-other'></a>B - Autres problèmes

- Bordures noires, image trop grande   
Utilisez la télécommande de la télévision pour accéder aux paramètres d’affichage. Il faut régler l’affichage sur  “1:1 pixel” ou “tout afficher“ pour que la TV ne perde pas une partie de l’image.
Sinon, regardez [[Overscan settings|Overscan-settings-(FR)]] pour plus d'informations.

- Ecran noir sur un écran de PC
Si vous avez une écran noir lorsque que vous utilisez un écran de PC (hdmi ou dvi), éditez le fichier config.txt (touche majuscule du clavier au boot) et retirez la ligne hdmi_drive=2
Plus d'informations dans [[Mini HowTo - Connectez votre recalbox à un écran DVI|Connectez-votre-recalbox-à-un-écran-DVI-(FR)]] 


### <a name='hard-reset'></a>C -  Restauration complète de la recalbox
Si vous voulez restaurer complétement votre recalbox, branchez un clavier USB et maintenez la touche MAJ en allumant la console. Vous pourrez alors réinstaller recalboxOS à partir de ce menu. 
Attention, cette procédure efface toutes les données.

### <a name='root-access'></a>D - Accès ROOT
- Utilisez le nom d'utilisateur `root` et le mot de passe `recalboxroot` 
- Vous pouvez vous connecter via SSH à la recalbox. 
- Vous pouvez accéder directement à un terminal en quittant emulationstation avec F4 et en appuyant sur ALT+F2

Plus d'information dans [[Mini HowTo - Accès ROOT avec un terminal|accès-root-sur-Terminal--(FR)]]

## <a name='recalbox.conf'></a>IX - recalbox.conf
Le fichier `recalbox.conf`, partagé via Samba dans le répertoire `system`, est utilisé pour modifier d'autres paramètres qui n'apparaîtront pas dans l'interface. Voir [[recalbox.conf|recalbox.conf-(FR)]]
