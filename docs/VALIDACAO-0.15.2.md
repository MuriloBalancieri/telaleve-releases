# Versão 0.15.2 — link direto para a sala

Copiar link da sala gera um endereço HTTPS compacto (aproximadamente 150 caracteres nas opções padrão). O segredo, a identidade da sala, o salt e a validade são preservados integralmente e permanecem no fragmento, que não é enviado na requisição HTTP. Não há encurtador, banco ou servidor adicional. STUN/TURN e sinalização personalizados e SFU são preservados; nesses casos o endereço pode ficar maior.

Ao abrir: sala sem senha inicia autenticação automaticamente; sala com senha mostra o campo e aguarda confirmação. Aprovação, bloqueio, expiração e convite revogado continuam valendo. Entrada não aciona tela, câmera ou microfone. A página remove o fragmento do endereço após lê-lo, como antes. O código anterior continua acessível em Código para versões anteriores; apps antigos devem usar esse código ou atualizar para entender o link compacto. O modo de teste local continua com seu convite restrito ao PC.

45 testes unitários passaram, incluindo formato compacto, preservação das credenciais/configurações, QR, dados truncados e expiração. Testes entre instâncias verificam link com senha e entrada automática sem senha, com aprovação e captura desligada. Não é homologação física de iPhone/Safari ou Mac.

# Correção 0.15.1 — qualidade presa na inicialização

Removida a realimentação entre estimativa de banda, fator de inicialização e sinal bandwidth do navegador. O teto passa a vir do perfil selecionado, orçamento de upload e preferência do espectador; o WebRTC continua controlando congestionamento. Conexão saudável recupera o teto em cinco amostras (aproximadamente 15 segundos), sem esperar aumentar o tráfego de uma imagem estática. Perda, latência alta e sobrecarga de codificação ainda reduzem a qualidade. Telas usam preferência de preservar resolução, exceto Priorizar o jogo.

41 testes unitários passaram. Regressão reproduz estimativa de 500 kbps, perda zero, RTT de 27 ms e indicação bandwidth; confirma restauração de resolução, FPS e teto do perfil, preservando Economia de dados. Teste entre aplicativos com captura sintética 1080p verifica a resolução realmente recebida. Não comprova a qualidade na conexão específica do usuário; é preciso atualizar o transmissor e verificar nessa sala.

# TelaLeve 0.15 — estabilidade, desempenho e controle

P2P continua sendo o padrão. Nenhum serviço pago, conta de hospedagem ou servidor compartilhado foi contratado/configurado nesta atualização.

## O que mudou

- Botão **Ouvir** independente de **Ampliar**, inclusive quando o áudio chega depois do vídeo.
- Recuperação automática de conexões de vídeo e da sessão do convidado. A seleção da fonte e as capturas existentes são preservadas. A tentativa de recuperar a sala dura até aproximadamente 90 segundos após detectar a queda; um reinício completo do app ainda exige entrar novamente.
- Erros distintos para senha/convite, versão incompatível, sinalização, aprovação e mídia.
- O convite vale oito horas para **novas entradas**. Não existe mais encerramento automático da sala ativa por esse prazo. Recuperações autenticadas de quem já entrou continuam permitidas.
- **Priorizar o jogo** no seletor e nos controles da sala: captura conservadora, reserva maior de upload e adaptação. Pode reduzir qualidade para proteger o jogo; não promete eliminar toda queda de FPS.
- Campo **Seu upload** nas opções. O limite efetivo considera o menor valor entre o teto configurado e a margem da conexão informada. Não usa o download como estimativa de upload.
- Início em qualidade menor e aumento gradual. Perda, latência, banda indicada pelo WebRTC e tempo de codificação podem reduzir a qualidade. O navegador ainda decide o codificador; a tela indica hardware, software ou não identificado conforme os dados disponíveis.
- Webcam limitada separadamente a 640 × 360, 15 FPS e até 900 kbps; tela recebe prioridade no orçamento e aproveita capacidade não usada pela câmera. A transmissão continua sujeita ao teto total.
- Apelidos temporários, espectadores por fonte e saúde de cada transmissão. Rotas são exibidas como direta, TURN, SFU ou não identificada a partir dos dados reais disponíveis.
- Economia de dados do espectador respeitada mesmo com adaptação desligada. SFU usa uma camada de vídeo para economizar codificadores; se alguém pede economia, o limite menor se aplica àquela fonte também para os demais espectadores.
- Opção de continuar ouvindo minimizado: mantém áudio e suspende recebimento de vídeo. O sistema/navegador pode suspender uma página móvel em segundo plano; não é garantia de reprodução com iPhone bloqueado.
- Aprovar entradas, bloquear novas entradas, expulsar, renovar e revogar convites. Quem já está conectado continua na sala ao renovar. Expulsar renova o convite para impedir reentrada com o código anterior; um convite novo pode ser compartilhado pelo anfitrião.
- Limites de tamanho, complexidade, frequência e fila de mensagens de controle; limite inicial também antes da leitura do JSON do PeerJS.
- Diagnóstico exportável por lista explícita de métricas, sem convite, senha, apelido, IP, SDP ou credencial. Medições manuais de jogos também podem ser exportadas.
- Transporte de mídia separado. SFU próprio opcional/experimental com autorização curta, limite de onze participantes e permissão por fonte. TURN próprio opcional permanece nas opções avançadas.
- CI essencial em Linux, execução cancelável, sem baixar Electron; compilação de Mac continua manual para controlar minutos de CI.

## Roteiro para comparar jogos reais

No painel **Medir desempenho no jogo**, registre FPS, ping e uso de GPU mostrados pelo jogo. O upload é coletado da transmissão; os demais valores são informados manualmente, não estimados pelo app.

1. Faça uma medição sem transmissão, usando o mesmo jogo, cenário e opções gráficas.
2. Repita com 1, 3, 5 e 10 espectadores de computadores externos, preferencialmente por cinco minutos em cada cenário.
3. Compare com Priorizar o jogo ligado/desligado, tela sozinha e tela + webcam.
4. Registre resolução, FPS, codec identificado e saúde da transmissão. Exporte o diagnóstico em cada etapa.
5. Anote também oscilações de internet e se foi necessário TURN. Não confunda a RAM de um teste com dez navegadores no mesmo PC com a RAM do transmissor numa partida real.

O painel e esse roteiro estão implementados. As medições com jogos reais e espectadores externos ainda precisam ser executadas; não foram substituídas por valores inventados.

## Alcance da validação

| Ambiente/cenário | Situação |
| --- | --- |
| Windows, duas instâncias completas, tela + webcam sintéticas | Testado localmente |
| Aprovação, bloqueio, expulsão, convite renovado | Testado entre as duas instâncias |
| Queda forçada do controle e do vídeo, sem recapturar | Testado localmente |
| Convite expirado com sessão ativa | Expiração simulada e recuperação testadas; sem esperar oito horas reais |
| Dez espectadores Chromium no mesmo computador | Regressão sintética; não equivale a dez pessoas em redes externas |
| SFU LiveKit próprio em loopback | Vídeo bidirecional, duas fontes, recuperação e expulsão testados localmente |
| TURN de produção em rede externa | Não disponibilizado nem validado nesta versão; modelo e gerador incluídos |
| Mac Intel / Apple Silicon | Pacotes compilados e verificados pelo workflow; uso em Mac físico pendente |
| Áudio isolado no Mac | Experimental; verificação estrutural e autoteste, sem captura real em Mac físico |
| iPhone / Safari físico | Pendente; fallback de tela cheia incluído, sem alegar homologação |
| Jogos reais com 1, 3, 5 e 10 pessoas | Pendente; painel de medição e roteiro disponíveis |

Todos precisam atualizar para 0.15 e recarregar a página para usar o protocolo novo. A atualização não converte salas abertas em versões anteriores.

A suíte local contém 39 testes unitários passando. Relatórios de integração locais: qa-v15-final-2 (duas instâncias), qa-v15-ten-verified (dez espectadores) e qa-v15-sfu-final (SFU). Testes de interface usam vídeo de canvas e webcam sintética; o botão Ouvir usa uma faixa sintética para verificar sua interface. Não são uma homologação acústica real do Windows/Mac.

