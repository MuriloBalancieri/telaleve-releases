# Validação 0.22.0 — Clipes da tela

Buffer opcional do monitor principal, independente da sala, desligado em cada inicialização. Captura até 720p/30 FPS, VP8 a 3 Mbps e Opus estéreo a 128 kbps quando o áudio nativo está disponível. Não usa microfone. Mantém somente pacotes codificados dos últimos 30, 45 ou 60 segundos e limita esse buffer a 64 MB. A gravação exige captura e codificação contínuas enquanto habilitada; não promete impacto zero nos jogos nem codificador em hardware.

O atalho global usa as mesmas combinações aceitas pelo compartilhamento e recusa colisões com ele. O botão Salvar clipe agora também funciona. Salva WebM em pasta local ou pasta sincronizada escolhida em diálogo nativo. O cliente de OneDrive/Google Drive/Dropbox faz a sincronização; não há upload direto nem credenciais de nuvem no TelaLeve. Arquivos recebem nomes exclusivos, gravação temporária e finalização atômica. O início respeita o quadro completo mais próximo, podendo variar cerca de um segundo. Durante o aquecimento salva apenas o tempo disponível.

Verificação: 152 testes automatizados aprovados. Integração Windows/Chromium com tela e áudio sintéticos: ativação fora da sala, callback do atalho registrado no sistema com janela oculta, gravação de 30/45/60 segundos, vídeo decodificável e áudio Opus não silencioso, salvamento em pasta local e pasta simulando diretório sincronizado, encerramento das faixas ao desligar. Preferências, limites de memória, validação dos destinos e escrita completa foram testados.

Limites: mídia sintética não comprova desempenho em jogos, captura de monitor físico, teclado físico ou upload de um cliente real de nuvem. Nenhum novo instalador Mac. A gravação pode ser interrompida na suspensão do computador e precisa ser reativada. Permissões e disponibilidade de áudio dependem do sistema operacional.

