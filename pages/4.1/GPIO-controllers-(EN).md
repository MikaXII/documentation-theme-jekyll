---
layout: page
title: GPIO controllers (EN)
wikiPageName: GPIO-controllers-(EN)
menu: wiki
---

recalboxOS is build with the [mk_arcade_joystick_gpio](https://github.com/digitalLumberjack/mk_arcade_joystick_rpi) driver that can manage a controller directly connected on rpi GPIO.

So if you plan to make a **Bartop**, **Arcade cab**, or a **portable panel**, you don't even need an usb controller.

The driver can manage up to **2 controllers** composed of a **4 direction joystick** and **9 buttons**.

If you are on a RPI1 B revision see directly the [mk_arcade_joystick pinout](https://github.com/digitalLumberjack/mk_arcade_joystick_rpi/blob/hotkeybtn/README.md#pinout)

### Pinout ###
Let's consider a 7 buttons cab panel with this button order : 

     ↑   Ⓨ Ⓧ Ⓛ  
    ← →	 Ⓑ Ⓐ Ⓡ Ⓗ
     ↓  

With Ⓡ _= Right trigger = TR_, Ⓛ _= Left trigger = TL_ and Ⓗ _= HK = Hotkey_


On RPI B+, RPI2 and RPi3 you must connect your buttons as specified by this pinout :  

![rpi2 pinout](https://www.dropbox.com/s/cxxl8fghke7xo4j/mk_joystick_arcade_GPIOsb%2B-hk-V2.jpg?raw=1)

You can connect you button **directly to the ground** as the driver enable _gpio internal pullups_.


### Configuration ###
In [[recalbox.conf|recalbox.conf-(EN)]], enable the gpio driver by setting controllers.gpio.enabled to 1 : `controllers.gpio.enabled=1` and you're done ! The GPIO are configured out of the box in the frontend and systems.
