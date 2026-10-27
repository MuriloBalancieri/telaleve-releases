# Validação 0.19.9 — Prévias locais e webcam HD

- Botões Ver minha tela e Ver minha webcam nos controles da própria transmissão, no Windows e no espectador web.
- Duas prévias independentes, inicialmente desligadas, sem áudio local e sem novas capturas ou conexões P2P. Fechar a prévia libera o player, sem parar a transmissão. Ao ocultar a janela, a prévia é suspensa; Picture-in-Picture permanece ativo quando utilizado.
- Webcam prefere 1280 × 720 a 30 FPS e até 1,8 Mbps por espectador, sujeita à câmera, adaptação e orçamento total de upload. Mantém prioridade para tela, modo Priorizar o jogo e tentativa de formato compatível no mesmo dispositivo.
- Sem upscaling artificial: ampliações no player preservam o vídeo original; não são prometidos detalhes inexistentes.

Verificação: 142 testes automatizados aprovados e integração Windows/Chromium com duas fontes e dois espectadores. A câmera virtual negociou 720p. Testadas abertura/fechamento de ambas as prévias no app e navegador, mesmos objetos de captura, nenhuma conexão adicional, prévia muda, suspensão por visibilidade, pausa/retomada, desligamento de uma fonte preservando a outra e encerramento.

Limites: mídia virtual/sintética; não houve teste com webcam física, Mac, Safari/iPhone ou redes de provedores diferentes. A mensagem de recuperação automática relatada anteriormente continua sem reprodução e não é declarada corrigida nesta versão. Nenhum novo instalador Mac.
