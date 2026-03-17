# ProjetoMobile2026-1

# Historias de Usuario e Criterios de Aceitacao

## Estrutura
Este documento segue o formato:
- **Como**
- **Eu quero**
- **Para**
- **Cenarios com Dado, E, Quando, Entao**

## Historias de Usuario - Morador

### Funcionalidade: HU-01 - Login no aplicativo
**Como** um morador
**Eu quero** fazer login no aplicativo
**Para** acessar minhas reservas e agendar quadras

Cenario 1: Login com credenciais validas
**Dado** que estou na tela de login
**E** informo credenciais validas
**Quando** envio o formulario
**Entao** devo ser autenticado e redirecionado para a tela inicial

Cenario 2: Login com credenciais invalidas
**Dado** que estou na tela de login
**E** informo credenciais invalidas
**Quando** envio o formulario
**Entao** devo visualizar mensagem clara de erro sem travar a aplicacao

Cenario 3: Persistencia de sessao
**Dado** que o login foi realizado com sucesso
**Quando** navego pelo app
**Entao** a sessao deve permanecer ativa ate logout ou expiracao

### Funcionalidade: HU-02 - Visualizar quadras disponiveis
**Como** um morador autenticado
**Eu quero** visualizar as quadras e horarios
**Para** escolher uma opcao de reserva

Cenario 1: Carregamento da lista de quadras
**Dado** que estou na tela inicial
**Quando** a pagina carrega
**Entao** devo ver a lista de quadras disponiveis

Cenario 2: Consulta de horarios por data
**Dado** que existem horarios para uma quadra
**E** seleciono uma data
**Quando** consulto disponibilidade
**Entao** devo visualizar horarios disponiveis e indisponiveis

Cenario 3: Data sem disponibilidade
**Dado** que nao ha disponibilidade para a data selecionada
**Quando** visualizo os horarios
**Entao** devo ver estado vazio com orientacao para escolher outra data

### Funcionalidade: HU-03 - Realizar agendamento de quadra
**Como** um morador autenticado
**Eu quero** reservar um horario em uma quadra
**Para** garantir meu uso da quadra no periodo desejado

Cenario 1: Reserva criada com sucesso
**Dado** que escolhi quadra, data e horario disponivel
**Quando** confirmo a reserva
**Entao** o agendamento deve ser criado com sucesso

Cenario 2: Conflito de reserva
**Dado** que o horario foi reservado por outro usuario antes da confirmacao
**Quando** tento confirmar a reserva
**Entao** devo receber mensagem de indisponibilidade e sugestao de outro horario

Cenario 3: Reserva aparece em Minhas Reservas
**Dado** que uma reserva foi criada
**Quando** acesso Minhas Reservas
**Entao** devo visualizar a reserva recem-criada

### Funcionalidade: HU-04 - Visualizar minhas reservas
**Como** um morador autenticado
**Eu quero** consultar minhas reservas
**Para** acompanhar horarios futuros e historico

Cenario 1: Lista de reservas existente
**Dado** que tenho reservas cadastradas
**Quando** acesso Minhas Reservas
**Entao** devo ver lista com data, horario, quadra e status

Cenario 2: Lista vazia
**Dado** que nao tenho reservas
**Quando** acesso Minhas Reservas
**Entao** devo ver mensagem de lista vazia com CTA para agendar

Cenario 3: Diferentes status
**Dado** que possuo reservas com diferentes status
**Quando** visualizo a lista
**Entao** os status devem estar claramente identificados

### Funcionalidade: HU-05 - Cancelar reserva
**Como** um morador autenticado
**Eu quero** cancelar uma reserva futura
**Para** liberar o horario e evitar no-show

Cenario 1: Cancelamento permitido
**Dado** que tenho uma reserva futura elegivel
**E** clico em cancelar e confirmo a acao
**Quando** a operacao e processada
**Entao** o status da reserva deve mudar para cancelada

Cenario 2: Cancelamento bloqueado por regra
**Dado** que a reserva ja passou ou nao permite cancelamento
**Quando** tento cancelar
**Entao** devo receber mensagem explicando a restricao

Cenario 3: Horario liberado apos cancelamento
**Dado** que conclui um cancelamento com sucesso
**Quando** volto para a lista de horarios da quadra
**Entao** o horario deve voltar a ficar disponivel conforme regra de negocio

### Funcionalidade: HU-06 - Acessar voucher/comprovante da reserva
**Como** um morador autenticado
**Eu quero** visualizar o voucher da reserva
**Para** apresentar comprovacao no dia do uso da quadra

Cenario 1: Voucher de reserva ativa
**Dado** que tenho uma reserva ativa
**Quando** abro o voucher
**Entao** devo ver identificacao da reserva, data, horario e quadra

Cenario 2: Voucher legivel e consistente
**Dado** que o voucher foi exibido
**Quando** compartilho ou apresento o comprovante
**Entao** as informacoes devem estar legiveis e consistentes com a reserva

Cenario 3: Reserva cancelada
**Dado** que a reserva foi cancelada
**Quando** tento abrir o voucher
**Entao** devo ver status atualizado e orientacao adequada

### Funcionalidade: HU-07 - Editar perfil
**Como** um morador autenticado
**Eu quero** atualizar meus dados de perfil
**Para** manter minhas informacoes corretas

Cenario 1: Atualizacao valida
**Dado** que estou na tela de perfil
**E** altero campos validos
**Quando** salvo as alteracoes
**Entao** as alteracoes devem persistir

Cenario 2: Validacao de campos
**Dado** que envio dados invalidos
**Quando** tento salvar
**Entao** devo receber mensagens de validacao por campo

Cenario 3: Persistencia apos retorno
**Dado** que as alteracoes foram salvas
**Quando** retorno para a tela de perfil
**Entao** os dados atualizados devem continuar visiveis

## Historias de Usuario - Administrador

### Funcionalidade: HU-08 - Login com perfil administrador
**Como** um administrador
**Eu quero** acessar uma area administrativa
**Para** gerenciar agenda, reservas e regras do condominio

Cenario 1: Acesso administrativo valido
**Dado** que informo credenciais validas de administrador
**Quando** realizo login
**Entao** devo acessar funcionalidades administrativas

Cenario 2: Bloqueio para usuario comum
**Dado** que sou usuario comum
**Quando** tento acessar telas administrativas
**Entao** devo receber bloqueio de acesso por permissao

Cenario 3: Sessao expirada
**Dado** que a sessao de administrador expira
**Quando** tento executar uma acao administrativa
**Entao** devo ser redirecionado para autenticacao

### Funcionalidade: HU-09 - Configurar regras de agendamento
**Como** um administrador
**Eu quero** definir regras de negocio
**Para** garantir uso justo das quadras

Cenario 1: Limite semanal por apartamento
**Dado** que estou na area de configuracoes
**E** defino limite de horas por semana por apartamento
**Quando** salvo a configuracao
**Entao** o sistema deve aplicar a regra em novas reservas

Cenario 2: Janela de antecedencia maxima
**Dado** que configuro antecedencia maxima de agendamento
**Quando** um morador tenta reservar fora da janela permitida
**Entao** o sistema deve impedir a acao com mensagem explicativa

Cenario 3: Regras refletidas imediatamente
**Dado** que altero regras validas e salvo
**Quando** moradores realizam novos agendamentos
**Entao** as novas regras devem ser refletidas imediatamente

### Funcionalidade: HU-10 - Gerenciar bloqueios de agenda
**Como** um administrador
**Eu quero** bloquear datas e horarios de uma quadra
**Para** reservar janelas para manutencao, eventos ou indisponibilidade

Cenario 1: Bloqueio de periodo
**Dado** que seleciono uma quadra, data e faixa de horario
**Quando** confirmo bloqueio
**Entao** o periodo deve ficar indisponivel para novos agendamentos

Cenario 2: Conflito com reserva ativa
**Dado** que existe reserva ativa no periodo selecionado
**Quando** tento bloquear o mesmo horario
**Entao** devo visualizar conflito e opcoes de tratamento conforme regra interna

Cenario 3: Remocao de bloqueio
**Dado** que removo um bloqueio futuro
**Quando** moradores consultam disponibilidade
**Entao** o horario deve voltar a aparecer como disponivel

### Funcionalidade: HU-11 - Gerenciar reservas de moradores
**Como** um administrador
**Eu quero** consultar e administrar reservas de todos os moradores
**Para** resolver conflitos e dar suporte operacional

Cenario 1: Filtros administrativos
**Dado** que acesso a listagem administrativa
**E** aplico filtros por data, tipo de quadra, bloco/apartamento ou status
**Quando** executo a busca
**Entao** devo ver resultados coerentes com os filtros

Cenario 2: Cancelamento administrativo
**Dado** que identifico reserva com necessidade de intervencao
**Quando** cancelo administrativamente
**Entao** a reserva deve mudar de status e registrar motivo e autor da acao

Cenario 3: Reflexo para o morador
**Dado** que uma reserva e alterada por administrador
**Quando** o morador acessa Minhas Reservas
**Entao** deve visualizar o status atualizado

### Funcionalidade: HU-12 - Auditoria e historico administrativo
**Como** um administrador
**Eu quero** visualizar historico de acoes criticas
**Para** garantir rastreabilidade e transparencia da operacao

Cenario 1: Registro de eventos criticos
**Dado** que ocorre acao critica administrativa
**Quando** consulto historico
**Entao** devo ver data, hora, usuario responsavel e resumo da acao

Cenario 2: Investigacao por filtros
**Dado** que preciso investigar um incidente
**E** filtro o historico por periodo e tipo de acao
**Quando** aplico os filtros
**Entao** devo localizar os eventos relevantes

Cenario 3: Estado vazio sem erro
**Dado** que nao existem eventos no periodo selecionado
**Quando** aplico filtro
**Entao** devo ver estado vazio sem erro

## Regras Gerais de Aceitacao
1. O aplicativo deve ser responsivo para uso em celular e desktop.
2. Mensagens de erro e sucesso devem ser claras, curtas e acionaveis.
3. A navegacao inferior deve manter consistencia entre as telas principais.
4. Nenhum fluxo principal deve depender de recarregar manualmente a pagina para refletir mudancas.
