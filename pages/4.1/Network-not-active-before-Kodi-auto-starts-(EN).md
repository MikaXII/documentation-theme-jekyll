---
layout: page
title: Network not active before Kodi auto starts (EN)
wikiPageName: Network-not-active-before-Kodi-auto-starts-(EN)
menu: wiki
---

## Issue

When Kodi is set to auto-start on Recalbox, there is a possibility on some systems and networks where the network will not be fully active when Kodi launches.  This can cause issues for users that are using network shares and shared database across a network where their network access will not function.

## Pre 4.x.x work-around

The easiest work-around on pre 4.x.x of Recalbox is to quit Kodi and then re-launch it from Emulation Station, the network should be active by the time this process is followed.

## on Recalbox 4.x (future release)

In the recalbox.conf file on your system, look in **Section A - System Options** and find the following:

    ;kodi.network.waitmode=required
    ;kodi.network.waittime=10
    ;kodi.network.waithost=192.168.0.50

Un-comment out the lines by removing the semi-colons, and change their values to suit your needs.

_kodi.network.waitmode_
* **required** - Use this option if you want Kodi to simply not launch until it can reach the host
* **wish** - Use this option to utilize the wait time, but is not needed to be able to ping the host

_kodi.network.waittime_
* Time in seconds to wait until Kodi either fails(when required is selected above) or continues its launch (when wish is selected)

_kodi.network.waithost_
* The IP address of the system you want to test your network connection against
