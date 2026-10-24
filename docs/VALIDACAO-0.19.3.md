# Validação 0.19.3

A causa foi reproduzida no CSS: o botão de administração era filho de .channels, cujo display era none. O botão passou para o cabeçalho visível e ganhou outra entrada no início das configurações.

A integração Windows verifica dimensões, posição dentro da janela e hit testing antes de enviar eventos de mouse por coordenadas. Os controles foram efetivamente clicados em 800×680, 1080×850 e 1440×1000, e o painel de login abriu em todos os tamanhos. O caminho pelas configurações foi verificado da mesma maneira, com a janela anterior fechando antes da abertura do painel.

119 testes automatizados aprovados. A verificação de autorização existente também passou: entradas inválidas recusadas, entrada autenticada preservada e reconexão. O instalador Windows e os metadados de atualização são verificados pela mesma chave das versões anteriores. Nenhuma permissão adicional de GitHub Actions foi aplicada e nenhum instalador Mac novo foi produzido.

O painel administrativo nativo requer o aplicativo Windows e a conta GitHub autorizada; o webapp de convidados não oferece esse login.
