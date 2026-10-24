# Validação 0.19.2

119 testes automatizados passaram. Incluem histórico de temporárias encerradas/expiradas, paginação sem perda ou repetição, associação de sessões às permanentes corretas, cadastro imediato e encerramento durante uma tentativa de cadastro pendente. O histórico não guarda os convites completos nem credenciais dos participantes.

A integração Windows com duas instâncias verificou entrada administrativa autorizada em sala com senha, bloqueio e aprovação, recusa de credencial inválida e mudança para nome pessoal sem perder a autorização. O nome e a presença permanecem na lista; a tag fixa não é exibida. A reconexão também passou.

Instalador Windows e metadados de atualização conferidos com a chave de confiança anterior. Somente Windows e webapp nesta entrega; nenhum novo instalador Mac foi publicado.

Limites: o catálogo abrange salas cadastradas neste serviço. Registros antigos já apagados ou nunca anunciados não podem ser recuperados. Temporárias encerradas não têm anfitrião P2P para entrar; permanentes vazias podem ser reabertas. Anfitriões e clientes precisam atualizar para refletir a nova identificação. Lotação e condições de rede continuam aplicáveis.

A verificação publicada com GitHub real confirmou o cadastro imediato, entrada autorizada com nome pessoal e manutenção da sala temporária de teste no histórico após encerramento. As salas dos amigos não foram acessadas nesse teste.
