---
layout: page
title: recalboxOS detalhado (PT)
wikiPageName: recalboxOS-detalhado-(PT)
menu: wiki
---

**recalboxOS** é um sistema operacional de código fonte aberto. Ele é uma distribuição baseada no linux, otimizada para processadores de arquitetura ARM do  RaspberryPI.

## Buildroot
**recalboxOS** é compilado com buildroot.

Buildroot é uma ferramenta simples, eficiente e fácil de usar para criar sistemas Linux incorporado através de cross-compilation. Ele compila todo sistema recalboxOS e softwares do código fonte, e cria os arquivos que serão copiados para seu cartão SD na instalação.

Ele cria um sistema Linux incorporado mínimo, correspondendo exatamente ao que voce quer que seu sistema tenha.
É por isso que o recalboxOS não possui gerenciador de pacotes, compiladores, cabeçalhos, etc...

## Projetos
**recalboxOS** é o principal projeto, que agrega 4 sub-projetos compondo o sistema :

- **recalbox-buildroot** :
https://github.com/digitalLumberjack/recalbox-buildroot (braço do recalbox)
O projeto recalbox-buildroot é um sistema buildroot. Ele cria todo sistema linux que será executado no recalbox. Voce poderia compilar esse projeto, então copiar os arquivos de saída para um cartão SD formatado manualmente para rodar o sistema no raspberryPi. Porém existe um caminho melhor chamado recalbox-rescue.

- **recalbox-rescue** :
https://github.com/digitalLumberjack/recalbox-rescue (braço do recalbox)
Baseado no incrível NOOBS da equipe do rpi, o recalbox rescue permite voce instalar facilmente o  recalboxOS e ter a partição de recuperação no seu cartão SD. É um outro sistema operacional mínimo que fará o download do recalboxOS, formatar seu cartão SD e instalar o sistema para voce.
Ele checará se uma nova versão está disponível a partir da internet antes de instalar a versão do cartão SD. 

- **recalbox-emulationstation** :
https://github.com/digitalLumberjack/recalbox-emulationstation/tree/recalbox-buildroot
Baseado no incrível emulationstation 2 desenvolvido por Aloshi, a interface gráfica sofreu pequenas modificações para ter suporte a músicas de fundo para cada sistema, seleção de idioma e configuração de controles.

- **recalbox-configgen** :
https://github.com/digitalLumberjack/recalbox-configgen
Ferramenta de configuração automática de emulador

Se voce quiser se aprofundar e aprender como compilar e modificar o recalboxOS, vá em [[Compilação & Modificações|Compilação-&-Modificações-(PT)]]

## Partições
O recalboxOS é configurado para rodar 3 partições :
- A primeira partição do tipo FAT32, chamada de BOOT, montada em /boot no sistema, que contém todos os arquivos do processo de boot
- A segunda partição do tipo EXT4, chamada de root, montada em / no sistema, que contém todo o sistema
- A terceira partição do tipo FAT32, chamada de SHARE, montada em /recalbox/share no sistema, contendo todas as roms, bios, saves e screenshots.
