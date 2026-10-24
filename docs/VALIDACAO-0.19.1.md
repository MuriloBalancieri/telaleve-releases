# Validação 0.19.1

113 testes automatizados passaram. Cobrem salvamento e saneamento do nome, persistência sem alterar o preset da tela, falha de armazenamento, anfitrião antigo, identificação administrativa fixa, confirmação autenticada da alteração e atualização somente do próprio participante.

A integração Windows/Chromium usou um aplicativo e um navegador com vídeo sintético: nomes do anfitrião e do convidado foram alterados nas configurações durante a live. O player, MediaStream e captura permaneceram os mesmos e os quadros continuaram avançando. A reconexão e o recarregamento do navegador preservaram o nome.

O instalador Windows foi inspecionado por extração de conteúdo e verificação da assinatura do atualizador, com a mesma chave das versões antigas.

A compilação Mac anterior passou na geração mas falhou ao enviar artefatos porque a cota de armazenamento do Actions foi atingida. A mudança de permissão proposta para outro meio de transferência não foi aplicada. O proprietário pediu não gerar um novo instalador Mac; portanto essa plataforma não é distribuída na versão 0.19.1. Versões antigas permanecem no histórico. Mac físico e iPhone/Safari não foram testados nesta etapa.
