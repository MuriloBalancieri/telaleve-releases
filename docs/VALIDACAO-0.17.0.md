# Versão 0.17.0 — recuperação após fechamento e queda abrupta

A recuperação automática mantém o link, senha, aprovação e bloqueio; preserva fontes e chamadas de mídia entre sobreviventes. Em uma saída coordenada pelo botão Sair, o novo controle é preparado antes e o link muda, como na 0.16. Convites vencidos continuam sem admitir novas pessoas. Encerrar para todos permanece separado e encerra os participantes alcançados.

Protocolo 9: todos precisam atualizar o app e recarregar o webapp; versões anteriores são incompatíveis. 80 testes unitários passaram, incluindo credenciais, prioridade, limites, cópia vencida, tempo de reconexão de salas longas e cercamento. Integração Windows/Chromium com mídias sintéticas validou pagehide, crash real dos renderizadores web e desktop, retorno do ex-dono, reconexão concorrente, duas fontes sem recaptura, manutenção de players/chamadas, senha, admissão, expulsão e encerramento. O instalador Windows e a saída normal pelo motor empacotado foram conferidos. Mac Intel/Apple Silicon compilados em CI, com auxiliar de áudio e assinatura ad hoc verificados; não equivale a teste físico. Mac físico e iPhone/Safari continuam sem homologação.

A transferência prepara o novo controle antes da saída, preservando as identidades e conexões de mídia P2P entre participantes que permanecem. Capturas dos sobreviventes não precisam ser escolhidas de novo. A tela/webcam do dono que saiu são desligadas. Participantes conectados recebem automaticamente o novo convite, e o link anterior deixa de alcançar a sala. Convide novas pessoas com o link atualizado. Senha, bloqueio e aprovação são preservados. As credenciais de recuperação e a senha da sala são enviadas somente ao sucessor escolhido, pelo canal de controle autenticado; nunca fazem parte da lista pública de participantes ou do relatório de diagnóstico. O novo dono precisa desse controle completo para validar novas entradas e renovar convites protegidos.

No aplicativo desktop, Sair da sala e Sair do TelaLeve aguardam a transferência. Fechar pelo X continua minimizando para a bandeja quando há sala ativa. No navegador, o dono deve usar Sair da sala para transferir: fechar a aba, encerrar o processo à força, desligar o computador ou perder a internet abruptamente não fazem uma transferência coordenada. Somente participantes que continuam conectados recebem a migração. Falha de preparação tenta outro candidato; se ninguém assumir, a saída é cancelada para preservar a sala. Sala vazia encerra normalmente.

O protocolo passa a 8. Todos precisam atualizar o aplicativo ou recarregar o webapp; versões anteriores recebem a mensagem de incompatibilidade. O formato de convite e o protocolo registrado no sistema permanecem válidos.

# Versão 0.15.9 — volume de transmissão até 300%

Cada vídeo recebido com áudio tem slider de 0 a 300%, iniciando em 100%, com porcentagem visível ao lado e valor acessível para leitor de tela. Acima de 100% há ganho real via Web Audio, independente por fonte, sem duplicar o áudio do elemento de vídeo. O botão Ouvir continua necessário; Silenciar preserva o volume escolhido. A reconexão mantém a escolha. Remover uma fonte ou sair da sala desconecta e fecha os recursos de áudio. O grafo só é criado ao ouvir; silenciado ou sem áudio fica suspenso.

Se a amplificação não estiver disponível no navegador, o controle informa a limitação e usa reprodução normal até 100%. Uma falha de ativação não mostra áudio como ligado. Não modifica o áudio enviado pelo transmissor nem o volume de outras pessoas.

67 testes unitários, incluindo ganho, limites, fontes independentes, reconexão, suspensão e descarte. Integração Windows/Chromium mede amplitude de tom sintético antes e depois de 300%, verifica zero, porcentagem, silêncio e reconexão. Site público HTTPS, instaladores e canais de atualização conferidos. Mac físico e iPhone/Safari ainda não homologados.

Referências da implementação: https://developer.mozilla.org/en-US/docs/Web/API/GainNode e https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamSource .

# Versão 0.15.8 — lembrar apelido e preset

O último apelido aceito é preenchido ao criar ou entrar em uma sala. O navegador também restaura o apelido em visitas seguintes. A última transmissão de tela iniciada com sucesso salva modo, resolução, FPS, bitrate e adaptação de qualidade. Abrir a webcam não sobrescreve o preset da tela. As preferências ficam no armazenamento local do perfil do app ou do navegador, sem conta e sem servidor.

O registro aceita somente esses campos e valida os valores. Convites, senhas, credenciais, fontes e autorização de áudio não entram nesse registro. Dados inválidos ou armazenamento bloqueado não impedem usar a sala. A fonte continua sendo escolhida explicitamente, e a captura só começa ao confirmar.

Validação: testes unitários de persistência, isolamento de campos, dados inválidos e armazenamento indisponível; teste integrado com preset personalizado, saída e reabertura da página, nova sala e apelido no navegador. Testes integrados de tela/webcam, reconexão, áudio, tela cheia e PiP preservados. Mac físico e iPhone/Safari ainda não homologados.

# Versão 0.15.7 — escolher o que assistir

Telas e webcams aparecem em cartões separados com nome da pessoa, tipo da fonte e botão Assistir. A imagem aberta mostra Assistindo agora e Parar de assistir. Pessoas sem transmissão ficam em uma linha informativa, sem seleção. Ao abrir duas fontes, a mensagem explica como liberar espaço para outra. Também é possível parar pelo próprio player. A primeira fonte continua abrindo automaticamente.

Os cartões mantêm foco do teclado e os mesmos players durante atualizações da sala. A seleção não cria prévias ou decodificadores adicionais; permanecem no máximo dois vídeos. Temas pessoais, áudio, volume, tela cheia e Picture-in-Picture são preservados.

Validação: testes unitários, integração Windows com fontes sintéticas e site HTTPS em Chromium. A integração confere seleção, parada, reabertura, limite de dois, foco, identidade do player e volume após atualização da sala. Instaladores Windows e Mac têm conteúdo e canais de atualização conferidos. Mac físico, iPhone/Safari e jogos reais continuam pendentes de homologação.

# Versão 0.15.6 — tela cheia e Picture-in-Picture

Ampliar abre o vídeo recebido em tela cheia real. O aplicativo antes recusava a permissão fullscreen; agora aceita somente a página principal do TelaLeve durante uma sala. Outros sites, subquadros, tela cheia automática, microfone e demais permissões continuam sem liberação por essa mudança. O botão passa a Sair da tela cheia, e Esc ou duplo clique retornam à janela normal. O vídeo usa a área disponível com proporção preservada e controles acessíveis.

Picture-in-Picture abre o mesmo vídeo em janela flutuante nativa, sem nova captura, nova conexão ou elemento de vídeo extra. Áudio e volume continuam os já escolhidos. O aplicativo mantém a recepção das fontes selecionadas (até duas) quando minimizado enquanto há PiP; ao fechar a janela flutuante, volta à regra de economia e à opção Ouvir minimizado do usuário. Remover a fonte ou sair da sala encerra o PiP e libera o bloqueio de suspensão do app.

Os controles aguardam o vídeo carregar e mostram mensagem se a abertura falhar. Navegadores sem API compatível não mostram o botão PiP; há alternativa WebKit para navegadores compatíveis. Trocar entre tela cheia e PiP primeiro retorna ao modo normal; a mensagem pede um novo clique no modo desejado. Isso mantém a ação explícita do usuário. Não há abertura automática de PiP.

58 testes unitários passaram. Teste integrado entre dois apps Windows, com fontes sintéticas, confirmou janela nativa em tela cheia, saída por Esc, PiP nativo com dimensões reais e quadros avançando com janela principal oculta, remoção de fonte, retorno à economia, recuperação de vídeo/controle e preservação do botão Ouvir. Site público HTTPS também verificado em Chromium com tela cheia e PiP. Safari/WebKit é simulado em unidade; Mac, iPhone/Safari e outros navegadores físicos continuam pendentes de homologação.

# Versão 0.15.5 — corrigir abertura do convite no aplicativo

O receptor do protocolo era rígido: aceitava telaleve://join#invite=… e descartava o formato com barra telaleve://join/#invite=…. A normalização de URI do Windows pode acrescentar essa barra. A regressão reproduz o descarte na cópia da versão anterior com protocolo de teste registrado no Windows.

O aplicativo e a bandeja agora aceitam a barra opcional, fragmentos antigos e variações de maiúsculas no esquema/ação. Novos botões usam telaleve://join/?invite=… para evitar dependência de fragmento na entrega ao sistema. O convite HTTPS compartilhado continua com o segredo no fragmento, sem mudar protocolo P2P, autenticação, senhas, aprovação ou validade. A query do protocolo local não é uma requisição HTTP. A página orienta atualizar o aplicativo para 0.15.5.

O parser continua limitado à ação join, um único convite compacto e um limite de tamanho; rejeita usuários, senhas, parâmetros adicionais, argumentos de comando e convites inválidos/expirados. O teste de regressão faz a passagem por ShellExecute e um protocolo temporário isolado, não altera a associação telaleve instalada nem as salas do usuário, e remove a associação de teste ao finalizar. Confere abertura a frio, senha, mesma sala, bandeja, fragmento antigo normalizado e aprovação. Evento open-url do Mac continua simulado. Isso não equivale a uma homologação manual do Chrome/Firefox ou Mac físico.

51 testes unitários e o fluxo integrado Windows passaram. Arquivos dos instaladores e canais públicos de atualização foram verificados. A página pública foi atualizada e conferida com HTTPS.

# Versão 0.15.4 — aparência pessoal

O botão Personalizar aparência (◐), ao lado da engrenagem, e Opções de conexão → Personalizar cores abrem a personalização. Há seis paletas: Verde original, Azul, Violeta, Âmbar, Rosa e Claro. Cor de destaque e Cor de fundo podem ser escolhidas separadamente. Painéis, textos e controles derivam da paleta; mídias e vídeos não recebem filtros de cor.

A prévia é imediata. Salvar aparência mantém a seleção no perfil local do usuário do sistema, inclusive após reiniciar. Fechar ou pressionar Escape cancela a prévia. Restaurar original aplica a paleta original à prévia; é necessário salvar para mantê-la. Nada é enviado aos participantes, colocado no convite ou salvo na nuvem. O iniciador nativo em segundo plano não carrega a interface ou executa um processo extra por causa do tema.

Preferências contêm somente duas cores hexadecimais validadas, em um arquivo pequeno separado das opções de conexão. Arquivos inválidos ou maiores que o limite são ignorados e voltam à paleta original. O texto, o texto secundário e os rótulos dos botões recebem cores com contraste mínimo calculado de 4,5:1; limites dos controles usam 3:1. Não é uma certificação completa de acessibilidade.

50 testes unitários passaram, incluindo validação, contrastes em paletas extremas, persistência e isolamento entre perfis. Teste da interface em Windows verificou prévia, cancelar, salvar, reabrir interface, tema claro, restauração, cores personalizadas e aplicação ao seletor durante sala aberta, preservando convite e captura desligada. Mac: compilação e estrutura dos dois pacotes verificadas; aparência em Mac físico ainda não homologada.

# Versão 0.15.3 — abrir a sala no aplicativo

A página do convite tem **Abrir no TelaLeve**, **Continuar no navegador** e **Baixar o app**. O botão abre o aplicativo instalado por um protocolo de convite registrado pelo instalador do Windows e pelo pacote do Mac. Requer 0.15.3 ou posterior. No Mac, mova o app para Aplicativos e abra-o uma vez. O navegador pode pedir confirmação para abrir o aplicativo; não se presume que ele consiga detectar se o app está instalado.

Somente um clique explícito tenta abrir o aplicativo. Antes da transferência, a página encerra sua conexão de participante para liberar a vaga e parar fontes locais. Se a abertura for recusada ou o app não estiver instalado, Continuar no navegador permite entrar novamente. A senha deve ser informada no aplicativo, quando exigida; aprovação do anfitrião permanece obrigatória. Nenhuma captura é iniciada pela entrada.

O aplicativo valida tamanho, ação e formato do URI e valida o convite completo antes de entregá-lo à interface. Não executa comandos ou URLs arbitrários. Convites inválidos e expirados são recusados. A bandeja do Windows encaminha o convite ao motor em instância única, inclusive ao reabrir após repouso. Receber convite para outra sala pede confirmação antes de encerrar a sala atual; repetir o convite da mesma sala preserva a sessão.

47 testes unitários. Testes com o iniciador real do Windows, motor empacotado com perfil isolado e página independente verificam senha, encaminhamento, bandeja e alternativa no navegador. Evento open-url do Mac é simulado; abertura real por LaunchServices e uso em Mac físico continuam pendentes. Os pacotes de Mac têm a declaração do protocolo verificada estruturalmente.

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
