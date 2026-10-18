## 0.15.4 — Cores do seu aplicativo

- Seis paletas, incluindo tema claro, e cores de destaque e fundo personalizadas.
- Prévia imediata, salvar, cancelar e restaurar a paleta original.
- Preferência local por usuário, sem alterar os amigos, a sala ou os vídeos.
- Contraste automático dos textos e controles.
- 50 testes unitários e teste da interface Windows; Mac físico pendente.

## 0.15.3 — Abrir no TelaLeve

- Botão na página do convite abre o aplicativo instalado no Windows e Mac.
- Convite recebido com app fechado ou na bandeja; senha e aprovação respeitadas.
- Confirmação antes de sair de outra sala; repetir convite mantém a sessão.
- Alternativa para continuar no navegador e baixar o app.
- 47 testes unitários e teste integrado com iniciador real do Windows; Mac físico pendente.

# Histórico das distribuições

Os pacotes abaixo foram preparados em 17/10/2026 e arquivados no GitHub posteriormente. Os arquivos de versões anteriores são preservados; as tags deste repositório identificam distribuições, sem reconstruir um histórico de commits do aplicativo.

## [0.15.2 — Links diretos para a sala](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.15.2)

Copiar link da sala passa a gerar convite HTTPS compacto, sem encurtador ou banco adicional. Sala sem senha inicia a entrada ao abrir o link; senha e aprovação permanecem exigidas. Código anterior disponível numa seção separada. Correção da geração da página para preservar o código minificado e sua integridade. 45 testes unitários e testes de links com/sem senha e aprovação.

## [0.15.1 — Recuperação da qualidade](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.15.1)

Corrige a realimentação entre estimativa de banda e redução inicial que podia manter a imagem em meia resolução. A qualidade sobe novamente em uma conexão saudável; limites de upload, economia do espectador e Priorizar o jogo permanecem. 41 testes unitários e teste entre aplicativos confirmando retorno a 1080p sem recapturar.

## [0.15.0 — Estabilidade, desempenho e controle](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.15.0)

Recuperação de vídeo e sessão sem recapturar, modo Priorizar o jogo, margem de upload, perfil leve de webcam, qualidade gradual e saúde de cada fonte. Apelidos, espectadores, escuta minimizada, diagnóstico sem credenciais, aprovação, bloqueio, expulsão e renovação de convites. P2P padrão e SFU/TURN próprios opcionais, sem contratação de servidores. Convite de oito horas deixa de limitar a duração da sala. 39 testes unitários; integração sintética com dez espectadores e SFU local. Homologação física em jogos, iPhone/Safari e Mac permanece pendente.

## [0.14.0 — Áudio isolado no Mac](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.14.0)

Captura nativa experimental por aplicativo no macOS 14.2+, com exclusão do Discord instalado na tela inteira. Filtro por lista explícita, conversor estéreo 48 kHz e encerramento em falhas. 29 testes unitários e autoteste nativo de política/conversão; captura real, permissões e desempenho em Mac físico ainda não validados.

## [0.13.0 — Mac e verificação automática](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.13.0)

DMG/ZIP para Mac Intel e Apple Silicon, verificação automática com download manual no Mac e notificações de versão na bandeja Windows sem abrir Chromium. Fonte preservado em repositório privado. 28 testes passaram em Windows/macOS; instaladores Mac gerados em runner macOS, ainda sem teste físico do usuário ou Developer ID.

## [0.12.0 — Áudio de aplicativo e tela sem Discord](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.12.0)

Áudio da janela usa captura nativa por árvore de processos do aplicativo escolhido. Tela inteira mistura sessões permitidas e exclui Discord instalado (incluindo novas instâncias) e o próprio TelaLeve. Sem driver, gravação ou mudança do som local. Descoberta separada da mixagem, temporização de áudio do Windows, buffers limitados e encerramento ao sair.

Falhas não ativam áudio geral. Outras janelas/abas do mesmo programa não são separadas. Discord em navegador não é filtrado de forma independente. Recurso disponível no app Windows com suporte à API de loopback por processo; navegador/Mac continuam com seu seletor nativo.

25 testes unitários, tons sintéticos isolados, reinício de instâncias Discord simuladas, envio nativo de áudio/vídeo por P2P, controles e regressão de tela+webcam em dois apps. Discord real em chamada, Windows 10 físico e Mac não foram validados nesta etapa.

## [0.11.0 — Iniciar com Windows e tela com áudio](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.11.0)

Opção para iniciar somente a bandeja nativa com o Windows, desligada por padrão. Atualização preserva a escolha e desinstalação remove a entrada. Nenhuma sala ou captura é iniciada automaticamente.

Tela com áudio opcional da saída padrão do Windows, silenciamento independente, volume por transmissão recebida e pausa conjunta de som/imagem. Webcam permanece sem microfone. Áudio do Discord também entra se usar a mesma saída; captura exclusiva por aplicativo ainda não está implementada. Navegadores dependem da disponibilidade de captura da fonte.

## [0.10.0 — Instalador e atualização automática](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.10.0)

Instalador Windows por usuário com atalhos e desinstalador. O app instalado procura e baixa atualizações pelo GitHub Releases fora de salas, valida assinatura Ed25519 e SHA-512, e instala ao sair ou reiniciar. Fechar para a bandeja com atualização pronta preserva o funcionamento em segundo plano, sem ligar captura. Preferências são mantidas.

A migração de ZIP antigo para instalador é manual na primeira vez. O portátil não atualiza automaticamente. A assinatura própria das atualizações não substitui um certificado Authenticode do Windows; esta prévia pode mostrar editor desconhecido.

## [0.9.0 — Acesso gratuito pelo celular com link e QR Code](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.9.0)

Página pública HTTPS no Cloudflare Pages, link privado e QR Code gerado no app. O link completo também é aceito no campo de convite do aplicativo.

Não precisa abrir portas ou configurar certificado no PC para essa opção. Vídeo continua P2P; não inclui serviço TURN. Algumas redes restritivas podem exigir TURN.

## [0.8.0 — Hospedagem local para navegador](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.8.0)

O dono da sala pode hospedar a página HTTPS no PC, escolher porta/certificado e compartilhar link. A prévia HTTP fica restrita a localhost.

A hospedagem local avançada exige certificado confiável e configuração de rede. A opção simplificada sem encaminhamento de portas chega na 0.9.

## [0.7.0 — Um app para criar, entrar, assistir e transmitir](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.7.0)

O mesmo aplicativo Windows cria salas e entra por convite/senha. Convidados assistem e transmitem tela e webcam no app.

O HTML permanece como alternativa. A distribuição nativa é Windows x64; Mac nativo ainda não está disponível.

## [0.6.0 — Tela e webcam ao mesmo tempo](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.6.0)

Cada pessoa transmite tela e webcam simultaneamente, com pausa e parada independentes. Duas fontes da mesma pessoa podem ser assistidas juntas.

O protocolo mudou: atualize aplicativo e participante para a mesma versão. O orçamento de upload é compartilhado entre as fontes.

## [0.5.0 — Seletor de fontes, modos e webcam](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.5.0)

Abas Aplicativos, Tela inteira e Webcam; perfis Jogos, texto e Personalizada; atalhos SD/HD. Webcam ativada somente após confirmação.

Nesta versão cada pessoa transmite tela OU webcam. Tela e webcam simultâneas chegam na 0.6.

## [0.4.0 — Várias pessoas transmitindo na sala](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.4.0)

Convidados também podem transmitir. Cada participante escolhe até duas imagens para assistir simultaneamente.

Nesta versão cada pessoa compartilha uma fonte de tela por vez. Use app e participante da mesma versão.

## [0.3.0 — Criar sala antes de compartilhar](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.3.0)

Fluxo inicial para criar sala e depois escolher a tela. Parar a captura mantém a sala e o convite; sair encerra a sala.

Use o espectador da mesma versão para aguardar na sala antes da transmissão.

## [0.2.0 — Transmissão P2P para dez espectadores](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.2.0)

Migração para vídeo P2P, sinalização pública PeerJS, convite e senha opcional. Espectador independente em HTML.

Até dez espectadores. Não inclui webcam; não há áudio. P2P pode exigir TURN em redes restritivas.

## [0.1.0 — Primeira prévia para Windows](https://github.com/MuriloBalancieri/telaleve-releases/releases/tag/v0.1.0)

Compartilhamento de tela com bandeja nativa, pausa/retomada e diagnóstico local. Arquitetura inicial com LiveKit, antes da migração para P2P.

Versão histórica: o uso pela internet exigia servidor LiveKit e servidor de salas. Limite original de cinco espectadores.
