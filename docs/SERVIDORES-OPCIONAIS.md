# TURN e SFU próprios — opcionais

O TelaLeve usa P2P por padrão. Não há TURN compartilhado nem SFU externo ativado. Estes recursos usam software livre em equipamento/servidor que você já possui; hardware, tráfego, energia, domínio ou uma eventual hospedagem escolhida por você podem ter custo. Nenhum desses serviços foi contratado.

## TURN próprio

Use as opções avançadas de conexão para informar servidores STUN/TURN. Prefira Coturn atualizado, autenticação com segredo do servidor e credenciais com prazo curto. O segredo administrativo nunca entra no app, no convite ou no gerador distribuído com segredo preenchido.

`server/coturn.example.conf` é um modelo com cotas: quatro alocações por credencial, 48 totais, teto por sessão e teto global. Ajuste esses valores à capacidade do seu equipamento e ao número de fontes. Também bloqueia destinos privados e multicast. Substitua domínio, segredo e caminhos de certificados antes de iniciar. Esse arquivo não abre portas nem configura o roteador automaticamente.

No computador administrativo, defina a variável de ambiente `TELALEVE_TURN_SECRET` com o mesmo segredo aleatório do Coturn e execute `node scripts/turn-credentials.mjs turn.seu-dominio.example 600`. A saída contém usuário/credencial válidos por dez minutos; cole o JSON nas opções do TelaLeve. O gerador aceita de um minuto a uma hora. Use uma identidade/credencial distinta por cliente quando administrar um serviço compartilhado; o exemplo CLI gera uma identidade aleatória.

Esse gerador é uma ferramenta administrativa, não um emissor público de credenciais. Um serviço público exigiria autenticação, cotas por conta e renovação segura. O app atual não renova essas credenciais TURN automaticamente: a expiração pode impedir novas conexões e atualizações de alocação; para uma sala longa, providencie credenciais renováveis no servidor e atualize as opções antes da próxima sala. Nenhum segredo TURN permanente vem incluído.

## SFU LiveKit próprio (experimental)

SFU reduz o upload repetido para espectadores, mas transfere o tráfego para o seu servidor. O padrão continua P2P. O SFU não substitui a sinalização autenticada da sala.

1. Instale o servidor LiveKit livre no seu equipamento. Para teste no próprio PC, use `livekit-server --dev --bind 127.0.0.1 --node-ip 127.0.0.1`. As credenciais de desenvolvimento `devkey`/`secret` servem apenas no teste local, nunca para internet.
2. Para uso externo, siga as instruções oficiais de HTTPS/WSS, TLS e portas de mídia do LiveKit. Não exponha o modo de desenvolvimento. O app não configura firewall ou roteador.
3. Em **Opções de conexão → Configuração avançada**, marque **Usar SFU próprio** e informe o endereço `wss://`, chave e segredo administrativo do servidor. O segredo fica protegido pelo sistema operacional neste computador; não entra no convite e não é enviado aos convidados. Para manter o segredo já salvo, deixe o campo vazio ao salvar.
4. Crie outra sala. O anfitrião autoriza cada convidado aprovado com um token de entrada de 60 segundos, limitado à sala. A sessão conectada pode continuar além da validade inicial; a recuperação pode solicitar outra autorização ao anfitrião. O emissor limita participantes únicos a onze e renovações a uma a cada dez segundos por identidade.
5. A sala SFU é criada com máximo de onze participantes. Cada transmissor libera somente as faixas selecionadas aos espectadores autorizados. Expulsar remove o participante no servidor e retira as permissões das fontes; sair da sala encerra a sala SFU. Um token já emitido pode continuar válido até completar seus 60 segundos, mas não devolve as permissões de assistir às fontes revogadas.
6. Desmarque a opção antes de criar a próxima sala para voltar a P2P.

Apenas o anfitrião precisa configurar o servidor; convidados recebem autorização temporária após entrar na sala. O SFU é identificado na saúde da transmissão, e não confundido com conexão direta. Em SFU, um pedido de economia reduz a camada única daquela fonte para todos os seus espectadores; isso evita codificar várias versões ao mesmo tempo.

Referências oficiais: [LiveKit local](https://docs.livekit.io/transport/self-hosting/local/), [implantação](https://docs.livekit.io/transport/self-hosting/deployment/), [permissões e tokens](https://docs.livekit.io/frontends/reference/tokens-grants/), [configuração Coturn](https://github.com/coturn/coturn/blob/master/examples/etc/turnserver.conf).
