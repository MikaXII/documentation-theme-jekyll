---
layout: page
title: Spiele mit zwei GameBoys (DE)
wikiPageName: Spiele-mit-zwei-GameBoys-(DE)
menu: wiki
---

Mit ***recalbox*** ist es möglich 2-Player-Games auf dem GameBoy zu spielen, indem zwei GameBoys emuliert werden.  
  
Ändere die [[recalbox.conf|recalbox.conf-(DE)]]-Datei und ersetze den GameBoy-Emulator durch `tgbdual`.  
  
    # ------------ I - EMULATORS CHOICES ----------- #
    ## You can override the global configuration here
    ## For GameBoy
    gb.core=tgbdual
    gb.ratio=custom
    ## For GameBoyColor
    gbc.core=tgbdual
    gbc.ratio=custom
  
Speichern und ***recalbox*** neustarten.  
  
Starte ein GameBoy Spiel, z.B. _Balloon Kid_. Öffne danach das RetroArch-Menüt mit **Hotkey+B** und ändere die folgenden Parameter:  
  
    Setting / Configuration / Save Configuration On Exit : ON
    Quick menu / Core Options / GB Link Enable (restart) : enabled
    Quick menu / Core Options / Screen placement (restart) : horizontal
    Quick menu / Core Options / Switch player screens : normal ; player 1 to the left player two to the right
    Quick menu / Core Options / Show player screens : both players
    Settings / Video / Aspect Ratio Index : 20:9 (1:1 PAR) ; 100% conform GB ratio 
    Quick menu / Restart Content
  
Du kannst die Einstellung `Save Configuration On Exit` wieder zurück auf `OFF` setzen, wenn du das Spiel neugestartet hast. Falls du das nicht machst ist die Gefahr grösser, dass ungewollte Änderungen beim Beenden von RetroArch gespeichert werden.  
  
Wenn dein Fernseher nicht auf 16:9 eingestellt ist, wird das Verhältnis falsch sein. Das erkennst du, wenn das ***recalbox***-Menü nicht auf den ganzen Bildschirm passt.  
  
Beachte, dass 1-Spieler-Games ebenfalls geteilt werden. Zwei GameBoys Seite an Seite können z.B. nützlich sein für ein Speedrun-Battle, sonst aber ziemlich sinnlos.  
  
Um zu viele Änderungen zu vermeiden können diese Einstellungen auch nur für eine einzige Konsole (z.B. den GameBoy oder GameBoy Color) geltend gemacht werden.  
