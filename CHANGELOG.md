# Histórico das distribuições

Os pacotes abaixo foram preparados em 17/10/2026 e arquivados no GitHub posteriormente. Os arquivos de versões anteriores são preservados; as tags deste repositório identificam distribuições, sem reconstruir um histórico de commits do aplicativo.

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
