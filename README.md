# TelaLeve — Downloads e versões

Compartilhamento de tela e webcam por P2P. Este repositório público guarda instaladores, pacotes e o histórico das distribuições, sem os ZIPs de código-fonte.

**[Baixar o instalador mais recente](https://github.com/MuriloBalancieri/telaleve-releases/releases/latest)** · **[Histórico completo](https://github.com/MuriloBalancieri/telaleve-releases/releases)** · **[Mudanças por versão](CHANGELOG.md)**

## Instalar

1. Na release mais recente, baixe **TelaLeve-Setup-0.11.0.exe**.
2. Encerre a versão anterior pelo ícone da bandeja e execute o instalador.
3. Abra o TelaLeve pelo atalho e crie uma sala ou entre com um convite.
4. Compartilhe tela e/ou webcam somente quando quiser.

A instalação é por usuário, com atalhos e desinstalador. Não precisa instalar Node.js. Quem usava o ZIP precisa instalar uma vez para receber atualizações automáticas.

## Atualizações automáticas

O aplicativo instalado procura versões ao abrir e periodicamente enquanto está aberto. Procura e download são adiados durante salas. Uma atualização pronta é instalada ao sair, ou pelo botão **Reiniciar e atualizar** nas opções. Se fechar para a bandeja com uma atualização pronta, somente a bandeja é reaberta após instalar. As preferências são preservadas.

As atualizações exigem uma assinatura Ed25519 reconhecida pelo app e conferência de tamanho/SHA-512, inclusive para instalador em cache. Não é necessário token ou conta GitHub para baixar. A assinatura de atualização é independente de Authenticode: esta prévia ainda pode aparecer como editor desconhecido no Windows.

O ZIP **TelaLeve-0.11.0-Windows.zip** é uma alternativa portátil e não recebe atualização automática. Não use os ZIPs “Source code” gerados automaticamente pelo GitHub para instalar: eles contêm apenas esta documentação.

## Celular e navegador

Dentro da sala, clique em **Entrar pelo celular** e envie o link privado ou QR Code. A página é **https://telaleve-p2p.pages.dev/**. Ela não lista salas: o convite é necessário. O vídeo continua P2P; algumas redes restritivas podem precisar de TURN, não incluído no app.

A sala permite anfitrião e dez convidados. Cada pessoa pode assistir até duas imagens. A captura começa desligada. Na 0.11, você pode iniciar na bandeja com o Windows e compartilhar áudio do computador opcionalmente. Mac nativo, celulares físicos e várias operadoras ainda precisam de validação completa.

## Histórico e integridade

As versões anteriores permanecem em Releases, com suas notas e arquivos originais. As tags identificam distribuições, não reconstroem commits históricos do código-fonte. Prefira a versão mais recente: os protocolos e recursos variam entre versões.

Cada release inclui **SHA256SUMS.txt**. A partir da 0.10, EXE, blockmap, latest.yml e TelaLeve-update.json são produzidos juntos para atualização do app instalado. Os testes e limites de cada entrega estão registrados em suas notas e relatórios.

## Inicialização e áudio (0.11)

Na engrenagem do app instalado, ative **Iniciar com o Windows em segundo plano**. A opção vem desligada. Inicia somente a bandeja leve, sem motor de vídeo, sala ou captura. Desativar/desinstalar remove a entrada; atualizar preserva a escolha.

Na engrenagem do seletor, marque **Compartilhar áudio do computador** antes de transmitir a tela. É o som da saída padrão do Windows, inclusive Discord se estiver na mesma saída; não é áudio exclusivo de uma janela. Deixe desligado ou use outra saída para o Discord se quiser evitar eco. Webcam não captura microfone.

Quem assiste clica **Ouvir** e ajusta o volume em cada transmissão. O transmissor pode silenciar apenas o áudio; pausar tela pausa som e imagem. No navegador, capturar áudio depende da fonte e do seletor oferecido pelo sistema. Atualize todos os participantes para usar os controles de som.
