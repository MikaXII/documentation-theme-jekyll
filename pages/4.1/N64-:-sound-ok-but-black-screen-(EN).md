---
layout: page
title: N64 : sound ok but black screen (EN)
wikiPageName: N64-:-sound-ok-but-black-screen-(EN)
menu: wiki
---

N64 emulator is in beta phase. Some games works perfectly, others not. When you launch a game, it may happen that you have sound but no video.

This a possible solution :

Press F4 to quit Emulationstation

Press ALT+F2 to display the command console

Login with "root" user and "recalboxroot" password

Enter:`` cd ../recalbox/scripts``

Enter: ``nano emulatorlauncher.sh`` to edit the file

Find those lines and replace "4" with "2"

``if [[ « $emulator » == « n64″ ]]; then /recalbox/scripts/runcommand.sh 4 « SDL_VIDEO_GL_DRIVER=/usr/lib/libGLESv2.so mupen64plus –corel…``

Press CTRL+X to quit editor then "Y" to save the changes.

Enter ``reboot`` to reboot the RaspBerry Pi.
