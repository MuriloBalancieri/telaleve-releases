# Validação 0.19.6

Identificação local de aplicativos que o Windows indica usando a câmera, no seletor de webcam e após uma falha de abertura.

- Consulta somente ao abrir a aba Webcam ou após uma tentativa que falhou; não há monitoramento contínuo.
- Exibe nomes, sem compartilhar caminhos, processos ou informações do computador com a sala ou o serviço.
- A lista pode ser incompleta e não confirma que o aplicativo bloqueia a webcam selecionada. A informação é uma indicação do Windows, não uma detecção garantida de conflito.
- Histórico sem processo correspondente e o próprio TelaLeve são desconsiderados. Sem encerramento automático de aplicativos.
- Organização da documentação e das notas históricas.

131 testes automatizados e cinco verificações do filtro nativo aprovados. Integração Windows com câmera simulada verificou o texto de indicação, a consulta sem ligar a webcam, a recuperação da abertura e a liberação ao parar. A detecção de conflitos reais entre dispositivos ou aplicativos físicos ainda não foi homologada. Recurso disponível no aplicativo Windows; navegadores e Mac não identificam os outros programas.

Atualize para 0.19.6 e reinicie o TelaLeve. Nenhum novo instalador Mac foi gerado.
