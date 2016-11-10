---
layout: page
title: Utility   Use of fbcp for small TFT screen (EN)
wikiPageName: Utility---Use-of-fbcp-for-small-TFT-screen-(EN)
menu: wiki
---

This page is under construction. feel free to correct it and append it ;)

# What is fbcp

https://github.com/tasanakorn/rpi-fbcp

This program used for copy primary framebuffer to secondary framebuffer (eg. FBTFT). It require lastest raspberry pi firmware (> 2013-07-11) to working properly.

fbcp takes a snapshot of `/dev/fb0`, copies it to `/dev/fb1` and waits 25ms before repeating.
Snapshotting takes ~10ms and with a 25ms delay it gives roughly 1000/(10+25) = 28fps
CPU usage: ~2%
Note: Snapshot and `/dev/fb1` driver refresh is not syncronized.

# Why do we need fbcp

As Recalbox does not use use Xorg or another Graphic server, all displays are made on the first frame buffer (`/dev/fb0`) (HDMI or composite output) which use the power of the GPU and hardware acceleration. 

In the case of the use of Xorg, we can easily redirect the display on the /dev/fb1. This is not as simple with the framebuffer mode of Recalbox. Even if it is achievable with some program thanks to environment variable in some cases https://github.com/notro/fbtft/wiki/Framebuffer-use.

In the case of the use or an SPI/I2C TFT screen, this new screen gets the second framebuffer (`/dev/fb1`) and dos not take profit of the GPU.

And in the case of recalbox, all programs send their displays on `/dev/fb0`. So if you try to use it with a small I2C/TFT screen, you'll get no display at all even if your display is well configured and activated.

So fbcp allows you to display the content of `/dev/fb0`thanks to taken snapshot. 

This method is not needed in the case of screen which use the DPI display mode https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md

# Modified version of the recalbox fbcp program

https://github.com/ian57/rpi-fbcp

Actually, fbcp is not yet included in recalbox, but it should be available in the 4.1 release.
the original program has been modofoed to try to get more than 28 FPS, with reducing the wait time :

```c
//usleep(25 * 1000);
usleep(5 * 1000); //only 5 ms to try to get 60fps
```

If you want to try it, you can to compile it or get the right binary from https://github.com/ian57/rpi-fbcp according to your Pi version.

To compile it, you can get my rb-4.1.X-fbcp branch or just add the  `rpi-fbcp` directory in the package directory https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcp/package/rpi-fbcp with its 2 makefiles to make a try.

This program does not require a lot of dependance and should compile on 4.0 and 4.1 releases. To create and install the program in your recalbox-buildroot tree, just run `make rpi-fbcp` at your recalbox-buildroot tree root directory. You'll get the `fbcp` program in the output/target/usr/bin directory when the compilation will finished.

After that juste run the global `make` to create the recalbox img file with the fbcp program, or just copy it to the `/usr/bin` directory of the recabox partition of your recalbox SD card. 

After that, read the page https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29 to configure your screen and run it at startup.


