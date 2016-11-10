---
layout: page
title: Compilation & Modifications (FR)
wikiPageName: Compilation-&-Modifications-(FR)
menu: wiki
---

Alors nous y voilà. Vous voulez compiler **recalboxOS**. Peut-être que vous voulez ajouter vos propres éléments au système d'exploitation. Avant d'aller plus loin, soyez alors certain de bien comprendre les différents projets composant **recalboxOS** : [[recalboxOS détaillé|recalboxOS-détaillé-(FR)]]

Ce qui suit va vous montrer comment compiler les projets et créer une carte SD contenant **recalboxOS** manuellement. A titre indicatif 30 Go d'espace disque sont nécessaire et 4 à 5h de compilation suivant votre processeur.
Si vous voulez seulement jouer, dirigez vous alors vers [[Installation.|Installation-(FR)]]


## I - Processus de Compilation

La première chose à faire est de compiler recalbox-buildroot project. Ensuite, vous aurez le choix:

- compiler le système recalbox-rescue et l'utiliser pour installer **recalboxOS**.
- créer manuellement les partitions sur votre carte SD et installer **recalboxOS** directement (non traité dans ce tutoriel)

### A - recalbox-buildroot

Pour compiler recalbox buildroot, installez les dépendances suivantes:
```
sudo apt-get install build-essential git libncurses5-dev qt5-default qttools5-dev-tools mercurial libdbus-glib-1-dev texinfo zip default-jre imagemagick
```

Sur une Ubuntu 16.04 fraîchement installée, vous aurez besoin des paquets suivants :
```
sudo apt-get install build-essential git libncurses5-dev libssl-dev mercurial texinfo zip default-jre imagemagick subversion hgsubversion autoconf automake bison scons libglib2.0-dev
```

Puis clonez le dépôt et sélectionnez la branche unified. Nous utiliserons la variable arch pour spécifier sur quelle version de rpi nous sommes (rpi1, rpi2 ou rpi3)
```
arch=rpi2
git clone https://github.com/digitalLumberjack/recalbox-buildroot.git recalbox-buildroot-${arch}
cd recalbox-buildroot-${arch}
```

Créons la configuration avec un defconfig
```
make recalbox-${arch}_defconfig
```
Puis utilisons make pour compiler le système
```
make
```

À la fin de la compilation, vous aurez trois choses à garder à l'esprit:

- le fichier output/images/recalbox/root.tar.xz  est l'archive de votre système de fichier root.
- le fichier output/images/recalbox/boot.tar.xz est l'archive de votre partition boot.
- le fichier output/images/recalbox/share.tar.xz est l'archive de votre partition SHARE, voir ci-dessous.


**Nota:**


Au cas où vous auriez le message d'erreur suivant:
```
You must install ‘java’ on your build machine
make: *** [core-dependencies] Erreur 1
```

Vous pouvez soit tenter une installation du jdk java directement depuis les dépots:
```
sudo apt-get install  openjdk-8-jdk
```
Soit installer le paquet manuellement après avoir téléchargé sur le site d'Oracle la dernière verion de l'installeur jdk pour votre Os (par exemple: jdk-8u45-linux-x64.tar.gz):
```
 sudo apt-get install java-package
 sudo apt-get install libxtst6
 cd ~/Téléchargements
 make-jpkg jdk-8u45-linux-x64.tar.gz
 sudo dpkg -i oracle-java8-jdk_8u45_amd64.deb
```

Si le make s'arrête à cause d'une erreur sur xbodrv, vérifiez de bien avoir le paquet libdbus-glib-1-dev 

### B – recalbox-rescue
Si vous avez installé les dépendances de recalbox-buildroot, clonez et compilez le projet recalbox-rescue :
```
git clone https://github.com/digitallumberjack/recalbox-rescue
cd recalbox-rescue
git checkout dual
lupdate -no-obsolete recovery/recovery.pro
./BUILDME.sh
```

A la fin de la compilation, les fichiers système de recalbox-rescue qui seront copiés sur la carte SD seront dans le répertoire `output/`

### C – Création de la carte SD

Maintenant que nous avons nos systèmes *recalbox-buildroot* et *recalbox-rescue* compilés, nous avons à créer la carte SD.
Créons un dossier qui représentera la racine de votre carte SD. Une fois la copie des fichiers dans ce dossier effectuée, vous n'aurez plus qu'à copier tous les fichiers présents dans ce dossier sur une carte sd formatée en fat32. Retournons sur le répertoire de travail et créons ce dossier.
```
cd ..
mkdir SDCONTENT
```

Maintenant nous pouvons copier le système recalbox-rescue :
```
cp -r recalbox-rescue/output/* SDCONTENT
```

Recalbox rescue a besoin de 3 archives pour installer les 3 partitions de **recalboxOS** :

- boot.tar.xz sera extrait dans la première partition, de type fat32, nommée BOOT, montée sur /boot dans le système
- root.tar.xz  sera extrait dans la seconde partition, de type ext4, nommée root, montée sur / dans le système
- share.tar.xz serra extrait dans la troisième partition, de type fat32 , nommée SHARE, montée sur /recalbox/share dans le système

Vous souvenez-vous de notre variable *arch* qui nous avons défini selon si nous étions sur *rpi1* ou *rpi2* ?

Copions les 3 archives avec cette ligne de commande :
```
cp recalbox-buildroot-${arch}/output/images/recalbox/*.tar.xz SDCONTENT/os/recalboxOS-${arch}/
```

Vous pouvez dès à présent copier tous les fichiers présents dans SDCONTENT sur votre carte SD !
**Vous n'avez plus qu'à démarrer votre RPI et profiter de recalbox !**


## II - Modification
Il y a deux répertoires importants dans les sources recalbox-buildroot:

- `board/recalbox/fsoverlay/` est le répertoire contenant les fichiers qui seront remplacés ou ajoutés à la partition root. Par exemple `board/recalbox/fsoverlay/etc/fstab` remplace l'original buildroot fstab pour monter les partitions de recalbox sur des points de montage personnalisés . Donc, si vous avez des fichiers de configuration, assets etc, vous devrez les ajouter ici.
- `package` est le répertoire contenant tous les « packages descriptor ».  De nombreux logiciels sont déjà disponibles, mais si vous souhaitez ajouter les vôtres, ça se passe ici.

#### 1 – Configuration

Vous pouvez configurer le système avec
```
make menuconfig
```

Ce menu montre la configuration système et la sélection de paquets. Il sauvegarde la configuration dans le fichier `.config`.

#### 2 – Ajouter un paquet

Si vous voulez ajouter un paquet, vous pouvez vous baser sur un paquet existant. Prenons `recalbox-emulationstation` comme cas d'étude :
``` 
$ ls package/recalbox-emulationstation/
Config.in  recalbox-emulationstation2-000-cmakelist.patch  recalbox-emulationstation2.mk
```

Le `Config.in` sera utilisé par buildroot pour obtenir les informations sur le paquet, les dépendances, les messages etc...

Tous les fichiers .patch seront exécutés avant la compilation.

Le fichier mk contient les commandes pour configurer, compiler et installer le logiciel.

Une fois que vous avez copié et modifié votre paquet, éditez le fichier `package/Config.in`. Il répertorie tous les paquets disponibles pour menuconfig. Ajoutez votre nouveau paquet dans ce fichier, puis exécutez `make menuconfig` depuis la racine du projet. Vous verrez votre nouveau paquet dans la liste des paquets cible!

Ne pas oublier de vérifier attentivement les noms variables dans les fichiers. Pour le reste, la documentation buildroot est très clair : http://buildroot.uclibc.org/downloads/manual/manual.html
