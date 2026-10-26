# Validação 0.19.5

Melhora a abertura de webcams que apresentavam erro de dispositivo em uso sem outro aplicativo usando a câmera.

- Formato de captura negociado com o driver, sem impor limites rígidos de resolução e FPS na abertura.
- Uma única nova tentativa compatível para falha de inicialização ou formato, mantendo o mesmo dispositivo selecionado e sem microfone.
- Erros distinguem permissão negada, dispositivo ausente, formato incompatível e falha do sistema ao iniciar a câmera.
- Perfil de envio leve da webcam permanece separado do compartilhamento de tela.

128 testes automatizados aprovados. Integração Windows com câmera simulada recuperou uma falha NotReadableError, transmitiu a imagem por P2P e liberou o dispositivo ao parar. Tela + webcam simultâneas também foram verificadas. A webcam física do usuário não foi ativada neste teste, portanto a confirmação do driver real permanece pendente.

Atualize para 0.19.5 e reinicie o TelaLeve antes de testar. Para convidados no navegador, recarregue o webapp fora da sala. Nenhum novo instalador Mac foi gerado.
