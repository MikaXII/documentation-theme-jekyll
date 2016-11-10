---
layout: page
title: Scraping artwork quickly using Fullscrape
wikiPageName: Scraping-artwork-quickly-using-Fullscrape
menu: wiki
---

Currently this method is dependent on the version of Recalbox you are using

For 3.3.0 17 or previous see the following documentation


 Step 1.  Connect to your raspi.  On windows you can use putty  and just open a connection to your ip and use root for username  recalboxroot for password.  

Or from a terminal client
>ssh root@yourip   

Step 2. Paste the following command 
> wget https://raw.githubusercontent.com/substring/fullscrape/master/fullscrape.sh && chmod u+x ./fullscrape.sh

Step 3.  Initiate an individual scrape request system by system  
For example to do SNES  see below
> ./fullscrape.sh snes -no_thumb=true -max_width=375

To do nes 
> ./fullscrape.sh nes -no_thumb=true -max_width=375

Using the rom folder name as reference. Just a list of examples of systems you can use are 

cavestory
fba
fbalibretro
fds
gamegear
gb
gba
gbc
gw
lutro
lynx
mame
mastersystem
megadrive
moonlight
msx
n64
neogeo
ngp
pcengine
prboom
psx
scummvm
sega32x
segacd
sg1000
snes
vectrex
virtualboy
wswan


If you want to update or only add images that have not already been scraped you can do 

> ./fullscrape.sh -u  -no_thumb=true -max_width=375   


Things to keep in mind.
To run the ./fullscrape.sh script you must be in the directory that you originally downloaded it to in the first step. 

Image art is stored in the directory /root/.emulationstation/downloaded_images/     
the gamelist.xml file is stored in the directory /root/.emulationstation/gamelists
each in their respective named folder

WARNING : fba_libretro has a little bug, that will be corrected in 4.0.0 : scraping can’t be displayed. This can be manually solved if you really really are desperate …






For Recalbox 4.0 or later please do all the same just simply change the first step with

> wget https://raw.githubusercontent.com/substring/fullscrape/4.0.0/fullscrape.sh && chmod u+x ./fullscrape.sh

