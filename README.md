# TelaLeve — Baixar e instalar

Compartilhe sua tela e webcam com seus amigos. Para usar o aplicativo, baixe **somente o instalador do seu computador**. Não é necessário ter conta no GitHub.

**[Abrir a versão mais recente](https://github.com/MuriloBalancieri/telaleve-releases/releases/latest)** · [Ver todas as versões](https://github.com/MuriloBalancieri/telaleve-releases/releases) · [Histórico de mudanças](CHANGELOG.md)

Na sala, cada tela ou webcam tem um cartão com o nome da pessoa. Clique em **Assistir** para abrir e em **Parar de assistir** para fechar. Você pode assistir duas transmissões ao mesmo tempo.

O TelaLeve lembra o último apelido usado e o preset da última transmissão de tela: modo, resolução, FPS, bitrate e adaptação. Essas escolhas ficam salvas no seu computador ou navegador.

## Qual arquivo baixar?

Downloads da versão **0.15.8**:

| Seu computador | Download |
| --- | --- |
| Windows de 64 bits | [Baixar instalador Windows (.exe)](https://github.com/MuriloBalancieri/telaleve-releases/releases/download/v0.15.8/TelaLeve-Setup-0.15.8.exe) |
| Mac com chip Apple Silicon — M1 ou posterior | [Baixar instalador Mac Apple Silicon (.dmg)](https://github.com/MuriloBalancieri/telaleve-releases/releases/download/v0.15.8/TelaLeve-0.15.8-mac-arm64.dmg) |
| Mac com processador Intel | [Baixar instalador Mac Intel (.dmg)](https://github.com/MuriloBalancieri/telaleve-releases/releases/download/v0.15.8/TelaLeve-0.15.8-mac-x64.dmg) |

No Mac, abra **menu Apple → Sobre Este Mac**. Se aparecer **Chip Apple M…**, escolha Apple Silicon. Se aparecer **Processador Intel**, escolha Intel.

## Instalar no Windows

1. Baixe o instalador `.exe` acima.
2. Se o TelaLeve já estiver aberto, escolha **Sair do TelaLeve** no ícone perto do relógio.
3. Abra o instalador e siga as instruções.
4. Inicie o TelaLeve pelo atalho criado.

O aplicativo instala para seu usuário. Não é necessário instalar Node.js ou outras ferramentas. O instalador ainda não tem certificado comercial de editor e o Windows pode exibir um aviso; confira a origem do download antes de decidir continuar.

## Instalar no Mac

1. Baixe o `.dmg` correspondente ao seu processador.
2. Abra o arquivo e arraste **TelaLeve** para **Aplicativos**.
3. Abra o TelaLeve pela pasta Aplicativos.
4. Quando solicitado, permita **Gravação de Tela** e **Câmera** em **Ajustes do Sistema → Privacidade e Segurança**. Reabra o app se o sistema pedir.

Esta versão tem assinatura local ad hoc, sem certificado Developer ID e sem notarização Apple. Se o macOS bloquear a abertura e você reconhecer o download deste repositório, confira **Ajustes do Sistema → Privacidade e Segurança → Abrir Mesmo**, quando disponível.

## Começar a usar

Abra o aplicativo e escolha **Criar sala** ou **Entrar com convite**. Dentro da sala, selecione a janela, a tela ou a webcam que deseja transmitir. Tela e webcam podem funcionar ao mesmo tempo. Nenhuma captura começa antes da sua confirmação.

A sala permite o anfitrião e até dez convidados. Cada pessoa pode assistir até duas fontes simultaneamente. A conversa por voz pode continuar no Discord.

**Áudio no Windows:** marque **Compartilhar áudio** no seletor de transmissão. Ao escolher uma janela, o app captura o áudio daquele aplicativo, podendo incluir outras janelas/abas dele. Ao escolher a tela inteira, exclui o Discord instalado e o próprio TelaLeve. Discord em uma aba não é separado do áudio das outras abas do mesmo navegador. O recurso depende de Windows com suporte à captura por processo; Windows 11 é a referência.

**Áudio no Mac (experimental):** no macOS 14.2 ou posterior, marque **Compartilhar áudio** no seletor e autorize a captura de áudio do sistema quando solicitado. Janela captura seu aplicativo e subprocessos; tela inteira exclui o Discord instalado e o próprio TelaLeve. Outras abas/janelas do mesmo aplicativo não são separadas. O recurso ainda precisa de validação em Mac físico; veja [instruções e limites do Mac](docs/MACOS.md).

## Atualizar o aplicativo

O app verifica novas versões ao iniciar e a cada quatro horas, adiando a verificação durante uma sala.

- **Windows instalado:** a atualização é baixada e autenticada automaticamente fora de salas. Quando estiver pronta, use **Opções → Reiniciar e atualizar** ou saia do aplicativo para instalar. A bandeja também avisa sobre novas versões quando o motor estiver fechado. Para procurar imediatamente, use **Opções → Procurar atualização**.
- **Mac:** o app avisa e oferece **Baixar instalador do Mac**. Saia do app, abra o novo DMG e substitua TelaLeve em Aplicativos. A instalação da atualização é manual nesta distribuição.

## Entrar pelo celular ou navegador

Quem está na sala pode usar **Entrar pelo celular** para compartilhar o link ou QR Code. Abra esse convite no navegador; não precisa instalar nada no celular. A página é [telaleve-p2p.pages.dev](https://telaleve-p2p.pages.dev/) e precisa do convite para entrar.

O vídeo é enviado por P2P. Algumas redes podem exigir um servidor TURN, que não está incluído nesta distribuição.

## E os outros arquivos da release?

Você só precisa do `.exe` ou `.dmg` do seu computador. `latest.yml`, `TelaLeve-update.json` e `.exe.blockmap` são arquivos usados pelo mecanismo de atualização. `SHA256SUMS.txt` permite conferir a integridade dos downloads, se desejar.

Os arquivos **Source code (zip)** e **Source code (tar.gz)** aparecem automaticamente no GitHub e **não instalam o TelaLeve**. Este repositório guarda os instaladores e a documentação; o fonte completo está em um repositório privado separado.

As versões antigas permanecem disponíveis no [histórico de releases](https://github.com/MuriloBalancieri/telaleve-releases/releases). Prefira a mais recente. Consulte os [testes e limites da versão 0.15.3](docs/VALIDACAO-0.15.3.md) e a [licença](LICENSE).

## Novidades da versão 0.15

Modo **Priorizar o jogo**, qualidade gradual, webcam mais leve, reconexão automática, apelidos, espectadores por fonte e saúde da transmissão. O anfitrião pode aprovar entradas, bloquear, expulsar e renovar convites sem encerrar a sala. A opção **Continuar ouvindo com a janela minimizada** preserva o áudio e suspende o vídeo recebido.

Todos devem atualizar o aplicativo e recarregar a página do navegador para entrar nas novas salas. O convite expira para novas entradas após oito horas; a sala ativa pode continuar. Nas opções, informe seu **upload** para o app reservar margem para o jogo.

P2P continua padrão. Nenhum servidor pago foi configurado. TURN e SFU próprios são opcionais: [instruções](docs/SERVIDORES-OPCIONAIS.md). [O que foi efetivamente testado](docs/VALIDACAO-0.15.3.md). Jogos reais com 1/3/5/10 espectadores, iPhone/Safari físico e Mac físico ainda precisam de validação.

Correção 0.15.3: resolvido o caso em que a qualidade ficava presa no início reduzido. Teste entre aplicativos confirmou retorno a 1920 × 1080, teto de 5 Mbps e limite de 30 FPS, sem recapturar. A qualidade recebida ainda depende do perfil e da conexão.

## Convidar por link

Crie uma sala e clique em **Copiar link da sala**. Envie o link ao amigo: ele abre no navegador e já tenta entrar. Se houver senha, precisa informá-la; se houver aprovação, aguarda o anfitrião. A entrada não liga tela, webcam nem microfone.

O endereço tem aproximadamente 150 caracteres nas opções padrão, sem encurtador ou servidor novo. Configurações personalizadas podem produzir links maiores. O código anterior continua disponível na seção **Código para versões anteriores**. Aplicativos antigos podem usar esse código ou atualizar para entender o link compacto.

### Abrir a sala no aplicativo

No link do convite, clique em **Abrir no TelaLeve** e confirme a abertura no navegador. Instale ou atualize para **0.15.5**. No Mac, mova o app para **Aplicativos** e abra uma vez. Se preferir, use **Continuar no navegador**. A senha da sala é solicitada no app; câmera e tela ficam desligadas até você escolher compartilhar.

### Personalizar as cores

Na versão **0.15.4**, clique em **◐** ao lado da engrenagem, ou abra **Opções de conexão → Personalizar cores**. Escolha uma das seis paletas ou ajuste **Cor de destaque** e **Cor de fundo**. Use **Salvar aparência** para manter; fechar ou Escape cancela a prévia. A escolha vale somente no seu aplicativo e fica salva neste computador.

### O botão não abriu o aplicativo?

Atualize para **0.15.5** e reabra a página do convite. Clique em **Abrir no TelaLeve** e confirme a abertura se o navegador perguntar. Esta versão corrige o endereço normalizado pelo Windows. Se a abertura for recusada pelo navegador, use **Continuar no navegador**.

### Tela cheia e janela flutuante

Atualize para **0.15.8**. Na transmissão, use **Ampliar** para tela cheia; **Esc** ou **Sair da tela cheia** volta à sala. **Picture-in-Picture** abre uma janela flutuante, inclusive com o app minimizado. O botão PiP aparece onde há suporte. O áudio mantém sua escolha de Ouvir/Silenciar e volume.
