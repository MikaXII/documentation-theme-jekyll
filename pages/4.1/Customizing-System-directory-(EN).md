---
layout: page
title: Customizing System directory (EN)
wikiPageName: Customizing-System-directory-(EN)
menu: wiki
---

[Recalbox >= 4.0.0]

The recalbox.conf file allow you to configure and customize your recalbox, but you can go further by editing the **System directory**

This directory can be internal (on the sd card) in `/recalbox/share/system` or on an external device (usb key) in the `/recalbox/system` directory.

This directory is available :
- Via Samba (Windows share) on `smb://recalbox.local/system` (`\\recalbox.local/system` in Windows Explorer)
- Via ssh (`/recalbox/share`) or directly by plugging the sd card or the external device on a ext4 compatible OS

# Structure of the System directory
Not all these directories and files are present by default in your **System directory**.

Create them if you want to customize them.

<pre>
bios
cheats
extractions
kodi 
roms
   /snes
   /...
saves
screenshots
shaders
system
   /bluetooth
   /configs
   /logs
   /recalbox.conf
   /upgrade
   /ssh
   /.config
   /.emulationstation
      /es_input.cfg
      /es_settings.cfg
      /es_systems.cfg
      /themes
   /.kodi
   /.ssh
</pre>

# Usage
File contained in **System directory** have always the priority over *Default Recalbox Directory**.  
When a file is not found in the **System directory**, the **Default Recalbox Directory** will be used.

The **Default Recalbox Directory** has the same structure as the **System directory** allowing you to easily use it to copy files if required.

The **Default Recalbox Directory** is available :
- Via ssh (`/recalbox/share_init`)

| Directory or file | Usage | Initialisation on the system directory |
| :--------------: | :--------------: | :--------------: |
| bios | Emulation bios directory | copied
| cheats | Emulation cheats files | merged
| extractions | | copied
| kodi | Musics and videos | copied
| roms/snes(1) | Emulation system roms | copied
| saves | Emulation saves | copied
| screenshots | Emulation screenshots | copied
| shaders | Shaders | system
| system/bluetooth | Bluetooth associated devices | copied
| system/configs | Emulation and kodi automatic configurations | best for Kodi, copied for others
| system/logs | Recalbox logs | copied
| system/recalbox.conf | Recalbox configuration file | copied
| system/upgrade | Place for boot and root.tar.xz for upgrade | created when needed
| system/ssh | Recalbox ssh server side key | copied
| system/.config | Applications configurations (lirc) | copied
| system/.emulationstation/es_input.cfg | Joystick configurations | copied
| system/.emulationstation/es_settings.cfg | EmulationStation configuration | copied
| system/.emulationstation/es_systems.cfg | Recalbox emulator definition | best
| system/.emulationstation/themes | EmulationStation themes | merged
| system/.kodi | Kodi files | copied
| system/.ssh | Ssh client side key | copied

(1) When new systems are available, the new directory is created. If you want to reset the roms for a system, delete the directory and reboot.

_copied_ : at boot time, if the directory doesn't exist, it is created from the **Default Recalbox Directory**. You can delete it to reinitialiaze it. Note that almost all copied directories are empty or just contain a readme file.

_merged_ : both directories, **System directory** and **Default Recalbox Directory** are visible.

_default_ : the feature is not complete. For example the shader customisation is still not possible. Only the **System directory** is considered.

_best_ : use the **System directory** if it exists or fall back to the **Default Recalbox Directory**.

Merged and best allows the Recalbox developers to upgrade system files. However, it is not always wanted or possible without great amount of work.
