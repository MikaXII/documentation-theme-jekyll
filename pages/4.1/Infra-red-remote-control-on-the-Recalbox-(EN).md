---
layout: page
title: Infra red remote control on the Recalbox (EN)
wikiPageName: Infra-red-remote-control-on-the-Recalbox-(EN)
menu: wiki
---

The Recalbox can be controlled by almost any infra red remote control.

This feature is for the Kodi media center.

The cost is about 2€ and it is quite simple to do.

**Warning**: require Recalbox 4.0.0 or over

# I - Requirements
## A - IR receiver
To make all this work, you need mainly one thing, an IR receiver : a 38KHz TSOP4838 module (it works with some other modules).
You can find it in any electronic shop for about 1€ or on internet on amazon, ebay, ...

For example, i got mine here :
- http://www.amazon.fr/s/field-keywords=38KHz+TSOP4838
- http://www.amazon.com/s/field-keywords=38KHz+TSOP4838

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/tsop.jpg)

## B - Jumpers female/female
To plug easyly your IR receiver, you need 3 jumpers. You can get them at the same place you get your IR receiver for some cents.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/jumpers.jpg)

## C - Schema
To plug the IR and the jumpers, use the following schema :

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/schema.png)

At the end, it looks like this :

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/montage.jpg)

## D - Remote control
Almost any remote control is supported, as soon it uses standards.

Personnaly, i've tested with success all the remotes of the house :
- the remote of the Philips hifi.
- the remote of the Samsung video recorder.
- an universal remote control.
- the remote of the Apple computer.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/remotes.jpg)

# II - Configuration
## A - config.txt
Open the file config.txt at the top of your sdcard (or /boot/config.txt from ssh)

Edit the following line and remove the #

 #dtoverlay=lirc-rpi

To get

 dtoverlay=lirc-rpi

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/config.png)

Reboot the system.

`reboot`

## B - Remote configuration
### 1. IR events check
Check that the hardware is working.
Connect to the Recalbox via ssh or directly on the terminal (see [[Root access on terminal|Root-access-on-terminal-(EN)]])
and run the following commands :
`lsmod`

You must find 1 line starting by lirc_rpi.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/lsmod.png)

Then, run the following command :
`mode2 -d /dev/lirc0 -r -m`

Each time you press a key on any remote control in the direction of the Recalbox, it will display numbers.
Press Ctrl+c to quit.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/mode2.png)

### 2. Record your remote

Type the following command : `irrecord -H default /tmp/custom.conf`

Press enter to continue.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord1.png)

Press enter to continue.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord2.png)

Now start pressing buttons on your remote control for approximately one second.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord3.png)

Enter the name of a button among the following names and press the button on your remote :
- KEY_LEFT (left)
- KEY_RIGHT (right)
- KEY_UP (up)
- KEY_DOWN (down)
- KEY_OK (ok)
- KEY_EXIT (back/quit)
- KEY_PLAY (play and pause)
- KEY_STOP (stop)
- KEY_VOLUMEUP (volume up)
- KEY_VOLUMEDOWN (volume down)
- KEY_INFO (display information about the playing media)
- KEY_MUTE (mute volume)
- KEY_POWER (quit)
- KEY_MENU (menu)

And eventually the following one :
- KEY_ENTER
- KEY_DELETE
- KEY_MEDIA
- KEY_RECORD
- KEY_PAUSE
- KEY_FASTFORWARD
- KEY_REWIND
- KEY_CHANNELUP
- KEY_CHANNELDOWN
- KEY_NEXT
- KEY_PREVIOUS
- KEY_EPG
- KEY_SUBTITLE
- KEY_LANGUAGE
- KEY_ZOOM
- KEY_VIDEO
- KEY_AUDIO
- KEY_NUMERIC_1
- KEY_NUMERIC_2
- KEY_NUMERIC_3
- KEY_NUMERIC_4
- KEY_NUMERIC_5
- KEY_NUMERIC_6
- KEY_NUMERIC_7
- KEY_NUMERIC_8
- KEY_NUMERIC_9
- KEY_NUMERIC_0
- KEY_RED
- KEY_GREEN
- KEY_YELLOW
- KEY_BLUE
- KEY_PVR
- KEY_RADIO

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord4.png)

Do the same for all (or a maximum) buttons of the remote.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord5.png)

When all the buttons are registered, press enter to continue and press an arbitrary button repeatedly as fast as possible. Make sure you keep pressing the SAME button and that you DON'T HOLD the button down!.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord6.png)

At the end, the program is automatically closed.

If you want to restart, remove the file by running : `rm /tmp/custom.conf` and restart the irrecord.

### 3. Configuration file

Edit the file by running the command : `nano /tmp/custom.conf`

Replace

 name  /tmp/custom.conf

by

 name  customremote

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/customremote.png)

Keep the file by running: `mv /tmp/custom.conf /recalbox/share/system/.config/lirc/lircd.conf`

Restart your Recalbox or just run the following command : `/etc/init.d/S25lircd restart`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/keeprestart.png)

### 4. Check custom remote event
Type the command `irw`

Each time your press a button on the remote, you will see a line with the name of the button.

Press ctrl+c to quit.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irw.png)

Now start Kodi and check it works ;-)

# III - Advanced configuration
## A - Lircmap.xml
You can customize the remote mapping by editing this file :

/recalbox/share/system/.kodi/userdata/Lircmap.xml

**Warning:** if you have removed manually the ~/.kodi directory and restart kodi without restarting the recalbox, you will not get the recalbox kodi customizations including the Lircmap.xml.

Consider copying /recalbox/share_init/system/.kodi/userdata/Lircmap.xml to /recalbox/share/system/.kodi/userdata/Lircmap.xml.

## B - remote.xml
You can edit the mapping between buttons and kodi action in this file :

/recalbox/share/system/.kodi/userdata/keymaps/remote.xml

## C - EXIT / STOP
About the fact that "Back" doesn't stop a film in Kodi :

If you don't like the default Kodi behavior or have only 1 button on your remote,

you can replace in the file remote.xml and in the section "&lt;FullscreenVideo&gt;", "&lt;back&gt;Back&lt;/back&gt;" by "&lt;back&gt;Stop&lt;/back&gt;"

## D - VOLUME UP/DOWN
This point is more for cec remote.

If your cec remote doesn't transfer the volume up/down, you can use some other key by replacing for example in the remote.xml in the global section :

      <skipplus>SkipNext</skipplus>
      <skipminus>SkipPrevious</skipminus>
by

      <skipplus>VolumeUp</skipplus>
      <skipminus>VolumeDown</skipminus>

## E - PAUSE on OK
I personnaly use the Refocus skin.
To make pause easier, mainly when using an Apple remote, you can :
modify the following file

~/.kodi/addons/skin.refocus/720p/VideoOSD.xml

by replacing

      <defaultcontrol always="true">700</defaultcontrol>

by

      <defaultcontrol always="true">705</defaultcontrol>
