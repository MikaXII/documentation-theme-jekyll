---
layout: page
title: Troubleshooting controllers (EN)
wikiPageName: Troubleshooting-controllers-(EN)
menu: wiki
---

There are a few useful commands to get devices information that should be run in order to help finding solving problems :
- `cat /proc/bus/input/devices` to show a list of available devices
- `lsusb -v` to get USB peripherals information
- `for i in /dev/input/event*; do echo $i;udevadm info -q all -n $i;done` to get udev information on devices that were mapped to an event
- ` for i in /dev/input/event*; do echo $i;(evtest $i) & ( evtestpid=$! && sleep 0.1 && kill -15 $evtestpid );done` will list all buttons/axes/keys found (even if it's a keyboard)

Whenever you run one of these commands, it's best not to paste the full output on the forum or irc. Instead, use something like http://pastebin.com/, paste your output, then give the link to the people you're talking with
