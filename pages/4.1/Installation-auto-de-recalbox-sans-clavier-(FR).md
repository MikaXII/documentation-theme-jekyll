---
layout: page
title: Installation auto de recalbox sans clavier (FR)
wikiPageName: Installation-auto-de-recalbox-sans-clavier-(FR)
menu: wiki
---

Vous pouvez installer recalboxOS automatiquement sur votre RapberryPi sans avoir besoin d'un clavier USB.

Suivez ces différentes étapes :

1. Télécharger et dézipper la dernière version de recalboxOS

2. Supprimer le dossier dans `os` celui qui ne correspond pas à votre RPi.  Si vous avez un RPi1 supprimer  `recalboxOS-rpi2`, si vous avez un RPi2 supprimer `recalboxOS-rpi` 

3. Editer le fichier  `recovery.cmdline` et ajouter `silentinstall` à la liste des arguments :  
`runinstaller quiet vt.cur_default=1 elevator=deadline`  
devient 
`runinstaller quiet vt.cur_default=1 elevator=deadline silentinstall`

Lorsque vous démarrez votre Pi en utilisant une carte SD contenant la version modifiée de recalbox que vous venez de créer, il va installer automatiquement recalboxOS puis le démarrer une fois l'installation est terminée. 
