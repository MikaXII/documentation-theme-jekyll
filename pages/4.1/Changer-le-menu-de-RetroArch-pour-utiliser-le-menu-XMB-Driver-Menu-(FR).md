---
layout: page
title: Changer le menu de RetroArch pour utiliser le menu XMB Driver Menu (FR)
wikiPageName: Changer-le-menu-de-RetroArch-pour-utiliser-le-menu-XMB-Driver-Menu-(FR)
menu: wiki
---

# Introduction

L'objectif est de changer le driver de menu du rgui vers le driver menu du menu xmb

# Etapes
1. Lancer un jeu
2. Aller dans le menu principal de retroArch
3. Dans la section updater, lancer update assets
4. quitter le jeu
5. en SSH, ajouter l'entrée menu_driver = "xmb" dans le fichier configs/retroarch/retroarchcustom.cfg

# Optionel

**changer l'image de background de xmb pour avoir, par exemple, un fond transparent ce qui permet de toujours voir en fond le jeu en pause**

1. Uploader une image transparente au format png de 1920*1080 pixels, ou toute image que vous souhaitez avoir en background
2. en SSH, mettre à jour l'entrée menu_wallpaper = "~/.config/retroarch/assets/wallpapers/your_uploaded_file.png
