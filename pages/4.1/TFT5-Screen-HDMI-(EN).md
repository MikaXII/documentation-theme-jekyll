---
layout: page
title: TFT5 Screen HDMI (EN)
wikiPageName: TFT5-Screen-HDMI-(EN)
menu: wiki
---

**Recalbox version** : any

# Configure your 5" HDMI TFT screen

You can find this screen at  : http://www.banggood.com/5-Inch-800-x-480-HDMI-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-B-A-B-p-1023438.html

It is the equivalent of the Adafruit device : https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview

You can make it work on Recalbox by configuring the /boot/config.txt file 

Remember, the TFP401 driver does not have a video scaler! If you don't feed it exactly 800×480 pixels the image will not stretch/shrink to fit! So we need to configure the resolution in the config.txt

Connect to your Pi (either SSH -> https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28EN%29 or on a local tty).

Make `/boot` writable to edit the required file :
```bash
mount -o remount, rw /boot
```
Edit the /boot/config.txt file with nano or vim and add :

```ini
# uncomment if hdmi display is not detected and composite is being output
hdmi_force_hotplug=1
 
# uncomment to force a specific HDMI mode (here we are forcing 800x480!)
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt=800 480 60 6 0 0 0
 
max_usb_current=1

```
The line `max_usb_current=1` increases the Pi max USB output current. This way your pi will supply enough power to your screen. Be sure that the main power supply is powerful enough for all your devices

If the image has not the good resolution during emulation, you'll need to edit the file `recalbox.conf` and change the `global.videomode` variable : 

```
global.videomode=default
```
to use the default configuration from the `config.txt`. Check this post to see this with pictures https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside

