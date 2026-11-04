# Validação 0.21.0 — Liga/desliga e câmera do celular

O botão Compartilhar tela vira Parar tela durante o envio. O mesmo atalho global agora liga e desliga a tela inteira com som, preservando webcam e sala.

Quando nenhuma webcam é encontrada, o QR abre automaticamente. Na aba Webcam, Usar câmera do celular também gera QR temporário (5 minutos) e link HTTPS com segredo apenas no fragmento. O celular autoriza a câmera e toca em Conectar câmera. A conexão separada usa desafio HMAC com nonce, aceita um celular autenticado, um vídeo e nenhum áudio; não transmite convite ou senha da sala. As tentativas de controle e o número de conexões pendentes são limitados. O vídeo chega por P2P ao PC, que o publica como a própria webcam, sem ocupar vaga de participante. Parar em qualquer ponta encerra a captura; encerrar a sala ou cancelar o QR também limpa a conexão.

A página permite câmera frontal/traseira antes de conectar; requer HTTPS, permissão de câmera, página aberta e tela ligada. Conexão de vídeo P2P pode falhar em redes que necessitam TURN; nenhum servidor pago foi configurado. O uso do celular como webcam exige que o PC receba e encaminhe o vídeo, com custo de decodificação/codificação.

Verificação: 149 testes automatizados aprovados. Integração Windows/Chromium com mídia sintética: liga/desliga/religa com som pelo atalho e botão; QR gerado sem webcam local; autenticação e sinalização PeerJS pública; câmera do navegador → PC → espectador P2P; tela e câmera simultâneas do mesmo participante; sem microfone nem vaga adicional; desligamento PC/celular e novo pareamento.

Limites: não houve teste em celular físico, Safari/iPhone, câmera física, teclado físico ou redes de provedores diferentes. A página do celular foi publicada na Cloudflare; index.html e phone.html retornam HTTP 200 e têm conteúdo idêntico ao build. Instalador Mac não gerado.
