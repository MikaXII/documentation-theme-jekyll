---
layout: page
title: GPIO controllers (FR)
wikiPageName: GPIO-controllers-(FR)
menu: wiki
---

Recalbox est compilé avec le pilote [mk_arcade_joystick_gpio](https://github.com/digitalLumberjack/mk_arcade_joystick_rpi) qui permet de gérer un contrôleur connecté directement sur les GPIO du rpi.

Donc si vous avez prévu de vous construire un **Bartop**, une **Borne d'arcade** ou un **Stick d'arcade portable**, vous n'avez pas besoin d'investir dans un contrôleur usb.  

Le pilote peut gérer jusqu'à **2 contrôleurs** composés chacun d'un **joystick 4 directions** et de **9 boutons**.

Si vous utilisez un `RPi1 B revision` reportez vous à : [mk_arcade_joystick pinout](https://github.com/digitalLumberjack/mk_arcade_joystick_rpi/blob/hotkeybtn/README.md#pinout)

### Pinout ###
Prenons comme exemple un panel à 7 boutons avec cette disposition :

     ↑   Ⓨ Ⓧ Ⓛ  
    ← →	 Ⓑ Ⓐ Ⓡ Ⓗ
     ↓  

Avec Ⓡ _= Gâchette droite = TR_, Ⓛ _= Gâchette gauche = TL_ and Ⓗ _= HK = Hotkey_  


Sur RPI B+, RPI2 et RPi3 vous devez connecter vos boutons en suivant ce pinout :  

![rpi2 pinout](https://www.dropbox.com/s/cxxl8fghke7xo4j/mk_joystick_arcade_GPIOsb%2B-hk-V2.jpg?raw=1)

Vous pouvez connecter vos boutons **directement à la masse** étant donné que le pilote active les _gpio internal pullups_.  


### Configuration ###
Dans [[recalbox.conf|recalbox.conf-(FR)]], activez le pilote GPIO en réglant controllers.gpio.enabled sur 1 : `controllers.gpio.enabled=1` et vous êtes prêt à jouer !  
Les GPIO sont configurés _out the box_ dans l'interface et les différents systèmes émulés.
