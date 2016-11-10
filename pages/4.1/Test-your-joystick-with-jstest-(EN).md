---
layout: page
title: Test your joystick with jstest (EN)
wikiPageName: Test-your-joystick-with-jstest-(EN)
menu: wiki
---

In order to test the buttons and axis of your joysticks, you can use the binary `jstest` that report all events concerning a joystick.

First get a [root access on a terminal](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29)

To know if your joysticks are detected by the system, use :
```
cat /proc/bus/input/devices
```

Once your joysticks are detected, a special event file should have been created for each one, you can see those special files by listing the /dev/input files :
```
ls /dev/input/js*
```

Now you can pass the special file path as an argument to jstest, to test your buttons and axis.
For example, to test the first joystick on the system : 
```
jstest /dev/input/js0
```

You should see the following output : 
```
Driver version is 2.1.0.
Joystick (Logitech Logitech Cordless RumblePad 2) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnTR2, BtnSelect, BtnStart, BtnMode, BtnThumbL, BtnThumbR).
Testing ... (interrupt to exit)
Axes:  0:     0  1:     0  Buttons:  0:off  1:off  2:off  3:off  4:off  5:off  6:off  7:off  8:off  9:off 10:off 11:off
```

And now you can check each button and axis response.
