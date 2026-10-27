# Validação 0.19.7

Recuperação de vídeo que para durante uma transmissão já aberta.

- Verifica o progresso de captura, codificação e recepção durante toda a conexão, além da chegada do primeiro quadro.
- Refaz somente a conexão afetada quando há atividade sem novos quadros, ou quando uma conexão estabelecida deixa de responder.
- Quando a captura avança mas o codificador trava, tenta um codec alternativo apenas para aquele espectador, com limites conservadores de resolução, FPS e bitrate.
- Duas fontes podem se recuperar simultaneamente; pedidos repetidos continuam limitados por fonte.
- Uma tela estática, uma transmissão pausada e o modo somente áudio não são tratados como falha.
- Diagnóstico exportável inclui contadores de recuperação, sem convites, senhas, nomes ou credenciais.

141 testes automatizados aprovados. Integração Windows/Chromium com cinco espectadores, vídeo sintético e falhas simuladas nas estatísticas: recuperação de recepção e envio preservou a captura; o codec alternativo negociou VP8 e uma tela estática não provocou reconexões. O teste não reproduz as redes reais dos participantes nem confirma todas as causas possíveis de uma imagem preta.

Atualize quem transmite e quem assiste para 0.19.7 e reinicie. Convidados no navegador devem recarregar o webapp fora da sala. Caso persista, exporte o diagnóstico do transmissor e de um espectador afetado enquanto a imagem estiver preta. Nenhum novo instalador Mac foi gerado.
