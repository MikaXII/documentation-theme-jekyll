---
layout: page
title: Manual (PT)
wikiPageName: Manual-(PT)
menu: wiki
---

# recalbox 3.3.X
## Manual v1.0.3

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.com

- I - Primeira utilização
- II - Configuração
 - A - Controles
  - 1 - Controles de PS3
  - 2 - Controles de XBox 360
  - 3 - Instalando um controle bluetooth
  - 4 - Configurando um controle
  - 5 - Mapeamento de botões
  - 6 - Mapeamento do teclado
  - 7 - Controles GPIO
  - 8 - Controles virtuais
 - B - Opções de sistema
- III - EmulationStation
 - A - Apresentação
 - B - Opções
  - 1 - Opções de sistema
  - 2 - Opções de jogo
  - 3 - Opções de controle
  - 4 - Opções de interface
  - 5 - Opções de áudio
  - 6 - Opções de rede
 - C - Controles
 - D - Favoritos
 - E - Scraper
- IV - Durante o jogo
 - A - Saves
 - B - Comandos especiais
- V - Atualizações
- VI - Características de rede
 - A - Adicionando seus jogos
 - B - Jogos do Scummvm
 - C - Screenshots
 - D - Salvando seus saves
- VI - Kodi Media Center
- VIII - Solução de problemas
 - A - Controles
 - B - Outros
 - C - Hard reset
 - D - Usuário Root
- IX - recalbox.conf


### Introdução
O recalbox é um sistema que permitirá que você jogue retrogames facilmente.

Ele roda num mini computador chamado Raspberry Pi, e utiliza um grupo de emuladores otimizados.

### I - Primeira utilização
O pacote necessário:
- Um Raspberry Pi 1 ou 2
- Cartão SD de 16GB ou maior
- Cabo HDMI
- Fonte de energia micro USB de pelo menos 1.5A
- Um controle USB ou Bluetooth

Acesse recalbox.com/diy para mais informações no caso de primeira instalação.

Após a [[Instalação|Instalação-(PT)]], o primeiro passo que deve ser feito é conectar o Recalbox na TV através do cabo HDMI.

Para ligar o Recalbox, apenas conecte seu RPi na tomada.

Muitos controles funcionam por padrão, porém se voce deseja configurar diretamente um controle USB, ligue um teclado USB em seu RPi e veja a seção "Configurando um controle".

Para desligar o sistema: aperte o botão Menu e escolha a opção “SAIR” e “DESLIGAR O SISTEMA”.  
Então, você pode desconectar o cabo de força da placa.

### II - Configuração

#### A - Controles

Controles de PS3 e XBox 360 possuem suporte wireless. Muitos controles USB e Bluetooth também possuem suporte. Para mais informações consulte a seção [Periféricos compatíveis](https://github.com/digitalLumberjack/recalbox-os/wiki/Perif%C3%A9ricos-Compat%C3%ADveis-%28PT%29)

##### 1 - Controles de PS3
Voce precisa ter um dongle Bluetooth para utilizar os controles sem fio de PS3. Voce não pode carregar as baterias do controle no USb do RPi, voce deve fazê-lo conectando seu controle em qualquer carregador USB.

Conecte o controle na USB do RPi somente se voce quiser utilizá-lo em seu Recalbox. Para fazê-lo, conecte o controle e espere 10 segundos. Então desconecte o controle e pressione o botão Home (PS Logo).

Para controles não oficiais (GASIA ou SHANWAN). Acesse [[PS3 controllers drivers|PS3-controllers-drivers-(EN)]] (Ainda em Inglês)

##### 2 - Controles de XBox 360

Os controles de XBox 360 sem fio precisam do receptor de sinal USB.
Se voce tem um controle de XBox 360 com fio ou sem fio, ative-os no recalbox.conf seguindo as instruções do link [xboxdrv no recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28PT%29)

##### 3 - Instalando um controle Bluetooth

Para instalar um controle Bluetooth, ajuste seu controle para o modo de pareamento.
Então vá no menu utilizando um teclado e acesse "Opções de Controle", então selecione "Parear um controle Bluetooth"

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair.jpg)

Uma lista de controles detectados surgirá, então selecione o seu controle para ser pareado!
Agora configure-o manualmente caso ele não seja um controle suportado!

Para usuários de 8bitdo, acesse [[8bitdo on recalbox|8bitdo-on-recalbox-(EN)]]. (Ainda em Inglês)

##### 4 - Instalando um controle Bluetooth

Você pode adicionar controles USB no recalbox.

A maioria dos modelos são compatíveis, acesse a [lista de compatibilidade](https://github.com/digitalLumberjack/recalbox-os/wiki/Perif%C3%A9ricos-Compat%C3%ADveis-%28PT%29).

Depois de plugar seu controle USB ou parear seu controle Bluetooth, aperte o START com um controle já configurado ou (ou ENTER no teclado) e selecione a opção “Configuração de controles”.

Então siga as instruções.

O último botão, o ** HOTKEY ** é um botão que ativará combinações com outros botões (Veja a seção Comandos Especiais do manual). É recomendado utilizar o **L3** (para controles com analógico) ou o botão **SELECT**.

Os nomes dos botões são baseados no controle de Super Nintendo:
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

Os botões L2, R2, L3 e R3 são baseados nos controles de Playstation.

Pule a configuração dos botões que não existem em seu controle pressionando qualquer botão por 2 segundos.
 
Volte para a tela de configuração, atribua o controle para um jogador. Pronto, seu controle agora está configurado !

##### 5 - Mapeando botões

Para controles de 6 botões (SNES, PSX, Arcade etc) os botões são mapeados para corresponder ao controle original.   
Para controles de 2 botões (NES, PC Engine, Gameboy etc) os botões utilizáveis são B e A.

##### 6 - Mapeando teclado
Se você falhou totalmente na configuração dos controles, você pode conectar um teclado USB no recalbox.
Enter é START, Barra de espaço é SELECT, Q é VOLTAR, S é OK.

##### 7 - Controles GPIO
Você pode conectar seus controles e botões diretamente na GPIO do Raspberry Pi. Acesse [[Controles GPIO|GPIO-controllers-(EN)]] (Ainda em Inglês) para maiores informações.

Voce pode conectar controles originais de PSX, NES, SNES, Megadrive (Genesis) entre outros.

##### 8 - Controles virtuais

Utlizando os controles virtuais Miroof voce pode instalar até 4 controles utilizando seus celulares! Para instalá-los acesse o navegador de internet do seu celular e digite o IP de seu Recalbox seguido pela porta de comunicação (porta = 8080). Para saber seu IP acesse a seção Opções de rede em seu manual.

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones-350px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones.png)

Para mais informações acesse [[Controles virtuais|Virtual-Gamepad-(EN)]] (Ainda em Inglês).

#### B - Opções de sistema

Voce pode configura seu Recalbox de duas maneiras:

* Utilizando a interface gráfica do Emulationstation (Veja a seção Emulationstation para mais detalhes)
* Através da configuração do arquivo [[recalbox.conf|recalbox.conf-(PT)]], lá voce pode fazer ajustes mais detalhados

### III - EmulationStation

#### A - Apresentação

Quando você iniciar o Recalbox, a interface gráfica Emulationstation surgirá.
Você pode selecionar seus sistemas e carregar os jogos a partir dela.

A primeira tela é a tela de sistema : 

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)

Ela mostrará todos os sistemas disponíveis.

#### B - Opções

Pressionando o Start, voce poderá mudar algumas configurações do sistema.

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings.jpg)

##### 1 - Opções de sistema

Voce poderá acessar as informações do sistema, mudar o idioma do Emulationstation, alterar as opções de overclocking, atualizar seu Recalbox e ajustar o Kodi..

No RPi 1, voce poderá realizar o overclocking nas seguintes opções (ordem de velocidade):

NONE < HIGH < TURBO < EXTREM

A opção EXTREM pode violar os termos de garantia do seu RPi 1 mas é a opção que dará a melhor performance para todos os emuladores no RPi 1.

Caso queira emular jogos de N64, é recomendado que voce faça overclocking no RPi 2.

##### 2 - Opções de jogos

Voce pode ajustar as seguintes opções: proporção de vídeo (16:9, 4:3), suavização das imagens e retroceder jogos.

A opção de retroceder jogos permite que voce volte numa determinada cena ou parte do jogo. (Se voce caiu no buraco tentando pegar o cogumelo verde no Super Mario World, entenderá a utilidade da função!)

:warning: _Essa função pode causar perda de velocidade em alguns emuladores (SNES, PSX) se voce ativá-lo por padrão. Voce pode ajustar quais emuladores terão essa função através do [[recalbox.conf | recalbox.conf (PT)]]

##### 3 - Opções de controle

Voce poderá configurar seus controles e mapear os botões da maneira que desejar.

##### 4 - Opções de Interface 

Voce terá acesso as opções de ajuste da interface do Emulationstation. Voce poderá ajustar o uso do overscan caso tenha problemas com bordas pretas ou tela cortada. Acesse [[Opções de Overscan|Overscan-settings-(EN)]] para mais informações (Ainda em Inglês)

##### 5 - Opções de áudio

Voce poderá desligar a trilha sonora do Emulationstation, ajustar o volume e escolher por onde o som sairá no RPi (Escolha automática, HDMI, P2).

##### 6 - Opções de rede

Voce poderá ativar e configurar uma conexão wifi e o hostname de seu Recalbox, pegar o IP de seu Recalbox. É necessário teclado para escrever o nome da rede wifi bem como a senha do wifi.

Existe um bug conhecido no qual voce não consegue digitar todos os caracteres necessários para o nome de sua rede ou senha. Por conta disso, é possível configurar o wifi no arquivo [[recalbox.conf | recalbox.conf (PT)]]

#### C - Controles

** Comandos da interface: **

A --> Selecionar
B --> Voltar
Y --> Favoritos
X --> Executa o Kodi
Start --> Menu
Select --> Opções
R --> Página seguinte
L --> Página anterior

Quando voce seleciona um sistema com o A, a tela mostrará todos os jogos disponíveis daquele sistema.

Caso queira retornar à interface durante uma emulação, consulte a seção do manual "Durante o jogo" para verificar o comando para isso.

#### D - Favoritos

Voce pode estabelecer um jogo como favorito pressionando o botão Y. O jogo ficará no topo de sua lista com uma ☆ antes do nome. Caso queria tirar do favorito aperte Y novamente. Voce precisará desligar o sistema apropriadamente dentro do Emulationstation para que seus favoritos sejam salvos e apresentados na próxima reinicialização do sistema.

#### D - Scraper

Para cada jogo, voce pode pegar a capa e algumas informações que serão apresentadas enquanto voce navega pela lista de jogos no Emulationstation. Para executar o Scraper, aperte START e vá para a opção Scraper. Então siga as instruções.

### IV - Durante o jogos

#### A - Saves 
Os emuladores possuem uma característica muito útil: save states. Um save state é um salvamento rápido de um jogo e permite que você recarregue o jogo daquele exato ponto.

Com save states, você nunca mais precisará procurar por savepoints novamente!

É possível salvar mais de um save state por jogo se você mudar o slot de salvamento.

Para usar o save state pressione **Hotkey + Y**

#### B - Comandos especiais
Quando você está em um jogo, os comandos especiais são disponibilizados

Aperte o hotkey mais um dos botões listados abaixo para executar os seguintes comandos: 

Y -> Salva um save state
X -> Carrega um save state  
Start -> Sair do jogo
B -> Menu do RetroArch
Up -> Muda para o slot de salvamento anterior (save state)
Down -> Muda para o slot de salvamento seguinte (save state)
L1 -> Screenshot  
Right -> Acelera o jogo
Left -> Retrocede o jogo (caso ativo)
R2 -> Muda para o efeito de tela seguinte
L2 -> Moda para o efeito de tela anterior

No FBA e no Mame, apertar o Select adiciona um crédito. No Mame, se seu Hotkey é o Select, o comando para sair da emulação passará a ser R1 + Start (dessa forma o Select preservará a função de adicionar fichas).

Voce poderá acessar as configurações do Retroarch através do Hotkey + B. Se voce quiser configurar o Retroarch e salvar as configurações, voce pode selecionar a opção "Save Settings on Exit" no menu do Retroarch. Após isso, toda configuração feita no Retroarch será salva.

### V - Atualizações
A atualização do recalbox pode ser feita no menu da interface gráfica. Conecte um cabo de rede no recalbox ou rede wifi, aperte o Start e então selecione 'Atualizar sistema' com o botão A.

Depois da atualização, o sistema será reiniciado.

### VI - Características de rede
Se você conectar um cabo de rede ou wifi no recalbox, ele compartilhará arquivos com sua rede local. No seu computador, entre em Redes no Windows Explorer e selecione o Recalbox :

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau-recalbox.jpg)

Se voce não consegui encontrar o Recalbox na sua lista de dispositivos de rede, tente digitar **\\RECALBOX** na barra de endereço. Caso não funcione, vá no menu do Recalbox, nas Opções de Rede e anote o número do IP. Então digite seu IP na barra de endereço, por exemplo \\192.168.1.30

Você pode acessar todas as pastas compartilhadas do recalbox :

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau.jpg)

#### A - Adicionando seus jogos
Copie os arquivos para a pasta correspondente.  
Voce pode utilizar tanto arquivos .zip quando roms descompactadas..

Não hesite em compartilhar seus jogos favoritos no fórum do recalbox !
http://blog.recalbox.fr/forums/

B - Jogos de Scummvm

Quando voce adicionar um jogo de Scummvm, é necessário descompactar os arquivos para uma pasta. Nessa pasta voce deverá ser incluído um arquivo com o nome [gameshortname].scummvm

Voce poderá encontrar os shortnames para todos os jogos suportados no site http://scummvm.org/compatibility/

Por exemplo, se voce copiar a pasta "Broken Sword 1" dentro da pasta scummvm, será necessário criar um arquivo, dentro dessa pasta, chamado sword1.scummvm

Seu jogo aparecerá na interface gráfica e voce poderá modificar seus metadados caso queira mostrar o nome completo do jogo.

#### C - Screenshots
Aperte Hotkey + L1 nos emuladores para tirar uma screenshot. O arquivo de extensão png é salvo na pasta “screenshots”, voce pode acessá-la através da rede.  
Compartilhe seus melhores screenshots conosco em http://blog.recalbox.com/forums/

#### D - Salvando seus saves
A pasta “sauvegardes” compartilhada com o recalbox contém todos os saves e save states. Voce pode copiá-los se voce quer guardá-los em algum local seguro.

### VII - Kodi Media Center

Pressionando o botão X no seu controle, voce executará o Kodi Media Center (conhecido também como XBMC). Voce também pode acessá-lo pressionando o START e executando-o a partir do menu.

Para sair do Kodi, selecione a opção "QUIT" no programa, com isso voce voltará ao Recalbox.

### VIII - Solução de problemas

#### A - Controles :

- O controle de PS3 está piscando mas não está associado
Conecte o controle no recalbox e espere 10 segundos. Voce pode agora desconectar o controle e apertar o botão Home (Logo PS).

- O controle de PS3 parece morto
Voce deve reiniciar o controle pressionando um pequeno botão atrás do controle em um pequeno buraco com um clips de papel.

#### B - Outros

- Bordas pretas e imagem grande demais
Tente ativar o Overscan no menu do recalbox na opção "System Settings".
Utilize o controle remoto de sua televisão para procurar o menu de imagem, e ajuste o tamanho da tela para “1:1 pixel” ou “Completa”. Se não funcionar, voce deve ativar o Overscan no Recalbox através do menu Opções de sistema. Acesse [[Opções de Overscan|Overscan-settings-(EN)]] para mais informações.

- Tela preta num monitor de PC
Caso seu monitor (HDMI ou DVI) esteja apresentando tela preta, modifique o arquivo config.txt e remova a linha hdmi_drive=2. Mais informações em [[Mini HowTo - Connect your recalbox to a DVI screen|Connect-your-recalbox-to-a-DVI-screen-(EN)]] (Ainda em Inglês)

#### C - Hard reset
- Se voce quiser reiniciar o sistema, conecte um teclado usb e aperte a tecla Shift no processo de boot do RPi. Voce pode reinstalar o recalboxOS a partir desse processo. Todos os seus dados serão excluídos.

#### D - Acesso Root

- Utilize como nome do usuário **root** e a senha **recalboxroot**
- Voce pode se conectar ao Recalbox via ssh
- Voce pode também acessar o terminal saindo do Emulationstation pressionando o F4 ou ALT+F2 no teclado

Mais informações em [[Mini HowTo - Root access on terminal|Root-access-on-terminal-(EN)]] (Ainda em Inglês)

### IX - recalbox.conf

O arquivo **recalbox.conf** que é compartilhado na rede (via Samba) através do diretório **system** é utilizado para modificar outras configurações que não estão presentes na Interface. Acesse [[recalbox.conf | recalbox.conf (PT)]] para mais detalhes.
