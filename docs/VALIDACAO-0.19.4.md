# Validação 0.19.4

Corrige a qualidade que ficava presa em baixa resolução e os vídeos que não terminavam de abrir.

- Latência estável acima de 250 ms não reduz mais a qualidade continuamente. A adaptação distingue atraso constante de crescimento de latência, perda de pacotes e sobrecarga persistente.
- Jogos podem reduzir resolução para preservar FPS quando faltar banda; texto mantém seu perfil de detalhes.
- Vídeo que não conecta ou não decodifica o primeiro quadro tenta novamente automaticamente, mantendo a fonte selecionada.
- Ajustes idênticos de qualidade não são reaplicados ao codificador; consultas simultâneas de estatísticas são agrupadas.

121 testes automatizados aprovados. Teste integrado com cinco espectadores reais sobre conexão local, vídeo animado e 272 ms simulados nas estatísticas: 1280×720 a cerca de 28–30 FPS. Recuperação de conexão sem recaptura verificada. A simulação não reproduz perda, jitter ou redes de provedores diferentes. Somente instalador Windows nesta versão; nenhum novo instalador Mac.

Atualize o aplicativo de todos os transmissores e espectadores para 0.19.4 e reinicie. No navegador, recarregue a página fora da sala para obter a correção.
