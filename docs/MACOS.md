# TelaLeve no Mac

Baixe o DMG `arm64` para Apple Silicon (M1 ou posterior) ou `x64` para Intel. Abra-o e arraste TelaLeve para Aplicativos. O pacote recebe assinatura local ad hoc, sem certificado Developer ID e sem notarização Apple; o macOS pode pedir autorização em Ajustes do Sistema → Privacidade e Segurança → Abrir Mesmo. Autorize somente se reconhecer a origem do arquivo.

Permita Gravação de Tela e Câmera quando solicitado e reabra o aplicativo se o sistema pedir. Tela e webcam podem ser transmitidas juntas. Microfone não é capturado.

## Áudio isolado — versão 0.14

Requer **macOS 14.2 ou posterior**. Marque Compartilhar áudio na engrenagem do seletor de transmissão e autorize a captura de áudio do sistema quando solicitado. A permissão pode aparecer como Gravação de Tela e Áudio do Sistema ou Gravação de Áudio do Sistema, dependendo da versão do macOS.

- Aplicativos: captura o áudio do processo da janela escolhida e seus subprocessos, podendo incluir outras janelas/abas do mesmo aplicativo.
- Tela inteira: captura uma lista explícita dos processos permitidos, excluindo Discord instalado, seus auxiliares e o próprio TelaLeve. Novos processos são reavaliados antes de entrarem na captura. Discord em uma aba não é separado das outras abas do navegador.
- O áudio que você ouve continua normal. Não há driver, microfone ou gravação em arquivo. A saída de áudio vai para a transmissão P2P.
- Ao fechar a sala, parar a tela ou encerrar o aplicativo, o capturador é encerrado e o dispositivo agregado privado é destruído. Erro não ativa captura geral; compartilhe sem áudio ou ajuste a permissão e tente novamente.
- Aplicativos protegidos ou auxiliares que não possam ser associados com segurança ao processo da janela podem ficar sem som. O dispositivo agregado é privado e temporário; não é configurado como saída padrão do computador.

Macs antigos continuam podendo compartilhar imagem e webcam, com o áudio isolado indisponível. Até a validação em um Mac físico, o recurso deve ser tratado como experimental, especialmente quanto a permissões, troca de saída de som e reprodução pelo Discord.

## Atualizações e segundo plano

A verificação de atualizações ocorre ao iniciar e a cada quatro horas, fora de uma sala. Quando houver uma nova versão para sua arquitetura, aparece Baixar instalador do Mac. Substitua o aplicativo em Aplicativos. Instalação automática no Mac depende de assinatura Developer ID, não configurada.

Fechar a janela mantém o app na barra de menus. Use Sair para encerrá-lo. No Mac, a bandeja utiliza Electron e consome mais memória que o pequeno host nativo do Windows. Inicialização junto com o sistema pode ser configurada em Ajustes do Sistema → Itens de Início.

## Compilar e testar

Use Node 24 e pnpm 10: `pnpm install --frozen-lockfile`, `pnpm test`, `pnpm build`, `pnpm installer:mac`. O build compila `native/audio-host-mac.m` com frameworks da Apple para arm64 e x86_64, sem dependências de terceiros. O capturador só inicia depois da autorização do seletor; o build e o autoteste não capturam áudio real.

`app/TelaLeveAudioMac --self-test` testa o mesmo filtro de processos utilizado na captura e a conversão 44,1/48 kHz para PCM estéreo 48 kHz/16 bits. O workflow manual gera DMGs e ZIPs e confere a assinatura ad hoc do aplicativo e do helper. Somente DMGs e os arquivos essenciais da atualização são publicados, conforme RELEASES.md.
