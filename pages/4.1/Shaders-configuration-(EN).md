---
layout: page
title: Shaders configuration (EN)
wikiPageName: Shaders-configuration-(EN)
menu: wiki
---

### I - Introduction
Shaders are filters that can change the image you get while running your emulators. It's often used to get "retro" image apparence, close to the crt we played on.

The different files you have in recalbox are :
- **glsl** : the shader itself
- **glslp** : the shader preset. Can combine several shaders.
- /recalbox/share_init/system/configs/shadersets/**xxx.cfg** : the configuration files for the shadersets

The shaderset configuration file (**.cfg**) references a shader preset (**glslp**) for each system on the recalbox. Each **glslp** references one or several shaders (**glsl**)

### II - Shader sets
With shader sets, you can configure shaders for all your systems with one option. 

The sets are created by the community, and are optimized at each new recalbox version.  

Available sets : 
- **scanlines** : enable scanlines on all emulators
- **retro** : select the "best" shaders for each system, choosen by the community, that will offer you the closest to original gaming experience.
- **none** : no shaders

You can set the **shader set** you want to enable in the EmulationStation menu "GAME SETTINGS", or directly in [[recalbox.conf|recalbox.conf-(EN)]] with the `global.shaderset` option

### III - Custom Shaders
You can combine the power of the **shader sets** with the heavily customisation of recalbox.conf
The `global.shaderset` can set a base shader for each emulators. Then you can change the shader preset of a system with the `systemname.shader` option.
The default shaders presets are based in `/recalbox/share_init/shaders/`

For example, if I want the best shaders on all emulators, but no shaders for my gameboy, an already existing shader preset for megadrive, and a custom shader preset for my snes : 
```
# Set the retro shader set for all emulators, now i know that i have the best selection
global.shaderset=retro
# But my gameboy seem better for me with no shaders
gb.shaders=
# We use the already existing 4xbr_retro.glslp shader for megadrive
megadrive.shaders=/recalbox/share_init/shaders/4xbr_retro.glslp
# And i want to apply my own shader preset on snes
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```

You can also switch shaders in-game using your controller. Use the [Special commands](https://github.com/digitalLumberjack/recalbox-os/wiki/Manual-%28EN%29#duringgame-special) **Hotkey + R2** or **Hotkey + L2** to see the next or previous shader.

### IV - Screenshots
No shaders :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-no-filter.png)

With retro shader set :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-caligari-115.png)
