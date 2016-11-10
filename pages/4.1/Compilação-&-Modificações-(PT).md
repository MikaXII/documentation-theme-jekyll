---
layout: page
title: Compilação & Modificações (PT)
wikiPageName: Compilação-&-Modificações-(PT)
menu: wiki
---

Lá vamos nós. Voce quer compilar o recalboxOS. Talvez queira acrescentar seus próprios componentes para o sistema operacional.
Tenha certeza que voce entendeu os diferentes projetos que compõe o recalboxOS : [[recalboxOS detalhado|recalboxOS-detalhado-(PT)]]

O que será mostrado a seguir é como voce pode compila os projetos e criar o recalboxOS no cartão SD manualmente. Se voce deseja apenas jogar, vá para [[Instalação|Instalação-(PT)]].

## I - Processo de compilação
A primeira coisa a ser feita é compilar o projeto recalbox-buildroot.
Então voce terá que escolher :  
- Compilar o sistema recalbox-rescue e utilizá-lo para instalar o recalbox-os.
- Criar as partições manualmente no seu cartão SD e instalar o recalboxOS diretamente (não explicado nesse tutorial)

### A - recalbox-buildroot

Para compilar o recalbox buildroot, instale as seguintes dependências :
```
sudo apt-get install build-essential git libncurses5-dev qt5-default qttools5-dev-tools mercurial libdbus-glib-1-dev texinfo zip imagemagick subversion
```

Então clone o repositório e selecione o braço do recalbox. Será utilizado a variável arch para determinar qual versão do RPi será utilizada (rpi ou rpi2)
```
arch=rpi2
git clone https://github.com/digitalLumberjack/recalbox-buildroot.git recalbox-buildroot-${arch}
cd recalbox-buildroot-${arch}
```

Crie a configuração da arquitetura com um defconfig
```
make recalbox-${arch}_defconfig
```

E execute o make para compilar o sistema
```
make
```

No fim da compilação voce terá que lembrar de 3 coisas :  
- O arquivo output/images/rootfs.tar.xz é seu arquivo de sistema root.
- O arquivo output/images/recalbox/boot.tar.xz é a a partição boot do recalbox.
- O arquivo output/images/recalbox/share.tar.xz é sua partição share

### B - recalbox-rescue

Se voce instalou as dependências do recalbox-buildroot, apenas clone e compile o projeto recalbox-rescue:

```
git clone https://github.com/digitallumberjack/recalbox-rescue
cd recalbox-rescue
git checkout dual
lupdate -no-obsolete recovery/recovery.pro
./BUILDME.sh
```

No fim da compilação, os arquivos de sistema do recalbox-rescue que voce copiará para o cartão SD estarão no diretório `output/`

### C - Criando um cartão SD

Agora que o recalbox-buildroot e o recalbox-rescue foram compilados, será necessário criar o cartão SD. Criaremos um diretório que representará a raiz do seu cartão SD. Só será preciso copiar todos esses arquivos para esse diretório num cartão SD formatado em FAT32. Para fazer isso voltaremos ao diretório de trabalho e então:

```
cd ..
mkdir SDCONTENT
```

Agora podemos copiar o recalbox-rescue para essa pasta

`cp -r recalbox-rescue/output/* SDCONTENT`

O recalbox-rescue precisa de 3 arquivos para fazer a instalação do Recalbox em 3 partições:

- O arquivo boot.tar.xz será extraído para a primeira partição, tipo FAT32, chamada BOOT, montada em  /boot no sistema
- O arquivo root.tar.xz será extraído para a segunda partição, tipo EXT4, chamada root, montada em / no sistema
- O arquivo share.tar.xz será extraído na terceira partição, tipo FAT32, chamada SHARE, montada em /recalbox/share no sistema

Lembre-se de selecionar qual RPi voce utilizará através da variável arch!

Para copiar os 3 arquivos utilizaremos um único comando:

`cp recalbox-buildroot-${arch}/output/images/recalbox/*.tar.xz SDCONTENT/os/recalboxOS-${arch}/`

Ok agora voce pode copiar todos os arquivos da pasta SDCONTENT para seu cartão SD!

Inicie seu RPi e agora voce terá um Recalbox!

## II - Modificações
Há dois importantes diretórios na fonte do recalbox-buildroot :
- `board/recalbox/fsoverlay/` é o diretório que contém os arquivos que serão substituídos ou adicionados na partição root. Por exemplo `board/recalbox/fsoverlay/etc/fstab` substitui o arquivo fstab do buildroot original para montar as partições do recalbox nos pontos de montagem customizados. Então se voce tem arquivos de configuração, assets, etc, voce terá que adicioná-los aqui.
- `package` é o diretório que contém todos os descritores de pacotes. Muitos software estão disponíveis mas se voce quiser adicionar seu próprio software, deverá ser feito aqui.

#### 1 - Configuração
Voce pode configurar o sistema com
```
make menuconfig
```
Esse menu mostrará a configuração do sistema e a seleção de pacotes. Ele salvara a configuração para o arquivo `.config`

#### 2 - Adicionando pacotes
Se voce quiser adicionar um pacote, voce pode se basear num pacote existente. Vamos usar o pacote `recalbox-emulationstation` como estudo de caso :
``` 
$ ls package/recalbox-emulationstation/
Config.in  recalbox-emulationstation2-000-cmakelist.patch  recalbox-emulationstation2.mk
```

O arquivo Config.in será utilizado pelo buildroot para pegar as informações no pacote, dependências, mensagens, etc,...

Todo arquivo .patch será executado antes da compilação.

O arquivo mk contém os comandos para configuração, construção e instalação do software.

Uma vez que voce copiou e modificou seu pacote, modifique o arquivo `package/Config.in`. Ele listará todos os pacotes disponíveis para o menuconfig. Adicione seu novo pacote nesse arquivo e então rode o comando `make menuconfig` a partir da raiz do projeto. Voce verá seu novo pacote na lista alvo de pacotes!

Tenha certeza de checar duplamente os nomes das variáveis nos arquivos. Para o restante, a documentação do buildroot é muito clara : http://buildroot.uclibc.org/downloads/manual/manual.html
