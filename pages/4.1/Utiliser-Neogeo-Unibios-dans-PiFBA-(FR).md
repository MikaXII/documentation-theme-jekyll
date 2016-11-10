---
layout: page
title: Utiliser Neogeo Unibios dans PiFBA (FR)
wikiPageName: Utiliser-Neogeo-Unibios-dans-PiFBA-(FR)
menu: wiki
---

### Que permet Unibios :

- Modifier la région (Europe/USA/Japan) et le mode (AES/MVS)
- Accéder au « soft dip » pour modifier la difficulté/vie/temps etc … du jeu
- Utiliser la base de donnée de cheats code
- Accéder au jukebox du jeudi

### Comment l'installer sur PiFBA/Recalbox :

1. Téléchargez la version 3,1 : http://unibios.free.fr/download.html
2. Extrayez le fichier téléchargé, puis renommez le fichier `uni-bios.rom` en `asia-s3.rom`
3. Ouvrez votre fichier `neogeo.zip`, vous devriez déjà avoir un fichier `asia-s3.rom` à l'intérieur. Faites en une sauvegarde si besoin.
4. Remplacez le fichier `asia-s3.rom` déjà présent dans le `neogeo.zip` par celui nouvellement renommé.
5. Uploadez le nouveau `neogeo.zip` dans les répertoires partagés `/bios` et `/finalburnalpha` de la recalbox.

### Utilisation :

-Démarrez n'importe quel jeu neogeo, vous devriez alors voir le nouvel écran de boot UNIVERSE BIOS V3,1
- Pendant cet « écran de boot, pressez et maintenez `BXY` pour modifier la région/mode, ou maintenez `ABX` pour activer le menu « dip switch »
- Pour accéder en jeu au menu, vous devez presser et maintenir `BXY+START`
