---
layout: page
title: Change RetroArch Menu to use XMB Driver Menu (EN)
wikiPageName: Change-RetroArch-Menu-to-use-XMB-Driver-Menu-(EN)
menu: wiki
---

# Introduction

The aim is to change from rgui Menu Driver to xmb menu driver

# Steps
1. Launch a game
2. go into retroArch main menu
3. Within updater, update assets
4. exit game
5. in SSH, add menu_driver = "xmb" in configs/retroarch/retroarchcustom.cfg

# Optional

**change xmb background image to have for example un transparent background and still see the paused game**

1. Upload a 1920*1080 png transparent image or whatever image you want for background
2. in SSH, update menu_wallpaper = "~/.config/retroarch/assets/wallpapers/your_uploaded_file.png
