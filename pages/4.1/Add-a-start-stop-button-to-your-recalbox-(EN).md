---
layout: page
title: Add a start stop button to your recalbox (EN)
wikiPageName: Add-a-start-stop-button-to-your-recalbox-(EN)
menu: wiki
---

You can add a Power button to start/stop your **recalbox** since 4.0 beta 3.  
The button can either be a push button, aka _momentary switch_ or a ON/OFF button aka _latching switch_.  
![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/switch/switch-battle.jpg)

To wire the switch to the Raspberry Pi GPIO, just connect one pin to the **GPIO3** (the **fifth** gpio from top left), and an other to the ground on its right (the **sixth** gpio):  
![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/switch/button-wire.png)


Last but not least, you must activate the support of your Power button in [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29), by adding/uncommenting one of the lines :  
- `system.power.switch=PIN56ONOFF` for a latching switch
- `system.power.switch=PIN56PUSH` for a momentary switch

And you have a recalbox that can be turned on/off with a simple button !

-----------------------------------

Since Recalbox 4.0 beta 4, there is another option where you can put additionally a Reset button and a Power LED.

In recalbox.conf, add/uncomment the following line:

- `system.power.switch=PIN356ONOFFRESET`

The Power button only works with latching switch in this mode and it's wire like in others modes, **GPIO3** and ground.

The Reset button only works with momentary switch and it's wire to the Raspberry Pi GPIO by one pin to the **GPIO2** (the **third** gpio from top left), and an other to the same ground as ON/OFF switch (the **sixth** gpio).

The Power LED is connected by anode (+,long pin) to **GPIO14** (the **eighth** gpio) and also by cathode (−,short pin) to the ground (the **sixth** gpio). The GPIO14 supply 3.3V so if you have a LED that requires less than 3.3V (most of red, orange, yellow and green LED) you have to add a resistor between anode(+) and GPIO14, to avoid burn out the LED. If you have a LED that requires more than 3.3V, you don't need a resistor but your LED emit less light than it should.

To sum up:
* one switch Power pin on **GPIO 3** (**PIN 5**)
* one switch Reset pin on **GPIO 2** (**PIN 3**)
* Led anode (+,long pin) on a resistor pin (or directly on **GPIO 14** (**PIN 8**) if you don't need a resistor)
* other resistor pin on **GPIO 14** (**PIN 8**) (if you need a resistor)
* other switch Power pin, other switch Reset pin and Led cathode (−,short pin), the three pins on **Ground** (**PIN 6**)

The resistor that you need for the LED is calculated by<br />
(Volt.Power − Volt.LED) ÷ Ampere.LED = Ohms.Resistor<br />
So for a red LED 2.25V 20mA (warning, there are many different LED, a lot, even with the same color)<br />
(3.3V - 2.25V) ÷ 0.02A = 52.5Ω (a resistor 52.5Ω don't exist, so, in this case a resistor 56Ω will be fine)<br />
If you take a resistor with lower Ohms than the result, the LED is brighter but it can burn out or shorten its lifetime.<br />
If you take a resistor with higher Ohms than the result, the LED is less bright and it's safe.<br />
If you have a negative result, your LED is too powerfull, you don't need a resistor but your LED emit less light than it should, but it's safe.<br />
And if you want your LED emit less light, choose an higher resistor or add a resistor if you have not added one. If you want your LED emit more light, don't, choose another LED. 
