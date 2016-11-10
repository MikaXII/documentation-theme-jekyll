---
layout: page
title: acces via WinSCP (FR)
wikiPageName: acces-via-WinSCP-(FR)
menu: wiki
---

### Prérequis
* Assurez-vous que votre recalbox est bien lancée et connectée au réseau via un cable ethernet ou un dongle wifi.

> Vous avez un doute et votre réseau à un accès Internet ? Rien de plus simple, rendez-vous dans le menu de recalbox puis sur 'OPTIONS RESEAU`. Vous aurez accès à votre IP et a l’état du réseau.

* Téléchargez et installer le logiciel WinSCP
 - Pour [Windows](http://winscp.net/)
 - Pour [Mac OSX](http://www.mediafire.com/download/w5d794zbnwv3dkj/WinSCP.zip) _(:warning: Attention, ce n'est pas une version officielle. C'est un portage de la version windows de 2011 sous OSX. Le logiciel payant [rbrowser](http://www.rbrowser.com/) est une solution alternative)_

* Facultatif : Connaitre l'adresse IP de votre recalbox. Suivez le [[mini How-to dédié | Know-IP-reseau (FR)]] si vous ne la connaissez pas.

### Configuration
* Lancez `WinSCP`
* Cliquez sur `Nouveau site`
* Remplissez les informations comme il suit :
 - Protocole de fichier `SCP`
 - Nom de l'hôte `recalbox` ou l'IP que vous avez précédemment identifié _(la config sera à modifer à chaque redemarragede recalbox si vous avez rentré l'ip)_
 - Numéro de port `22`
 - Nom d'utilisateur `root`
 - Mot de passe `recalboxroot`
 - Faite `Sauver...`
 - Remplissez les informations comme il suit :
 - Enregistre la session sous : `Recalbox` par exemple
 - Cochez la case Enregistrer le mot de passe (non recommandé) puis faite `OK`
* Votre logiciel est maintenant configuré

* Rendez-vous dans vos favoris (colonne de gauche) et double cliquez sur recalbox
* Une pop-up s'ouvre vous informant de la connexion en cours
* Une autre pop-in peut s'ouvrir vous demandant de `Continuer la connexion au serveur inconnu et ajouter la clé d'hôte dans le cache ?` puis cliquez sur `oui`
* Vous voilà connecté

### Afficher les fichiers cachés

* Allez dans `Préférences` (CTRL+ALT+P) puis `Panneaux` et enfin, cochez la case `Afficher les fichiers cachés`. Cela vous sera utile pour accéder au dossier .emulationstation pour modifier le thème par exemple.

<a href="http://www.zimagez.com/zimage/winscphidden.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscphidden.png" alt="Visionner l'image" /></a>


### Utilisation

L'utilisation se veut assez intuitive. Par défaut, vous retrouvez à gauche votre ordinateur et à droite, l'arboresence de votre recalbox.
Quelques astus :
* Pour revenir au dossier supérieur ou à la racine de votre recalbox, il suffit de cliquer sur le premier dossier avec un picto de retour haut et identifié comme `...`.
* Vous pouvez déposer des dossiers par simple glisser déposer dans la colonne de droite ou depuis la colonne de droite.
* Vous pouvez changer les permissions sur un fichier via un clic droit sur ce dernier puis `Propriétés`
* Retrouvez les chemins vers les fichiers/dossiers utiles dans le [[FAQ|FAQ]]

### Mettre winscp en français

Une fois winscp installé
Télécharge le fichier de langue français sur cette page (French) : http://winscp.net/eng/translations.php

Décompresse-le et place le fichier dans C:\Program Files(x86)\winscp\

Puis execute winscp,si l interface est toujours en anglais, nous allons modifier la langue en français.
Clic sur le bouton tools en bas à gauche choisir préférences.

A gauche en haut, environnements > languages > french - français doit apparaître
sélectionne le puis clic sur ok.

<a href="http://www.zimagez.com/zimage/winscplangue.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscplangue.png" alt="Visionner l'image" /></a>

### Ajouter putty : 

il suffit de placer l executable de putty dans le dossier %programfiles%\WinSCP\Putty
Puis de le configurer dans winscp &gt; outils &gt; Préférences &gt; Intégration &gt; Applications
comme indiqué sur la capture d écran suivante [télécharger ici](https://the.earth.li/~sgtatham/putty/latest/x86/putty.exe)   

<a href="http://www.zimagez.com/zimage/winscpputty.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscpputty.png" alt="Visionner l'image" /></a>   

Une astuce et aussi de cocher la case suivante : se souvenir du mot de passe de la session et le passer à Putty (SSH)   
   
<a href="http://www.zimagez.com/zimage/puttyviawinscp02.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/puttyviawinscp02.png" alt="Visionner l'image" /></a>    
   


### Ajouter notepad++     
   
[Télécharger notepad++](https://notepad-plus-plus.org/download/v6.9.html)   
il suffit de l ajouter à winscp en l'ajoutant comme éditeur externe : 
&gt; outils &gt; Préférences &gt;  Editeurs &gt; Ajouter
indiquer le chemin vers l application notepad++ , coche les cases comme indiqué sur la capture d'écran
puis cliquer sur le bouton monter pour qu il soit en haut ds la liste des choix.

<a href="http://www.zimagez.com/zimage/winscpnotepadplus01.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscpnotepadplus01.png" alt="Visionner l'image" /></a>

<a href="http://www.zimagez.com/zimage/winscpnotepadplus02.php" target="_blank" title="config"><img src="http://www.zimagez.com/miniature/winscpnotepadplus02.png" alt="config" /></a>

/play yeah
