---
layout: page
title: TFT Screen SPI Bus (EN)
wikiPageName: TFT-Screen-SPI-Bus-(EN)
menu: wiki
---

This integration method is temporary and for Recalbox 4.0. With the next release 4.1, most of the manipulations will be superfluous due to the fbcp program integration.

# Configure your Adafruit 2,8" capacitive/resistive TFT screen

This screen can be found at https://www.adafruit.com/product/1601. As the overlays already exist for this screen in the directory `/boot/overlays`, it will be supported with a simple configuration. 

```bash
pitft28-capacitive.dtbo
pitft28-resistive.dtbo
```
Check if you have the capacitive or resistive version of the screen and adjust the dt-overlay line in `/boot/config.txt`.

This screen uses the SPI bus to be driven. It's low resolution allows us to get a good frame rate in emulators framerates. Not really 60fps, but more than the minimum of 30 fps thanks to the `fcbp` modified program (see https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29). 

To get the this screen work, you need to had these lines in the `/boot/config.txt` file :
```ini
#overclocking extreme
arm_freq=1100
core_freq=550
sdram_freq=600
over_voltage=8
over_voltage_sdram=6
force_turbo=1
 
dtparam=spi=on
dtparam=i2c1=on
dtparam=i2c_arm=on
#forcing HDMI output at TFT screen resolution to be able to make the FB copy
#resolution configuration
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2
hdmi_mode=87
# working config for speed
# 900 Mhz -> 48000000
# 1Ghz -> 35000000
#modification of the speed   
dtoverlay=pitft28-resistive,rotate=90,speed=22000000,fps=60
```
The overclocking section is not required, and is confiured for a Pi1.

The SPI bus speed has to be adjusted if you overclock your raspberry Pi to get a good image. These settings have been tested on a Raspberry P1 at 1.1Ghz. 

For a start you can try : 
```ini
dtoverlay=pitft28-resistive,rotate=90,speed=32000000,fps=20
```
In the case of a capacitive screen, just replace by 
```ini
dtoverlay=pitft28-capacitive,rotate=90,speed=32000000,fps=20
```

When rebooting, the screen should start with a white screen and after a few seconds, it should turn black. It's the sign that the screen is now supported. But you'll get no images until you are not running `fbcp`.

Now you should use a SSH connection to your Raspberry Pi to make/check the following steps (see https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28EN%29).

Get or compile the right binary from https://github.com/ian57/rpi-fbcp according to your Pi version. Copy it in the `/usr/bin` directory. You'll need to get write access on the system for that :
```bash
mount -o remount, rw /boot
mount -o remount, rw /
```
We can test the screen display by running the `fbcp`program from the ssh connection with the following command :

```bash
fbcp
```
just type CTRL-C to stop the display. If it works, we can go further and run `fcbp` at Recalbox boot.

Create a new file named `S11fbcp` in `/etc/init.d/` :

```bash
#!/bin/sh
 
case "$1" in
        start)
                printf "Starting fbcp ... "
                start-stop-daemon -S -q -m -b -p /var/run/fbcp.pid --exec /usr/bin/fbcp -- -n
                echo "done."
                ;;
        stop)
                printf "Stopping fbcp ..."
                start-stop-daemon -K -q -p /var/run/fbcp.pid
                echo "done."
                ;;
        restart)
                $0 stop
                sleep 1
                $0 start
                ;;
        *)
                echo "usage: $0 {start|stop|restart}"
                ;;
esac
```
Make it runnable :
```bash
chmod 755 S11fbcp
```
This script will be launch at recalbox startup, and will run the `fbcp` program

Modifiy the ̀recalbox.conf` file like :

```ini
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Save the file, and reboot. The screen should now work perfectly. If you encounter some problems, first check that the `fbcp` program is running with : 

```bash
ps aux | grep fbcp
```

This 2,8" screen works well but can be too small and too expensive (35€) regarding the chinise clones. Let's configure a Waveshare 3,2" TFT screen found on Banggood for a price lower than 15€

# Configure your Waveshare 3,2" resistif TFT screen

The screen is the following http://www.banggood.com/3_2-Inch-TFT-LCD-Display-Module-Touch-Screen-For-Raspberry-Pi-B-B-A-p-1011516.html. A 3.2 Inch TFT LCD Display Module Touch Screen For Raspberry Pi B+ B A+. It's resolution is the same as the 2,8" : 320x240. It is actually a waveshare screen http://www.waveshare.com/3.2inch-rpi-lcd-b.htm. 

This screen is not supported by default by the kernel's overlays. We'll need to add the specific ones to make the screen work. 

These files can be found at the following address : https://github.com/swkim01/waveshare-dtoverlays

Get the files  `waveshare35a-overlay.dtb` and `waveshare32b-overlay.dtb` respectively for the WaveShare 3,2" 320x240 screen and the WaveShare 3,5" 320x480 screen. For the new 4.4 kernels, we have to rename the dtb files in dtbo files to match the new overlay tree naming. Rename `waveshare35a-overlay.dtb` to `waveshare35a.dtbo` and ̀waveshare32b-overlay.dtb` to ̀waveshare32b.dtbò and copy them in the `/boot/overlays directory

Now we modify the ̀`/boot/config.txt` file to support the new screen :

```ini
#tft screen
 
#Waveshare 3.2 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2                
hdmi_mode=1                 
hdmi_mode=87                
 
dtparam=spi=on              
dtoverlay=waveshare32b:rotate=270,speed=82000000
```

We can test the screen by running the `fbcp` program with :
```bash
fbcp
```
just type CTRL-C to stop the display. If it works, we can go further and run `fcbp` at Recalbox boot.

Create a new file named `S11fbcp` in `/etc/init.d/` :

```bash
#!/bin/sh
 
case "$1" in
        start)
                printf "Starting fbcp ... "
                start-stop-daemon -S -q -m -b -p /var/run/fbcp.pid --exec /usr/bin/fbcp -- -n
                echo "done."
                ;;
        stop)
                printf "Stopping fbcp ..."
                start-stop-daemon -K -q -p /var/run/fbcp.pid
                echo "done."
                ;;
        restart)
                $0 stop
                sleep 1
                $0 start
                ;;
        *)
                echo "usage: $0 {start|stop|restart}"
                ;;
esac
```
Make it runnable :
```bash
chmod 755 S11fbcp
```
This script will be launch at recalbox startup, and will run the `fbcp` program

Modifiy the ̀recalbox.conf` file like :

```ini
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Save the file, and reboot. The screen should now work perfectly. If you encounter some problems, first check that the `fbcp` program is running with : 

```bash
ps aux | grep fbcp
```

A working screen in video :

[![Waveshare 3,2" resistif TFT](http://img.youtube.com/vi/hcFk_vjQLVo/0.jpg)](http://www.youtube.com/watch?v=hcFk_vjQLVo)

https://youtu.be/hcFk_vjQLVo


# Why is the  Waveshare 3,5" resistif TFT screen is not usable with Recalbox

This screen cannot be used for arcade with Recalbox. The SPI bus does not have sufficient bandwidth to deal with this higher 480x320 resolution. If you increas the bus speed the display becomes unstable (colors, flickering). During my tests I only be able to get 20-25 FPS. This screen is usable with an X server  with slow frame rate but not in arcade mode which requires higher frame rates. 

As described in this page https://learn.adafruit.com/running-opengl-based-games-and-emulators-on-adafruit-pitft-displays/3-dot-5-pitft, it is not recommended to use this screen for gaming. "With twice as many pixels to push to the screen, the 3.5" PiTFT is noticably slower than its more compact brethren and we strongly recommend against it for gaming." Now you konw!

But if you want to make if work, you can follow this : 

Get the files  `waveshare35a-overlay.dtb` and `waveshare32b-overlay.dtb` respectively for the WaveShare 3,2" 320x240 screen and the WaveShare 3,5" 320x480 screen. For the new 4.4 kernels, we have to rename the dtb files in dtbo files to match the new overlay tree naming. Rename `waveshare35a-overlay.dtb` to `waveshare35a.dtbo` and ̀waveshare32b-overlay.dtb` to ̀waveshare32b.dtbò and copy them in the `/boot/overlays directory

Now we modify the ̀`/boot/config.txt` file to support the new screen :

```ini
#tft screen
#Waveshare 3.5 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=480 320 60 1 0 0 0
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
 
dtparam=spi=on
dtoverlay=waveshare35a:rotate=270,speed=27000000
```

We can test the screen by running the `fbcp` program with :
```bash
fbcp
```
just type CTRL-C to stop the display. If it works, we can go further and run `fcbp` at Recalbox boot.

Create a new file named `S11fbcp` in `/etc/init.d/` :

```bash
#!/bin/sh
 
case "$1" in
        start)
                printf "Starting fbcp ... "
                start-stop-daemon -S -q -m -b -p /var/run/fbcp.pid --exec /usr/bin/fbcp -- -n
                echo "done."
                ;;
        stop)
                printf "Stopping fbcp ..."
                start-stop-daemon -K -q -p /var/run/fbcp.pid
                echo "done."
                ;;
        restart)
                $0 stop
                sleep 1
                $0 start
                ;;
        *)
                echo "usage: $0 {start|stop|restart}"
                ;;
esac
```
Make it runnable :
```bash
chmod 755 S11fbcp
```
This script will be launch at recalbox startup, and will run the `fbcp` program

Modifiy the ̀recalbox.conf` file like :

```ini
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=3/2
```

Save the file, and reboot. The screen should now work perfectly. If you encounter some problems, first check that the `fbcp` program is running with : 

```bash
ps aux | grep fbcp
```


A working 3,5 screen with FPS issues in video :

[![Waveshare 3,5" resistif TFT](http://img.youtube.com/vi/HJXQAEaVhKE/0.jpg)](http://www.youtube.com/watch?v=HJXQAEaVhKE)

https://youtu.be/HJXQAEaVhKE
