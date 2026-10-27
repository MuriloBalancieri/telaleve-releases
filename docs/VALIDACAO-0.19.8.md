# Validação 0.19.8

Remove o menu padrão que aparecia ao pressionar Alt no aplicativo Windows.

- A janela deixa de ter uma barra de menu oculta acionável por Alt.
- A tecla não é bloqueada globalmente; os atalhos do sistema operacional, como Alt+Tab e Alt+F4, continuam a cargo do Windows.
- O menu da bandeja e os controles do aplicativo continuam disponíveis.

Verificação em um perfil Windows isolado confirmou a ausência do menu da aplicação e da barra de menu após três pressões de Alt. A interface permaneceu disponível e nenhuma sala foi criada. Alteração restrita ao aplicativo desktop; o webapp não precisa ser recarregado por causa desta mudança.

Atualize para 0.19.8 e reinicie o TelaLeve. Nenhum novo instalador Mac foi gerado.
