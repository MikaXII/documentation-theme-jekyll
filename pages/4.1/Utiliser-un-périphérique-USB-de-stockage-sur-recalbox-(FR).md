---
layout: page
title: Utiliser un périphérique USB de stockage sur recalbox (FR)
wikiPageName: Utiliser-un-périphérique-USB-de-stockage-sur-recalbox-(FR)
menu: wiki
---

Vous pouvez très facilement utiliser un périphérique USB de stockage (clé USB, disque dur externe auto alimenté etc.) pour stocker vos roms, fichiers perso etc.

* Premièrement, vous devez utiliser un périphérique utilisant un système de fichiers suivant : FAT32, EXT4 ou NTFS (les taux de transferts peuvent être lents dans le cas du NTFS, attention donc).
Soyez également certain que le système de fichier que vous choisirez soit bien compatible avec le système d'exploitation de votre PC.
RecalboxOS ne formatera pas votre périphérique, il ne créera que de nouveaux fichiers dessus.

* Branchez votre périphérique à votre recalbox, puis allumez la. Une fois, sous l'interface de recalbox, pressez le bouton start de votre manette, allez dans les options système et dans média de stockage. Maintenant, sélectionnez  votre périphérique dans la liste, puis validez et attendez que le système ait redémarré..
Durant cette phase de redémarrage, recalboxOS va créer à la racine de votre périphérique, un nouveau répertoire nommé `recalbox` qui contiendra toute l'arborescence de votre partition `/share`.

* Pour ajouter vos fichiers (roms, sauvegardes de jeux, bios, données de scrape etc...) sur votre périphérique de stockage, vous devez éteindre votre recalbox. Puis branchez votre périphérique à votre PC. Il ne vous reste plus qu'à copier vos fichiers perso sur votre périphérique depuis votre PC, sans utiliser votre réseau local. Une fois le transfert terminé, il ne vous reste plus qu'à rebrancher votre périphérique à votre recalbox, l'allumer et jouer.

Avec cette méthode, le système (sur la carte sd) et la partition share (sur le périphérique) sont séparés. Donc si vous deviez réinstaller votre système, vous conserveriez toutes vos données utilisateur. Vous n'aurez alors qu'à rebrancher votre périphérique à votre recalbox, puis le sélectionner dans le système, et jouer.
