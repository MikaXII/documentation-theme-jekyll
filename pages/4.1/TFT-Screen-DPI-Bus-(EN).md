---
layout: page
title: TFT Screen DPI Bus (EN)
wikiPageName: TFT-Screen-DPI-Bus-(EN)
menu: wiki
---

# Configure your small TFT screen on DPI

## DPI (PARALLEL DISPLAY INTERFACE)
source  https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md

An up-to-24-bit parallel RGB interface is available on all Raspberry Pi boards with the 40 way header (A+, B+, Pi2, Pi3, Zero) and Compute Module. This interface allows parallel RGB displays to be attached to the Raspberry Pi GPIO either in RGB24 (8 bits for red, green and blue) or RGB666 (6 bits per colour) or RGB565 (5 bits red, 6 green, and 5 blue).

This interface is controlled by the GPU firmware and can be programmed by a user via special config.txt parameters and by enabling the correct Linux Device Tree overlay.

By sending the data via this parallel interface, with have no problem with Bus badwidth and display speed (FPS). But It uses almost all the GPIO pins.

This mode is very useful, you can tune very finely your display parameters : timings, resolutions etc.

This mode comes with new overlays, which allow you to produce a RGB signal thanks to the VGA666 (Gert Passive VGA adapter 666 for Raspberry-Pi B+ https://github.com/fenlogic/vga666) (http://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html). 

```ini
dtoverlay=vga666
```

You will be able to use the 5" http://www.adafruit.com/products/1596, 7" http://www.adafruit.com/products/2354 Adafruit TFT screen thanks to the  Adafruit DPI TFT Kippah for Raspberry Pi with Touch Support https://www.adafruit.com/products/2453

```ini
dtoverlay=dpi24
```

## Geekwrom HD 3.5 Inch TFT Display Shield 800x480 For Raspberry Pi 3B 2B

This screen has a small size, and provides a 800x480 resolution. Its specifications arte quite good : 

![hd-tftScreen.png](http://images.morere.eu/hd-tftScreen.png)

I found this amazing screen on the chinese site : http://www.banggood.com/Geekwrom-HD-3_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html for a price lower than 40€. 

It can be used as is, without the fbcp program. Fbcp is not more needed as the DPI mode uses directly the GPU.

To get the support of this screen, juste add the following lines your /boot/config.txt. 

Now you should use a SSH connection to your Raspberry Pi to make/check the following steps (see https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28EN%29).

Turn the filesystem in ReadWrite mode to be able to make the modifications :
```bash
mount -o remount, rw /boot
mount -o remount, rw /
```
Edit the /boot/config.txt file with nano or vim and add :

```ini
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

#Banggood
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off
enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=0x6f015
dpi_group=2
dpi_mode=87
hdmi_timings=480 0 16 16 24 800 0 4 2 2 0 0 0 60 0 32000000 6
display_rotate=3
```

Save the file and restart recalbox... it should be enough, you can now watch the amazing images displayed on this screen


[![Geekwrom HD 3.5 Inch TFT Display Shield 800x480](http://img.youtube.com/vi/qKdItNspYVM/0.jpg)](http://www.youtube.com/watch?v=qKdItNspYVM)


## Adafruit 5" and 7" TFT screen

To use these screen (https://www.adafruit.com/product/2353, https://www.adafruit.com/products/1596), you'll need the Adafruit DPI TFT Kippah for Raspberry Pi with Touch Support https://www.adafruit.com/products/2453 to make them work.

They use the DPI mode too. The configuration of the config.txt file is the following :

```ini
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0
#Adafruit
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x6f005
hdmi_timings=800 0 40 48 88 480 0 13 3 32 0 0 0 60 0 32000000 6
display_rotate=3
```
