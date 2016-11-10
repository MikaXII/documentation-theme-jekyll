---
layout: page
title: Skip noobs screen (EN)
wikiPageName: Skip-noobs-screen-(EN)
menu: wiki
---

You can win few seconds of boot time by forcing noob to boot on the `boot` partition directly.

Put your sd card in your personal computer. Open the `RECOVERY` partition and create a file named `autoboot.txt` 

Edit the file and add the following line : 

- With a recalbox in version 3.3.0
```
boot_partition=5
```

- With a recalbox in version 4.0.0
```
boot_partition=6
```

That will avoid the noobs screen and boot directly on recalboxOS.
If you want to reenable the noobs screen, just delete the `autoboot.txt` 
