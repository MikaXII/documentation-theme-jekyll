---
layout: page
title: Añadir Bios de sistemas (ES)
wikiPageName: Añadir-Bios-de-sistemas-(ES)
menu: wiki
---

Algunos emuladores necesitan bios para poder emular juegos de forma correcta. 
Si quieres añadir Bios a tu sistema, debes abrir la carpeta compartida de bios con samba, o ir directamente a /recalbox/share/bios/

Para revisar si el md5sum de tus bios es el correcto revisa [Revisar MD5 checksum](Revisar MD5 checksum (ES)).

El nombre y el MD5 crc de tus bios debe ser igual a los de la siguiente lista:

```
- Sega 32X :

6a5433f6a132a2b683635819a6dcf085  32X_G_BIOS.BIN
f88354ec482be09aeccd76a97bb75868  32X_M_BIOS.BIN
7f041b6a55cd7423a6c08a219335269e  32X_S_BIOS.BIN


- Sega MEGA CD :
854b9150240a198070150e4566ae1290  us_scd2_9306.bin
d8b8b720dea6c6ba25c309ed633930f4  eu_mcd2_9306.bin
bdeb4c47da613946d422d97d98b21cda  jp_mcd1_9112.bin


- FAMICOM DISK SYSTEM :
ca30b50f880eb660a320674ed365ef7a  disksys.rom


- PLAYSTATION :
924e392ed05558ffdb115408c263dccf  SCPH1001.BIN


- GAMEBOY ADVANCE :
a860e8c0b6d573d191e4ec7db1b1e4f6  gba_bios.bin


- PCENGINE CD :
ff1a674273fe3540ccef576376407d1d  syscard3.pce


- MSX :
d6dedca1112ddfda94cc9b2e426b818b  CARTS.SHA
85b38e4128bbc300e675f55b278683a8  CYRILLIC.FNT
80dcd1ad1a4cf65d64b7ba10504e8190  DISK.ROM
af8537262df8df267072f359399a7635  FMPAC16.ROM
6f69cc8b5ed761b03afd78000dfb0e19  FMPAC.ROM
c83e50e9f33b8dd893c414691822740d  ITALIC.FNT
febe8782b466d7c3b16de6d104826b34  KANJI.ROM
2183c2aff17cf4297bdb496de78c2e8a  MSX2EXT.ROM
7c8243c71d8f143b2531f01afa6a05dc  MSX2PEXT.ROM
6d8c0ca64e726c82a4b726e9b01cdf1e  MSX2P.ROM
ec3a01c91f24fbddcbcab0ad301bc9ef  MSX2.ROM
6418d091cd6907bbcf940324339e43bb  MSXDOS2.ROM
aa95aea2563cd5ec0a0919b44cc17d47  MSX.ROM
403cdea1cbd2bb24fae506941f8f655e  PAINTER.ROM
279efd1eae0d358eecd4edc7d9adedf3  RS232.ROM

- LYNX :
fcd403db69f54290b51035d82f835e7b  lynxboot.img

-ATARI 7800 :
0763f1ffb006ddbe32e52d497ee848ae  7800 BIOS (U).rom   

-ATARI ST : 
b2a8570de2e850c5acf81cb80512d9f6  tos.img   

-ODYSSEY2/VIDEOPAC :
562d5ebf9e030a40d6fabfc2f33139fd  o2rom.bin   
```

* NEO-GEO: Si quieres jugar juegos de NEO-GEO, debes añadir las Bios en la misma carpeta asociada al emulador, la misma en la que guardas las Roms de dicho sistema.

El nombre y el Checksum de las bios debe coincidir con los siguientes:

```
FBA and FBA Libretro
798e5538be8b6557e7c4529f52d2938c  neogeo.zip
Mame (Pimame4all)
12f370a3fc42c3e413c4a0771d6d089f  neogeo.zip
```
