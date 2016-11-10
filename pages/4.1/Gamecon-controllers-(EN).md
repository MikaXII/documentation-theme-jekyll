---
layout: page
title: Gamecon controllers (EN)
wikiPageName: Gamecon-controllers-(EN)
menu: wiki
---

# 1 - Intro

The driver is designed to be used with retro game controllers connected to Raspberry Pi's GPIO. Currently, up to 4 controllers of following types are supported:
- NES gamepads
- SNES gamepads
- PSX/PS2 gamepads
- N64 gamepads
- Gamecube gamepads
	
The driver is based on gamecon driver, but uses different pinout and parameters. No warranty - use at your own risk.


# 2 - Connecting the controllers


Pins P1-01 and P1-06 are used as common power and ground for all controllers. Note that 3.3V is used for all controllers, even if SNES&NES pads nominally are operated at 5V. They should work fine with 3.3V so no level shifters are needed for data pins. The maximum current spec (50mA) should be enough for 4 controllers. However, use a proper ac adapter with Pi to avoid any unwanted voltage drops.


Pins P1-03,05,07,26 (GPIO0, GPIO1, GPIO4 and GPIO7) are independent data pins, one per pad.
NOTE: P1-03 & P1-05 correspond to GPIO2 G GPIO3 in rev.2 board, which must taken into account when loading the module. This is explained in section 3.


Pins P1-19 & P1-23 (GPIO10 & 11) are common signal pins for all NES/SNES pads.
Pins P1-08, P1-10 & P1-12 (GPIO14, 15 & 18) are common signal pins for all PSX/PS2 pads.


## 2.1 NES & SNES gamepads
| Rpi pin        | SNES controller pin | NES controller pin |
| -------------- |:-------------------:|:------------------:|
| P1-01 (3.3V)   | 1 (power - 5V)      | 1 (power - 5V)     |
| GPIO10	 | 2 (clock)           | 5 (clock)          |
| GPIO11         | 3 (latch)           | 6 (latch)          |
| GPIOXX         | 4 (data)            | 7 (data)           |
| P1-06 (GND)    | 7 (ground)          | 4 (ground)         |


Nes and snes Pinout : 

![snes nes pinout](https://i.warosu.org/data/vr/img/0027/22/1444150264652.png)


GPIOXX is the independent data pin. See section 3 on how to select the correct GPIO.


## 2.2 N64 pads
| Rpi pin        | N64 controller pin  |
| -------------- |:-------------------:|
| P1-01 (3.3V)   | power (leftmost)    |
| GPIOXX         | data (middle)       |
| P1-06 (GND)    | ground (rightmost)  |
			

GPIOXX is the independent data pin. See section 3 on how to select the correct GPIO.

N64 controller pinout:  
![](http://s.hswstatic.com/gif/n64-pinout.gif)


## 2.3 Gamecube pads
| Rpi pin        | Gamecube controller pin  |
| -------------- |:------------------------:|
| P1-01 (3.3V)   | 6 (power/3.43V)          |
| GPIOXX         | 3 (data)                 |
| P1-06 (GND)    | 2&5 (gnd)                |

GPIOXX is the independent data pin. See section 3 on how to select the correct GPIO.

Gamecube Pinout :  
![](http://ezhid.sourceforge.net/gcpad.png)


## 2.4 PSX/PS2 pads
| Rpi pin        | PSX controller pin       |
| -------------- |:------------------------:|
| P1-01 (3.3V)   | 5 (VCC)           |
| GPIO14         | 2 (Command)              |
| GPIO15         | 6 (ATT)               |
| GPIO18         | 7 (CLK)                |
| GPIOXX         | 1 (Data)                 |
| P1-06 (GND)    | 4 (ground)               |

GPIOXX is the independent data pin. See section 3 on how to select the correct GPIO.

![](http://www.geocities.ws/digitan000/Hardware/22/pinout.gif)

# 3. Configuring the driver

## 3.1 Configure pads
Enable the gamecon driver in recalbox.conf [[recalbox.conf|recalbox.conf-(EN)]] by setting `controllers.gamecon.enabled=1`

Use the following pad indexes to configure the `controllers.gamecon.args` :  
`map=<pad1/GPIO0>,<pad2/GPIO1>,<pad3/GPIO4>,<pad4/GPIO7>,<pad5/GPIO2>,<pad6/GPIO3>`  
where <pad...> is a number defining the pad type:
- 0 = no connection
- 1 = SNES pad
- 2 = NES pad
- 3 = Gamecube pad
- 6 = N64 pad
- 7 = PSX/PS2 pad
- 8 = PSX DDR controller
- 9 = SNES mouse 
	
For example, if a snes pad is connected to GPIO4 and a N64 pad to GPIO7, the map would be `map=0,0,1,6`.

**IMPORTANT NOTE**: **pad1 & pad2 are only used with rev.1 board, and pad5 and pad6 with rev.2. So if you have rev.2 board (rpi b+, zero and rpi2 are rev2) , pad1 and pad2 must be set as 0.
So you will probably have : `controllers.gamecon.args=map=0,0,X,X`**

The final pad index (used by the programs) is assigned sequentially for connected pads starting from 0. So in the previous example, snes pad would get index 0 and N64 pad index 1.

Use "tail /var/log/kern.log" to verify that module loading was successful


## 3.2 Testing the pads
See [[Test your joystick with jstest mini how-to|Test-your-joystick-with-jstest-(EN)]]
	

## 3.3 Calibrating the axis of N64 analog pad
```
jscal -s 4,1,0,0,0,6972137,6972137,1,0,0,0,6547006,6468127,1,0,0,0,536854528,536854528,1,0,0,0,536854528,536854528 /dev/input/jsX
```
for each N64 controller


## 3.4 Setting access delay for psx pads

The access delay for PSX pads is set to 10us, which minimizes the performance penalty caused by the driver. However, in some rare cases it may not be enough to get stable input. If you have issues when reading psx pads, raise the delay with following extra modprobe parameter: "psx_delay=<delay>". <delay> is value in us, and can be set between 1-50. 


## 5  More information
http://www.raspberrypi.org/phpBB3/viewtopic.php?f=78&t=15787

Credits to marqs. Thank you for the drivers and for letting us use your README for the wiki.
