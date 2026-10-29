# Validação 0.20.1 — Atalho Ctrl + [

Aceita Ctrl + [ e Ctrl + ], com Shift opcional, na gravação, validação e persistência do atalho global. Usa o símbolo digitado para colchetes em posições físicas diferentes (por exemplo, layout brasileiro); mantém os atalhos anteriores e a rejeição de modificadores não suportados.

Verificação: os 5 testes específicos do atalho passaram, incluindo gravação e validação de colchetes com códigos físicos diferentes. Integração Windows/Chromium com registro real de Control+[ e callback nativo, mídia sintética e transmissão com áudio sem seletor. Não houve teste com tecla física em teclado ABNT2.

Correção exclusiva do app instalado; site permanece na versão funcional publicada 0.20.0. Nenhum novo instalador Mac.
