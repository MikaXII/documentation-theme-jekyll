---
layout: page
title: recalbox.conf (PT)
wikiPageName: recalbox.conf-(PT)
menu: wiki
---

O Recalbox tem uma ferramente avançada de configuração chamada recalbox.conf e permite que voce modifique algumas opções que não estão disponíveis no Emulationstation.

Voce pode editar esse arquivo de duas formas:

- Utilizando as pastas compartilhadas pela rede. O arquivo ficará disponível na pasta **system**
- Voce poderá se conectar como Root e editar o arquivo no próprio sistema através da pasta **/recalbox/share/system/recalbox.conf**

**Para usuários de Windows**: Voce deve editar esse arquivo com um editor de texto avançado, por exemplo NotePad++. Os editor de texto padrão do Windows pode inserir caracteres incorretos no arquivo.

O caractere ";" no começo da linha significa que aquela linha está desativada (ou comentada). Se voce remover o ; a linha estará ativa.

Esse arquivo não é sobrescrito durante a atualização do Recalbox. Porém o arquivo recalbox.conf.template será, então voce encontrará novas opções para ajustes nesse arquivo após a atualização.

### I - Opções disponíveis

#### A - Opções do Emulationstation:

- Ajustar o tipo de menu
- Ocultar o Kodi no Emulationstation
- Iniciar o Kodi automaticamente durante o boot
- Impedir que o botão X inicie o Kodi

#### B - Rede:

- Ajustar o hostname
- Configurar o wifi

#### C - Áudio:

- Selecionar a saída de som
- Ajustar o volume
- Ativar/Desativar as músicas de fundo

#### D - Controles:

- Selecionar o driver do controle de PS3
- Ativar/Desativar o xboxdrv
- Ajustar os controles no xboxdrv
- Ativar/Desativar controles na GPIO
- Ativar/Desativar controles na marqs DB9
- Ativar/Desativar controles na marqs gamecon

#### E - Idioma e teclado:

- Selecionar idioma
- Selecionar layout do teclado
- Selecionar o fuso horário

#### F - Atualizações:

- Ativar/Desativar checagem de atualização

#### G - Configurações da emulação:

- Detalhes abaixo

### II - Configurações da emulação

#### 1 - Configurações globais

Voce pode realizar ajustes detalhados nos emuladores através do recalbox.conf. A variável global ajusta as preferências para todos os emuladores.

**Variáveis disponíveis:**

- **videomode** : Seleciona a resolução de vídeo (utilize tvservice para conseguir os valores compatíveis). Utilize _default_ para desativar a mudança de resolução (indicado para monitores CRT)

Exemplo : `global.videomode=CEA 4 HDMI`

- **shaderset** : Ajusta o tipo de efeito de imagem para todos os emuladores (Nenhum, Retro, Scanlines). Acesse [[shaders configuration|Shaders-configuration-(EN)]]  (Ainda em Inglês)

Exemplo : `global.shaderset=retro`

- **shaders** : Indica o local onde estão presentes os efeitos de imagem (glsl ou glslp)

Exemplo : `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`

- **ratio** : Ajusta a proporção da tela para os jogos (16:9, 4:3, 16:10, automático ou personalizado)

Exemplo : `global.ratio=16/9`

- **smooth** : Ativa a suavização das imagens

Exemplo : `global.smooth=0`

- **rewind** : Ativa a opção de retroceder os jogos (pode causar lentidão na emulação)

Exemplo : `global.rewind=0`

- **inputdriver** : Força a escolha do tipo de drive de entrada utilizado no Retroarch (Automático, sdl2, udev)

Exemplo : `global.inputdriver=auto`

A configuração padrão é:

```
global.videomode=CEA 4 HDMI
global.shaders=
global.ratio=auto
global.smooth=1
global.rewind=0
global.inputdriver=auto`
```

Se deseja suavizar as imagens de todos os emuladores, ajuste `global.smooth=1`
Se deseja adicionar scanlines nas emulações, ajuste `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`

#### 2 - Configurações especificas dos emuladores

Cada emulador pode ser configurado individualmente através de configurações específicas. Coloque o nome do sistema à frente e então a variável que deseja modificar.

**Sistemas disponíveis:**

snes , nes , n64 , gba , gb , gbc , fds , virtualboy , sg1000 , mastersystem , megadrive , gamegear , sega32x , segacd , neogeo , mame , fba , fbalibretro , ngp , gw , vectrex , lynx , lutro , wswan , pcengine , atari2600 , atari7800 , msx , prboom , psx

**Libretro cores disponíveis:**

- snes : pocketsnes - snes9x_next - catsfc
- nes / fds : fceumm - fceunext - nestopia
- n64 : mupen64plus
- gb/gbc : gambatte - tgbdual
- virtualboy : vb
- megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 : genesisplusgx - picodrive
- neogeo : imame4all - fba
- mame : imame4all
- fbalibretro : fba
- ngp : mednafen_ngp
- gw : gw
- vectrex : vecx
- lynx : mednafen_lynx
- lutro : lutro
- wswan : mednafen_wswan
- pcengine : mednafen_supergrafx - pce
- atari2600 : stella
- atari7800 : prosystem
- msx : fmsx - bluemsx
- prboom : prboom
- psx : pcsx_rearmed
- cavestory : nxengine

**Variáveis disponíveis:**

- **videomode** : Seleciona a resolução de vídeo (utilize tvservice para conseguir os valores compatíveis). Utilize _default_ para desativar a mudança de resolução (indicado para monitores CRT)

Exemplo : `snes.videomode=CEA 4 HDMI`

- **shaders** : Indica o local onde estão presentes os efeitos de imagem (glsl ou glslp)

Exemplo : `snes.shaders=/recalbox/share/shaders/shaders_glsl/snes.glsl`

- **ratio** : Ajusta a proporção da tela para os jogos (16:9, 4:3, 16:10, automático ou personalizado)

Exemplo : `snes.ratio=4/3`

- **smooth** : Ativa a suavização das imagens

Exemplo : `snes.smooth=0`

- **rewind** : Ativa a opção de retroceder os jogos (pode causar lentidão na emulação)

Exemplo : `snes.rewind=0`

- **core** : Seleciona qual core voce deseja utilizar para o sistema (cores localizados em /usr/lib/libretro)

Exemplo : `snes.core=snes9x_next`

- **emulator** : Seleciona qual emulador voce deseja utilizar para a emulação (os emuladores são retroarch, fba2x, mupen64)

Exemplo : `neogeo.emulator=fba2x`

- **configfile** : Força a utlização de seu próprio arquivo de configuração para cada emulador. O Recalbox não utilizará nenhuma configuração automatizada.

Exemplo : `snes.configfile=/path/to/my/configfile.cfg`

### III - Arquivo recalbox.conf padrão

```
# System Variable
# You can configure your recalbox from here
# To set a variable, remove the first ; on the line


# ------------ A - ES Options ----------- #
## EmulationStation menu style
## default -> default all options menu
## none -> no menu except the game search menu
## bartop -> less menu, only needed for bartops
system.es.menu=default

## Show or hide kodi in emulationstation (0,1)
kodi.enabled=1
## Start kodi at launch (0,1)
kodi.atstartup=0
## set x button shortcut (0,1)
kodi.xbutton=1



# ------------ B - Network ------------ #
## Set system hostname
system.hostname=RECALBOX
## Activate wifi (0,1)
wifi.enabled=0
## Wifi SSID (string)
;wifi.ssid=new ssid
## Wifi KEY (string)
;wifi.key=new key



# ------------ C - Audio ------------ #
## Set the audio device (auto, hdmi, jack)
audio.device=auto
## Set system volume (0..100)
audio.volume=90
## Enable or disable system sounds in ES (0,1)
audio.bgmusic=1



# -------------- D - Controllers ----------------- #
## Please enable only one of these

# -------------- D1 - PS3 Controllers ------------ #
##Enable PS3 controllers support
controllers.ps3.enabled=1
## Choose an driver beetween official, shanwan and gasia if you have dualshock clones (official,shanwan,gasia)
controllers.ps3.driver=official


# ------------ D2 - XBOX Controllers ------------ #
## Xbox controllers are already supported, but xboxdrv can solve some compatibility issues 
## Enable xboxdrv driver, disable this if you enabled ps3 controllers (0,1)
controllers.xboxdrv.enabled=0
## Set the amount of controllers to use with xboxdrv (0..4)
controllers.xboxdrv.nbcontrols=2


# ------------ D3 - GPIO Controllers ------------ #
## GPIO Controllers
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
## mk_gpio arguments, map=1 for one controller, map=1,2 for 2 (map=1,map=1,2)
controllers.gpio.args=map=1,2


## DB9 Controllers
## Enable DB9 drivers for atari, megadrive, amiga controllers (0,1)
controllers.db9.enabled=0
## db9 arguments
controllers.db9.args=map=1

## Gamecon controllers
## Enable gamecon controllers, for nes, snes psx (0,1) 
controllers.gamecon.enabled=0
## gamecon_args
controllers.gamecon.args=map=1



# ------------ F - Language and keyboard ------------ #
## Set the language of the system (fr_FR,en_US,en_GB,de_DE,pt_BR,es_ES)
system.language=en_US
## set the keyboard layout (fr,en,de,us,es)
;system.kblayout=us
## Set you local time
## Select your timezone from : ls /usr/share/zoneinfo/ (string)
;system.timezone=Europe/Paris



# ------------ G - UPDATES ------------ #
## Automatically check for updates at start (0,1)
updates.enabled=1



# ------------ H - HERE IT IS - GLOBAL EMULATOR CONFIGURATION ------------ #
## The global value will be used for all emulators, exept if the value
## is redifined in the emulator

## Set game resolution for emulators
## select your mode from the command : tvservice -m [MODE]
## CEA 5 HDMI : 1920x1080 @ 60Hz 16:9, clock:74MHz interlaced 
## CEA 4 HDMI : 1280x720 @ 60Hz 16:9, clock:74MHz progressive
## use 'default' for using the default resolution
## (string)
global.videomode=CEA 4 HDMI

## Shader set 
## Automatically select shaders for all systems
## (none, retro, scanlines)
global.shaderset=none

## Set gpslp shader for all emulators (prefer shadersets above). Absolute path (string)
global.shaders=

## Set ratio for all emulators (auto,4/3,16/9,16/10,custom)
global.ratio=auto

## Set smooth for all emulators (0,1)
global.smooth=1

## Set rewind for all emulators (0,1)
global.rewind=0

## Set retroarch input driver (auto, udev, sdl2)
## If you don't have issues with your controllers, let auto
global.inputdriver=auto

## If you do not want recalboxOS to generate the configuration for all emulators (string)
;global.configfile=/path/to/my/configfile.cfg

# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
## Here is the snes example
;snes.videomode=CEA 4 HDMI
;snes.core=snes9x_next
;snes.shaders=/recalbox/share/shaders/shaders_glsl/mysnesshader.gplsp
;snes.ratio=16/9
;snes.smooth=0
;snes.rewind=1
;snes.emulator=libretro
## If you do not want recalboxOS to generate the configuration for the emulator : 
;snes.configfile=/path/to/my/configfile.cfg

## NeoGeo emulator 
## You can use pifba or a libretro core (fba2x,libretro)
neogeo.emulator=fba2x
## If you set libretro as neogeo.emulator, uncomment the line below and set the retroarch core (fba,imame4all)
;neogeo.core=fba

## N64 core (n64,rice)
## The recommanded plugin is n64, but if your game don't start, try rice (example Zelda Ocarina of Time, Banjo Kazooie, ...)
n64.core=n64
n64.videomode=CEA 4 HDMI

## If you use rice core, set mode 480p as below
;n64.core=rice
;n64.videomode=CEA 3 HDMI
```
