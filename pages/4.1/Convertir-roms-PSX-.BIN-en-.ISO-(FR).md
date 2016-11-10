---
layout: page
title: Convertir roms PSX .BIN en .ISO (FR)
wikiPageName: Convertir-roms-PSX-.BIN-en-.ISO-(FR)
menu: wiki
---

Bonjour à tous,

Un problème récurrent avec les roms pour la PSX est que les fichiers sont plus souvent aux formats .BIN et .CUE qu'en .ISO, et parfois encore des roms au format .BIN.ECM

L'un des inconvénients de ces fichiers, c'est qu'ils sont souvent plusieurs, 2 ou 3 fichiers voire parfois des dizaines, et cela fausse la qualité de la présentation dans l'interface d'EmulationStation : on peut se retrouver avec plusieurs fichiers par jeu, et du coup le nombre total de jeux pour ce système est aussi faussé.

Nous allons développer ici une solution qui fonctionne pour tous ces désagréments et obtenir un seul fichier au format .ISO par jeu. Tous les jeux fonctionnent sur ce modèle à condition que les fichiers .BIN téléchargés fonctionnent également.

Tout d'abord le fichier ISO est une 'image de disque' en binaire, c'est le format qui nous intéresse car l'intégralité du jeu tient en un seul fichier.

Le fichier BIN est également une image de disque, c'est un format très proche de l'ISO. L'inconvénient est que les fichiers BIN peuvent être plusieurs, voire parfois très nombreux, et sont généralement accompagnés d'un autre fichier au format CUE.

Le fichier CUE est un petit fichier texte qui accompagne les .BIN. Il peut être ouvert avec n'importe quel éditeur de texte, son seul but est d'aider à l'indexation des fichiers BIN qu'il accompagne, pour indiquer à l'émulateur qui va le lire, où sont les fichiers BIN, quels sont leur noms, leur ordre, et parfois les différentes pistes audio contenues.

Le fichier .BIN.ECM est plus rare. C'est le résultat d'un fichier BIN compressé. Nous allons voir dans la dernière partie comment le décompresser.

La première remarque c'est que souvent un jeu est composé d'un fichier BIN accompagné d'un fichier CUE. Dans ce cas, le fichier CUE (texte), qui a pour rôle d'indexer les différents fichiers BIN qui l'accompagnent, ne sert plus à rien. Les utilisateurs l'ont bien compris, en effet dans ce cas de figure il suffit de supprimer le fichier CUE, et alors le fichier BIN est autonome (comme un ISO), vous pouvez le laisser tel quel, ça fonctionne. (edit : ça n'est pas toujours si simple : voyez à l'exemple 4b de ce tuto : il y a des fichiers CUE qui ne servent à rien, d'autres sont plus complets et donc importants. Vous pouvez apprendre à faire la différence en les consultant systématiquement, vous avez aussi la possibilité de convertir toutes vos roms pour n'avoir aucun problème).

La seconde remarque est de ne jamais renommer les fichiers BIN que nous venons de voir. En effet, si vous ouvrez un fichier CUE avec un éditeur de texte, vous allez voir qu'il liste tous les fichiers.BIN qu'il accompagne : si vous renommez les fichiers BIN, alors ça ne correspond plus. Vous pouvez dans ce cas renommer tous les BIN dans le fichier CUE, mais c'est une étape qu'il est plus simple d'éviter en ne renommant pas les fichiers : lorsque vous aurez obtenu un fichier ISO vous aurez la liberté de le nommer comme vous le souhaitez.

Nous allons maintenant aborder la conversion des fichiers BIN en ISO. Pour cela j'ai utilisé le logiciel [IsoBuster](http://www.isobuster.com/fr/) (pour Windows, compatible Windows 10), gratuit en version de démonstration.

1. Ouvrir IsoBuster

2. Fichier > Ouvrir un fichier image
![](http://img15.hostingpics.net/pics/85390120160612204825IsoBuster37.png)


3. Aller chercher où se trouve le jeu au format BIN/CUE. Moi je les ai classés par jeux parce que c'était le bordel, vous n'êtes pas obligés de les classer ainsi.
![](http://img15.hostingpics.net/pics/41683420160612205002Ouvrirunfichierimage.png)


4. Comme on ne peut pas sélectionner plusieurs fichiers BIN à incorporer dans IsoBuster, l'astuce est de se servir du fichier CUE, qui lui indexe tous les BIN qui forment le jeu. Mon exemple n'est pas intéressant parce qu'il n'y a qu'1 fichier BIN, mais le principe serait le même avec 3 ou 30 fichiers BIN : on se sert du .CUE

Si votre rom est en 1 fichier BIN et que vous avez supprimé le .CUE, pas de souci, ça fonctionne en sélectionnant directement le .BIN
![](http://img15.hostingpics.net/pics/69789820160612205039Ouvrirunfichierimage.png)


4b. Sauf que je viens d'avoir un autre cas avec Rayman, composé de Rayman.bin et Rayman.cue : comme vous pouvez le voir dans la capture ci-dessous, le fichier .cue est beaucoup plus complet et indexe en plus les pistes audio du jeu. Les fichiers .CUE ne sont pas tous aussi complets, mais c'est une bonne habitude de toujours travailler avec le .cue
![](http://img15.hostingpics.net/pics/98664320160613030000IsoBuster3.png)

Voici une archive contenant les fichiers CUE pour toutes les roms PSX : [cue_and_sbis](https://www.google.fr/#q=cue_and_sbis)


5. Dans la colonne de gauche, clic droit sur la racine [CD], puis Extraire CD <image>    >    Données brutes (.BIN, .ISO)
![](http://img15.hostingpics.net/pics/88278920160612205101IsoBuster37.png)


6. Vous donnez un nom à votre fichier d'export, le nom du jeu désiré. Habituellement à cette étape dans les programmes, si vous ne mettez pas d'extension de fichier (.ISO) mais que c'est sélectionné .ISO en dessous, votre fichier arrive bien en .iso
Avez IsoBuster ce n'est pas le cas, votre fichier n'aura aucune extension de fichier si vous ne l'écrivez pas. Vous pourrez l'ajouter plus tard mais vous pourriez aussi vous y perdre, il est plus simple de bien mettre l'extension .iso dans le nom du fichier :
![](http://img15.hostingpics.net/pics/96101020160612205124Extrairelefichier.png)

7. La conversion prend quelques secondes :
![](http://img15.hostingpics.net/pics/94599520160612205131IsoBuster37.png)

8. Si vous avez sélectionné un .CUE vous cliquez sur non, de toute façon étant utilisé dans le programme il ne peut pas être écrasé.
![](http://img15.hostingpics.net/pics/61400420160612205141Lefichierexistedj.png)

Vous avez obtenu votre jeu au format ISO, qui aura été extrait à côté des fichiers BIN et CUE originaux.


Et nous allons finir avec le cas plus rare de BIN compressé, au format **.BIN.ECM**

Supprimer l'extension .ECM pour obtenir un .BIN ne fonctionne pas, il faut passer par un programme de décompression.

Il y a plusieurs méthodes, vous pouvez essayer :

* En passant par le navigateur Chrome sur ce site (bouton Add)
* Pour Linux et OSX il y a des méthodes en ligne de commande, où la méthode est de glisser les fichiers dans le terminal Vous trouverez des tutoriaux appropriés en cherchant les termes "BIN.ECM" et "Un-ECM" + le nom de votre système d'exploitation.
* Et enfin une autre méthode pour Windows que nous allons développer, est de télécharger le programme Un-ECM.exe (24Ko) [sur cette page](http://www.google.fr).
Vous extrayez le programme Un-ECM.exe dans un répertoire du même nom parmi vos programmes, et retenez son chemin d'installation. Faites un clic droit sur un fichier .BIN.ECM et faites "Ouvrir avec". Dans la liste des programmes proposés, faites défiler vers le bas, et cliquer sur "Rechercher une autre application sur ce PC" et ouvrez le avec le programme Un-ECM.exe. Vous pouvez cocher la case "toujours ouvrir avec cette application, ainsi à l'avenir un double-clic sur un fichier .BIN.ECM décompressera automatiquement le fichier BIN dans ce même répertoire. 

Le fichier BIN obtenu est donc utilisable en l'état ou vous pouvez aussi le convertir en ISO comme on l'a vu précédemment.
