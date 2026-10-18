# Validação 0.13.0

28 testes unitários passaram no Windows: políticas de sala, captura, áudio nativo, autenticação de atualização e verificação de versão do Mac. A nova verificação do Mac recusa releases provisórias, versões antigas, arquivo de outra arquitetura e links fora do repositório previsto. Respostas têm tamanho e tempo limitados. O navegador só abre após clique.

O fluxo de isolamento de áudio da 0.12 foi validado por tons sintéticos e P2P. A captura de uma chamada real do Discord ainda não foi validada. O instalador Windows 0.13 foi conferido por assinatura Ed25519, tamanho, SHA-512 e comparação dos arquivos reais embutidos. A interface empacotada abre sem Node externo; encerrar em repouso para o motor e mantém a bandeja (35,1 MB observados no teste do portátil). O ciclo completo de instalar/desinstalar foi validado na 0.11; não se declara repetido neste documento.

Mac: o workflow gera DMG e ZIP para Intel e Apple Silicon e verifica a assinatura ad hoc dos aplicativos. Não há certificado Developer ID ou notarização. Câmera, captura, Gatekeeper e desempenho em Mac físico precisam de validação do usuário. Atualizações no Mac são verificadas automaticamente; substituição do aplicativo é manual.

Bandeja Windows: somente cópias instaladas verificam a versão pela URL fixa de releases. Nenhum executável é baixado ou iniciado pela bandeja. Ela apenas notifica; ao abrir, o motor valida o manifesto assinado antes da instalação. Falhas de rede são silenciosas e uma nova tentativa ocorre em quatro horas. Não consulta durante o uso do motor.
