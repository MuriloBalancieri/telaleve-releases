# TelaLeve — Downloads e versões

Compartilhamento de tela e webcam por P2P. Este repositório público guarda instaladores, pacotes e o histórico das distribuições, sem os ZIPs de código-fonte.

**[Baixar o instalador mais recente](https://github.com/MuriloBalancieri/telaleve-releases/releases/latest)** · **[Histórico completo](https://github.com/MuriloBalancieri/telaleve-releases/releases)** · **[Mudanças por versão](CHANGELOG.md)**

## Instalar

1. Na release mais recente, baixe **TelaLeve-Setup-0.13.0.exe**.
2. Encerre a versão anterior pelo ícone da bandeja e execute o instalador.
3. Abra o TelaLeve pelo atalho e crie uma sala ou entre com um convite.
4. Compartilhe tela e/ou webcam somente quando quiser.

A instalação é por usuário, com atalhos e desinstalador. Não precisa instalar Node.js. Quem usava o ZIP precisa instalar uma vez para receber atualizações automáticas.

## Atualizações automáticas

O aplicativo instalado procura versões ao abrir e periodicamente enquanto está aberto. Procura e download são adiados durante salas. Uma atualização pronta é instalada ao sair, ou pelo botão **Reiniciar e atualizar** nas opções. Se fechar para a bandeja com uma atualização pronta, somente a bandeja é reaberta após instalar. As preferências são preservadas.

As atualizações exigem uma assinatura Ed25519 reconhecida pelo app e conferência de tamanho/SHA-512, inclusive para instalador em cache. Não é necessário token ou conta GitHub para baixar. A assinatura de atualização é independente de Authenticode: esta prévia ainda pode aparecer como editor desconhecido no Windows.

O ZIP **TelaLeve-0.13.0-Windows.zip** é uma alternativa portátil e não recebe atualização automática. Não use os ZIPs “Source code” gerados automaticamente pelo GitHub para instalar: eles contêm apenas esta documentação.

## Celular e navegador

Dentro da sala, clique em **Entrar pelo celular** e envie o link privado ou QR Code. A página é **https://telaleve-p2p.pages.dev/**. Ela não lista salas: o convite é necessário. O vídeo continua P2P; algumas redes restritivas podem precisar de TURN, não incluído no app.

A sala permite anfitrião e dez convidados. Cada pessoa pode assistir até duas imagens. A captura começa desligada. Na 0.11, você pode iniciar na bandeja com o Windows e compartilhar áudio do computador opcionalmente. Mac nativo, celulares físicos e várias operadoras ainda precisam de validação completa.

## Histórico e integridade

As versões anteriores permanecem em Releases, com suas notas e arquivos originais. As tags identificam distribuições, não reconstroem commits históricos do código-fonte. Prefira a versão mais recente: os protocolos e recursos variam entre versões.

Cada release inclui **SHA256SUMS.txt**. A partir da 0.10, EXE, blockmap, latest.yml e TelaLeve-update.json são produzidos juntos para atualização do app instalado. Os testes e limites de cada entrega estão registrados em suas notas e relatórios.

## Inicialização e áudio (0.12)

Na engrenagem do app instalado, ative **Iniciar com o Windows em segundo plano**. A opção vem desligada. Inicia somente a bandeja leve, sem motor de vídeo, sala ou captura. Desativar/desinstalar remove a entrada; atualizar preserva a escolha.

Na engrenagem do seletor de transmissão, marque **Compartilhar áudio**:

- **Aplicativos:** áudio do aplicativo da janela escolhida e seus subprocessos. Outras janelas/abas do mesmo programa podem compartilhar esse áudio.
- **Tela inteira:** mistura os aplicativos permitidos e exclui o **Discord instalado** (incluindo Stable/PTB/Canary e novas instâncias) e o próprio TelaLeve. Seu som local continua normal.

O filtro é nativo do app Windows. Discord em uma aba não pode ser separado do restante do áudio do mesmo navegador. Use o Discord instalado para essa proteção. Navegadores/Mac recebem as transmissões normalmente, mas, ao transmitir, dependem do seletor do sistema e não aplicam esse filtro Windows.

Não captura microfone, grava áudio, instala drivers ou altera dispositivos. Se o isolamento falhar, o som é interrompido sem retornar à captura geral. A API exige Windows compatível com loopback por processo; Windows 11 é a referência. Sons do sistema sem PID e aplicativos protegidos podem não ser incluídos na mixagem. Limite de 24 processos de áudio.

Quem assiste clica **Ouvir** e ajusta o volume por transmissão. O transmissor pode silenciar só o som ou pausar áudio e vídeo juntos. Atualize o TelaLeve em cada PC que for transmitir para usar o novo isolamento. Webcam continua sem microfone.

## Mac e verificação automática (0.13)

Agora há DMG para **Apple Silicon** (M1 ou posterior, arm64) e **Intel** (x64), além dos ZIPs correspondentes, nos arquivos desta versão. Arraste TelaLeve para Aplicativos. Veja **MACOS.md** na release para permissões e abertura de um aplicativo com assinatura local ad hoc, sem Developer ID ou notarização Apple.

O Mac transmite tela e webcam juntas, sem áudio de saída; recebe áudio normalmente dos outros participantes. O filtro de áudio do Discord permanece exclusivo do Windows. O consumo ocioso no Mac é maior, pois utiliza Electron na barra de menus.

O app verifica versões automaticamente ao iniciar e a cada quatro horas, adiando em salas. No Mac avisa e oferece o instalador da arquitetura correta; a substituição em Aplicativos é manual. Atualização instalada automaticamente no Mac depende de assinatura Apple, ainda não configurada.

No Windows instalado, a bandeja leve também procura versões quando o motor está fechado. Ela só avisa, sem carregar Chromium. Abrir o app mantém a atualização autenticada por Ed25519 e SHA-512 e instalação ao sair.
