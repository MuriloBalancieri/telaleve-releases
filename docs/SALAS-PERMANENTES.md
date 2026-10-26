# Salas permanentes — 0.18.0

No app, clique em **Criar sala permanente**, escolha o nome e seu apelido. Copie o link da sala e envie aos amigos. Após entrar uma vez, a sala aparece em **Suas salas** no app ou navegador de cada pessoa. Para voltar, clique em **Entrar**, sem pedir outro convite.

**Sair** encerra somente sua participação na chamada atual. A sala fica salva mesmo se todos saírem. O primeiro membro que voltar abre uma nova sessão; o criador não precisa estar conectado. Tela, áudio e webcam continuam desligados até você escolher transmiti-los. **Encerrar para todos** encerra a sessão atual, mas não apaga a sala salva. **Esquecer** remove o acesso apenas deste aparelho; um novo convite é necessário para cadastrá-lo novamente.

## Gratuidade e limites

A mídia continua P2P. Um pequeno cadastro Cloudflare D1 no plano gratuito mantém nomes, membros e o endereço da sessão ativa, permitindo reencontrar a turma quando ninguém estava online. Nenhum plano pago, TURN ou servidor de vídeo foi contratado. Salas salvas e fechadas não mantêm conexão, captura nem consultas periódicas no seu PC. A lista carrega uma vez ao abrir e a presença só é atualizada durante uma sessão.

Limites do app: 20 salas por aparelho, 64 acessos de aparelhos cadastrados por sala e 11 pessoas simultâneas (você e dez amigos). Criar salas tem limite de quatro por rede por dia; convites e controle têm limites contra abuso. O cadastro tem limite preventivo de mil salas, cem criações diárias e os tetos gratuitos do provedor. Atingir uma cota pode impedir temporariamente novas entradas; não ativa cobrança automaticamente. Não há garantia de disponibilidade eterna de um serviço gratuito.

Use o mesmo perfil do app ou navegador. Não há login nem sincronização automática entre aparelhos. Limpar os dados do site, trocar de computador ou perder a proteção local exige aceitar o convite novamente. O convite dá acesso a quem o possui: compartilhe somente com sua turma.

## Privacidade

O link usa um fragmento (#room=), sem token individual. Cada aparelho recebe um token aleatório exclusivo. No servidor, token e segredo de convite são guardados como SHA-256; nomes e identificadores ficam no cadastro. O endereço P2P e a autorização da sessão ativa ficam no registro enquanto ela está aberta. Membros admitidos são confiáveis para assumir a sessão. As chaves do servidor SFU e senhas de salas temporárias não entram nesse cadastro.

No app, as salas usam safeStorage do sistema, sem alternativa em texto simples. No navegador, usam IndexedDB com conteúdo AES-GCM e chave não exportável. Isso protege o conteúdo armazenado contra leitura casual; não protege um perfil já comprometido ou código malicioso executado na origem. Diagnósticos não incluem tokens, convites ou respostas do cadastro. A perda do acesso ao cadastro não interrompe por si só a mídia P2P existente; novas entradas e reaberturas dependem de o serviço voltar.

## Manutenção do cadastro

O banco foi criado no Cloudflare D1 gratuito como `telaleve-rooms`, vinculado ao Pages `telaleve-p2p` pela variável `ROOM_DB`. O esquema está em `server/rooms-schema.sql`. Aplique-o no console D1 antes do primeiro deploy, sem apagar tabelas existentes.

O build gera `dist/site/_worker.js` e `_routes.json`, além de index.html, _headers e robots.txt. Publique os cinco arquivos na raiz do Pages. `_routes.json` encaminha somente `/api/rooms/*` ao worker; o restante mantém os arquivos estáticos. O endpoint público `/api/rooms/health` confirma o vínculo; as demais operações exigem POST e autorização de membro ou convite. Não publique dumps do banco ou credenciais.

Teste implementado com Windows/Chromium e mídias sintéticas. Mac físico, iPhone/Safari e redes diferentes ainda precisam de validação real.
