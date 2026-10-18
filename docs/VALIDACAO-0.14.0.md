# Validação 0.14.0 — áudio isolado no Mac

## Implementação

Capturador original Objective-C com Core Audio process taps, compilado para arm64 e x86_64. Janela: resolve o PID pelo identificador CGWindow da fonte selecionada e inclui sua árvore de processos. A identidade do processo usa PID e instante de criação; janela encerrada ou PID reutilizado interrompe o áudio. Tela inteira: lista explícita dos processos permitidos, excluindo Discord, auxiliares/descendentes e TelaLeve. Processos desconhecidos são excluídos. Alterações na lista de processos de áudio suspendem o recebimento até nova classificação. Limite de 256 objetos de áudio.

O tap mistura somente a lista autorizada. Lista vazia não é enviada ao Core Audio; produz silêncio até existir processo permitido. Sem captura geral de fallback, microfone, arquivos de áudio, drivers, alteração do volume ou da saída padrão. Dispositivo agregado privado e temporário, encerrado com a captura/processo. Buffers limitados; pipe de saída sem bloqueio permanente e interrupção em sobrecarga ou mudança de formato. Conversão de alta qualidade do AVAudioConverter para PCM estéreo 48 kHz/16 bits, reutilizando o transporte P2P existente.

Mac anterior a 14.2 mantém áudio isolado indisponível. O app e o helper incluem NSAudioCaptureUsageDescription. A captura só é iniciada pela seleção autorizada de fonte em uma sala e o pedido de permissão pode aguardar até 90 segundos. Encerrar a sala cancela o helper.

## Verificado nesta entrega

- 29 testes unitários passaram no Windows e no runner macOS, incluindo limites de versão e plataforma, cancelamento e tokens da captura, políticas de sala e autenticação da atualização.
- Autoteste do executável nativo no runner macOS: filtro de árvore de processos, Discord e descendentes, TelaLeve, exclusão de processos desconhecidos, aplicação selecionada, e conversão de tons sintéticos em 44,1/48 kHz para PCM estéreo 48 kHz/16 bits. Não inicia taps nem pede permissão de captura real nesse teste.
- Compilação do helper para Intel e Apple Silicon; assinatura ad hoc do app e helper e chave de permissão conferidas na geração dos pacotes.
- Pacote Windows: abre sem Node externo, mantém isolamento do renderer e limite de dez convidados. Fechar em repouso encerra o motor e mantém a bandeja; 33,5 MB observados no teste.
- Instalador Windows: autenticação Ed25519, mesma chave pública das versões anteriores, tamanho/SHA-512 e arquivos embutidos comparados ao fonte.

## Limites que ainda precisam de Mac físico

Captura real de outros aplicativos, resposta aos pedidos de permissão, isolamento de uma chamada real do Discord, reinício de aplicativos durante reprodução, troca de saída/Bluetooth e desempenho em uso prolongado não foram validados. O recurso de áudio do Mac é experimental até essa validação. Compilar e testar o filtro com dados sintéticos não confirma a captura real no computador do usuário.

Outras janelas e abas do mesmo aplicativo podem ter áudio incluído; Discord em uma aba não é separado das outras abas. Conteúdo protegido e processos que não possam ser associados com segurança à janela podem ficar sem áudio. A distribuição continua com assinatura local ad hoc, sem Developer ID/notarização; atualizações do Mac são verificadas automaticamente e instaladas manualmente. O ciclo completo de instalação/desinstalação Windows foi validado na 0.11, não repetido nesta entrega.
