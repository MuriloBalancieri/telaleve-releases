# Validação 0.19.0

106 testes automatizados passaram, incluindo recusa de conta incorreta, credencial ausente, tickets vencidos e reutilizados e revogação de acessos temporários. A integração Windows confirmou entrada administrativa identificada em uma sala de teste com senha, bloqueio e aprovação, além da reconexão.

O login real do GitHub e a API publicada foram verificados separadamente: a conta autorizada foi reconhecida, o login cifrado foi restaurado após reiniciar o app e um ticket real permitiu entrar numa sala sintética. Nenhuma sala de amigos foi acessada para essa verificação.

O webapp publicado corresponde à compilação. O instalador comum e a edição privada do proprietário foram inspecionados; mantêm o mesmo runtime, protocolo, atualizador público e chave de atualização. O instalador privado contém apenas o identificador público do login, sem credencial que conceda administração.

O workflow macOS foi aprovado, os pacotes Intel e Apple Silicon foram comparados com o runtime da fonte e o helper de áudio universal passou no autoteste. A assinatura é ad hoc, sem notarização Apple. Mac físico, Safari/iPhone e redes de provedores diferentes não foram homologados nesta etapa.

Salas locais e sessões temporárias em versões antigas não são descobertas pelo painel. Entradas administrativas exigem anfitrião compatível, uma vaga disponível e conectividade P2P. O administrador é identificado na sala e a entrada não inicia captura.
