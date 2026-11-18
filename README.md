# OneMoreRPG

O VTT é uma plataforma web destinada à organização e realização de partidas de RPG de mesa de forma virtual. Seu objetivo é oferecer um ambiente integrado no qual Mestres e Jogadores possam criar e participar de campanhas, interagir por meio de salas de jogo, utilizar mapas, movimentar tokens e realizar rolagens de dados. A plataforma busca oferecer flexibilidade para diferentes sistemas de RPG, permitindo futuramente a personalização de fichas, regras e conteúdos por meio de recursos próprios.

📋 Product Backlog - Projeto VTT (RPG de Mesa)
ÉPICO 1: Autenticação e Gestão de Usuários
Gerenciamento de contas e acesso à plataforma.

US01 - Cadastro e Login: Como usuário, quero criar uma conta e fazer login para salvar minhas campanhas, fichas e preferências.

Critérios de Aceite: Tela de cadastro/login com e-mail e senha, criptografia de senha (bcrypt), sessão persistente (JWT ou Session).

US02 - Perfil do Usuário: Como usuário, quero definir meu nome de exibição e avatar para ser identificado nas mesas.

ÉPICO 2: Menu Principal e Gerenciamento de Campanhas
A estrutura central onde o usuário navega pelo sistema.

US03 - Dashboard Principal: Como usuário, quero ver um menu limpo com acesso rápido às opções: Campanhas, Fichas, Mapas e Homebrew.

US04 - Criar e Gerenciar Campanhas: Como Mestre, quero criar uma nova campanha definindo um nome e uma descrição, e gerar um link/código de convite para enviar aos jogadores.

US05 - Entrar em Campanha: Como Jogador, quero usar um link de convite ou código para entrar em uma mesa ativa.

US06 - Painel da Mesa (Room): Como participante, quero entrar na sala de jogo da campanha onde encontro o mapa, o chat de dados e a lista de jogadores online.

ÉPICO 3: Sistema de Fichas Livres
A flexibilidade para criar qualquer sistema de RPG.

US07 - Construtor de Fichas (Editor): Como usuário, quero criar uma ficha do zero adicionando blocos personalizados (campos de texto, números, caixas de seleção, listas).

US08 - Salvar e Gerenciar Fichas: Como usuário, quero listar minhas fichas criadas, editá-las, duplicá-las ou excluí-las.

US09 - Vincular Ficha à Campanha: Como jogador, quero selecionar qual das minhas fichas desejo usar ativamente em uma determinada campanha.

ÉPICO 4: Sistema de Rolagem de Dados em Tempo Real
A transparência das rolagens visíveis para todos.

US10 - Chat e Rolagem de Dados (Sintaxe básica): Como jogador/mestre, quero digitar comandos no chat (ex: /r 1d20+5) para realizar rolagens de dados.

US11 - Sincronização em Tempo Real (WebSocket): Como participante da mesa, quero ver as rolagens de dados de qualquer jogador instantaneamente no chat lateral ou em um alerta na tela.

US12 - Histórico de Rolagens: Como participante, quero rolar a barra do chat para cima e ver o histórico de todas as rolagens e mensagens trocadas na sessão atual.

ÉPICO 5: Sistema de Mapas e Upload de Mídia
O ambiente visual do jogo.

US13 - Upload de Imagens de Mapas: Como Mestre, quero fazer upload de arquivos de imagem (PNG, JPG) para usar como cenários nos mapas da campanha.

US14 - Biblioteca de Mapas da Campanha: Como Mestre, quero selecionar qual mapa da minha biblioteca está ativo e visível na mesa no momento.

US15 - Ferramentas Básicas de Visualização: Como usuário, quero dar zoom (aproximar/afastar) e arrastar o mapa para navegar facilmente pelo cenário.

ÉPICO 6: Sistema de Tokens e Permissões (Core do Jogo)
A interação dinâmica e segura no mapa.

US16 - Adicionar Tokens ao Mapa: Como Mestre, quero arrastar fichas ou avatares para o mapa ativo, transformando-os em tokens visíveis.

US17 - Movimentação Restrita por Jogador (Padrão): Como jogador, quero conseguir arrastar e mover pelo mapa somente os tokens que me pertencem, tendo meus movimentos bloqueados nos tokens dos outros.

US18 - Painel de Permissões do Mestre: Como Mestre, quero clicar em um token e definir/alterar qual jogador é o proprietário dele (ou deixá-lo exclusivo do Mestre).

US19 - Privilégios do Mestre: Como Mestre, quero ter permissão irrestrita para mover qualquer token no mapa, independentemente de quem seja o dono.

US20 - Sincronização de Posição dos Tokens: Como participante, quero ver os tokens se movendo em tempo real na tela de todos os jogadores à medida que são arrastados.

ÉPICO 7: Sistema de Homebrew (Opcional para MVP avançado)
Conteúdo personalizado criado pela comunidade.

US21 - Cadastro de Homebrew: Como usuário, quero criar itens, magias ou monstros personalizados e salvá-los no meu repositório de Homebrew.

US22 - Importar Homebrew para Campanha: Como Mestre, quero importar elementos do meu Homebrew para dentro de uma campanha específica.



Java 21 + Spring Boot (Backend recomendado)
Regras de negócio, autenticação, campanhas, fichas, permissões e comunicação.



React + TypeScript (Frontend recomendado)
Interfaces, dashboard, editores, fichas e ambiente de jogo.



PostgreSQL
Banco de dados relacional para usuários, campanhas, personagens, mapas e histórico.


Redis
Presença de jogadores, estados temporários e distribuição de eventos em tempo real. Opcional inicialmente.



PixiJS (Importante para o VTT)
Renderização de mapas, tokens, efeitos e elementos interativos em uma área 2D.



Docker
Padronização do ambiente de desenvolvimento e implantação.



======================================================================================================================================================================================================================



ÉPICO 1 — Fundação e infraestrutura
Preparar o ambiente de desenvolvimento e estabelecer a estrutura técnica do projeto.
P0 — Essencial
#001 — Definir o escopo e as regras de negócio do VTT
Descrição: Documentar o funcionamento esperado da plataforma, definir os tipos de usuários, as regras das campanhas, as permissões dos participantes e as funcionalidades que farão parte da primeira versão.

Resultado esperado: Documento com o escopo inicial e as principais regras de negócio do projeto.

Critérios de aceite:
- [ ] Objetivo da plataforma documentado.
- [ ] Funcionalidades do MVP identificadas.
- [ ] Papéis de Mestre e Jogador definidos.
- [ ] Regras de acesso às campanhas estabelecidas.
- [ ] Regras de propriedade e movimentação de tokens definidas.
- [ ] Funcionalidades futuras separadas das essenciais.
Responsável: A definir.
Dependências: Nenhuma.
#002 — Configurar o ambiente e as ferramentas do projeto
Descrição: Preparar os ambientes de desenvolvimento do backend e frontend, configurar as tecnologias e estabelecer uma estrutura inicial de repositórios.

Resultado esperado: Projeto inicial configurado e executando localmente.

Critérios de aceite:
- [ ] Java 21 e Spring Boot configurados.
- [ ] React e TypeScript configurados.
- [ ] Estrutura inicial do backend criada.
- [ ] Estrutura inicial do frontend criada.
- [ ] Dependências principais instaladas.
- [ ] Arquivos de configuração e variáveis de ambiente preparados.
Responsável: A definir.
Dependências: #001.
#003 — Organizar a arquitetura do backend
Descrição: Estabelecer uma arquitetura em camadas para separar as responsabilidades da aplicação e facilitar a manutenção e evolução do sistema.

Resultado esperado: Backend organizado, com estruturas definidas para as diferentes responsabilidades.

Critérios de aceite:
- [ ] Camadas de Controller, Service e Repository estabelecidas.
- [ ] Estruturas de entidades e DTOs criadas.
- [ ] Configurações de segurança e aplicação organizadas.
- [ ] Tratamento global de exceções estruturado.
- [ ] Convenções de nomenclatura definidas.
Responsável: A definir.
Dependências: #002.
#004 — Organizar a arquitetura do frontend
Descrição: Organizar a aplicação React para separar páginas, componentes, serviços, interfaces e funcionalidades.

Resultado esperado: Frontend estruturado para receber as funcionalidades da plataforma.

Critérios de aceite:
- [ ] Estrutura de páginas e componentes criada.
- [ ] Configuração de rotas estabelecida.
- [ ] Comunicação com a API centralizada.
- [ ] Organização de estilos definida.
- [ ] Tipos e interfaces TypeScript organizados.
Responsável: A definir.
Dependências: #002.
#005 — Configurar o banco de dados e o ambiente Docker
Descrição: Preparar o PostgreSQL e padronizar a execução dos serviços necessários ao desenvolvimento utilizando Docker.

Resultado esperado: Ambiente local reproduzível, com banco de dados configurado.

Critérios de aceite:
- [ ] PostgreSQL configurado.
- [ ] Docker Compose preparado.
- [ ] Aplicação consegue estabelecer conexão com o banco.
- [ ] Variáveis de ambiente configuradas.
- [ ] Instruções para iniciar o ambiente documentadas.
Responsável: A definir.
Dependências: #002.
#006 — Modelar o banco de dados da aplicação
Descrição: Projetar as entidades e os relacionamentos necessários para armazenar usuários, campanhas, participantes, fichas, mapas, tokens e mensagens.

Resultado esperado: Modelo de dados inicial documentado e implementado.

Critérios de aceite:
- [ ] Entidade de usuário definida.
- [ ] Estrutura de campanhas e participantes definida.
- [ ] Estrutura de convites definida.
- [ ] Estrutura inicial de fichas definida.
- [ ] Estrutura de mapas e tokens definida.
- [ ] Relacionamentos e restrições estabelecidos.
- [ ] Controle de versão do banco configurado, preferencialmente com Flyway.
Responsável: A definir.
Dependências: #003 e #005.



Regras de negócio — Cargos e permissões

RN-01 — Hierarquia de cargos da campanha
- Toda campanha deve possuir pelo menos um Mestre.
- Por padrão, o usuário que cria a campanha recebe o cargo de Mestre.
- Uma campanha poderá possuir vários Mestres e Administradores.
- O Mestre poderá promover participantes para Administrador ou Mestre.
- Administradores não podem promover participantes nem alterar os cargos de outros usuários.
- Um usuário poderá possuir cargos diferentes em campanhas distintas.

RN-02 — Permissões dos Mestres
Os Mestres possuem controle administrativo completo sobre a campanha.
- Podem alterar as configurações da campanha.
- Podem adicionar, editar, substituir e remover mapas.
- Podem adicionar, movimentar, editar e remover tokens.
- Podem acessar e administrar as fichas dos personagens, respeitando as regras de privacidade definidas.
- Podem promover participantes para Administradores ou Mestres.
- Podem expulsar, banir e remover banimentos de participantes.
- Podem bloquear ou liberar a movimentação de tokens de jogadores.

RN-03 — Permissões dos Administradores
Os Administradores auxiliam na organização e moderação da campanha, possuindo permissões operacionais, mas não administrativas sobre os cargos.
- Podem adicionar, editar, substituir e remover mapas.
- Podem adicionar, movimentar, editar e remover tokens.
- Não podem visualizar ou acessar as fichas particulares de outros jogadores.
- Podem bloquear ou liberar a movimentação dos tokens de jogadores.
- Podem expulsar participantes da campanha.
- Podem banir participantes.
- Podem remover banimentos.
- Não podem promover participantes para Administrador ou Mestre.
- Não podem alterar os cargos dos participantes.

RN-04 — Privacidade das fichas dos jogadores
- Cada jogador possui controle sobre suas fichas particulares.
- Mestres e Administradores não recebem automaticamente acesso às fichas particulares dos jogadores.
- Administradores nunca podem acessar fichas particulares de outros jogadores.
- O acesso às informações de uma ficha utilizada na campanha deverá respeitar as permissões de compartilhamento definidas para ela.
Observação: Recomendo separar a ficha particular da ficha compartilhada com a campanha. Assim, o jogador poderá manter informações privadas e disponibilizar somente os dados necessários para a partida.

RN-05 — Controle de movimentação dos tokens
- Por padrão, jogadores podem movimentar somente os tokens sob sua propriedade.
- Mestres e Administradores podem movimentar qualquer token.
- Mestres e Administradores podem bloquear ou liberar a movimentação dos tokens de jogadores.
- Um token bloqueado não poderá ser movimentado pelo seu proprietário.
- O bloqueio de movimentação não impede que Mestres e Administradores controlem o token.

RN-06 — Expulsão e banimento de participantes
- Mestres e Administradores podem expulsar participantes de uma campanha.
- Mestres e Administradores podem banir participantes, impedindo seu retorno.
- Mestres e Administradores podem remover banimentos.
- A expulsão remove o participante da campanha, mas não impede automaticamente seu retorno mediante um novo convite válido.
- O banimento impede a entrada do usuário na campanha, mesmo que ele possua um convite válido.
- Administradores não podem banir, expulsar ou alterar permissões de outros Mestres ou Administradores.


RN-07 — Hierarquia de moderação 
- Somente Mestres podem moderar outros Administradores ou Mestres. 
- Administradores podem moderar jogadores comuns, mas não podem expulsar, banir ou alterar as permissões de participantes com cargos de Administrador ou Mestre.

RN-08 — Privacidade e acesso às fichas
- Cada jogador possui controle sobre suas fichas particulares.
- Administradores não podem acessar fichas particulares de outros jogadores.
- Mestres podem solicitar acesso às fichas particulares dos jogadores.
- O jogador pode permitir ou negar esse acesso.
- O compartilhamento de informações da ficha com a campanha continua sendo controlado pelo jogador.

RN-09 — Gerenciamento de convites
- Somente Mestres podem criar convites para uma campanha.
- Administradores não podem gerar novos convites.
- Jogadores podem entrar em campanhas por meio de um convite válido.
- A administração dos convites fica sob responsabilidade dos Mestres.

RN-10 — Validade dos convites
- O Mestre pode escolher entre duas modalidades ao criar um convite:
  - Permanente: permanece válido até ser revogado por um Mestre.
  - Temporário: expira automaticamente após 3 dias da criação.
- Mestres podem revogar convites antes do vencimento.
- Convites expirados ou revogados não permitem a entrada na campanha.

RN-11 — Privacidade das campanhas
- Todas as campanhas são privadas.
- Campanhas não podem ser encontradas por meio de pesquisas públicas na plataforma.
- A entrada ocorre exclusivamente por meio de um convite válido.
- Não existe solicitação pública de participação.

RN-12 — Saída de participantes
- O jogador pode sair da campanha a qualquer momento.
- Seus tokens deixam de ser controláveis por ele e ficam sem proprietário.
- Suas fichas particulares permanecem salvas em sua conta.
- As fichas vinculadas à campanha permanecem nela, mas perdem o vínculo com o jogador que saiu.
- O nome do jogador deixa de aparecer como proprietário da ficha.
- Caso retorne à campanha, o vínculo com suas fichas não será recuperado automaticamente.


RN-13 — Criação e gerenciamento de tokens
- Mestres: podem criar, editar, remover, posicionar e atribuir tokens na campanha.
- Administradores: possuem as mesmas permissões dos Mestres para o gerenciamento de tokens.
- Jogadores: podem criar e personalizar seus próprios tokens na aba de personagens do menu.
- Jogadores: não podem adicionar seus tokens à campanha sem autorização de um Mestre ou Administrador.
- Mestres e Administradores: podem autorizar a entrada de tokens criados pelos jogadores na campanha, além de atribuí-los aos respectivos jogadores.

RN-14 — Propriedade dos tokens
- Um token pode ser atribuído a um jogador.
- O jogador responsável pode movimentá-lo livremente pelo mapa, desde que a movimentação não esteja bloqueada.
- Mestres e Administradores podem movimentar qualquer token, independentemente de quem seja o proprietário.
- Mestres e Administradores podem alterar a atribuição de um token.

RN-15 — Bloqueio de movimentação
- Mestres e Administradores podem bloquear a movimentação dos tokens de um jogador específico.
- O bloqueio impede que aquele jogador movimente qualquer token presente no mapa, mesmo que esteja atribuído a ele.
- O bloqueio não afeta os demais jogadores.
- Mestres e Administradores continuam podendo movimentar os tokens normalmente.
- Mestres e Administradores podem liberar a movimentação a qualquer momento.

RN-16 — Movimentação de tokens sem proprietário
- Tokens sem jogador atribuído podem ser movimentados somente por Mestres e Administradores.
- Jogadores não podem movimentar tokens sem proprietário.
- Mestres e Administradores podem atribuir esses tokens a jogadores quando desejarem.

RN-17 — Remoção de tokens
- Somente Mestres e Administradores podem remover tokens da campanha.
- Jogadores não podem excluir tokens, mesmo quando forem seus proprietários.
- A remoção de um token não exclui o personagem ou token original salvo na conta do jogador.

RN-18 — Comunicação na sala de jogo
- Todos os participantes da campanha podem enviar mensagens no chat público.
- As mensagens públicas são visíveis aos participantes conectados à sala.
- Jogadores podem enviar mensagens privadas a outros membros da campanha.
- Mensagens privadas são visíveis somente ao remetente e ao destinatário. Mestres e Administradores não podem acessá-las, mesmo possuindo permissões administrativas na campanha.
- Mestres e Administradores podem apagar mensagens inadequadas do chat público.
- Jogadores não podem apagar mensagens enviadas por outros participantes.

RN-19 — Rolagens de dados
- Todos os participantes podem realizar rolagens de dados.
- Por padrão, os resultados são públicos e visíveis a todos os participantes da sala.
- Jogadores e administradores podem realizar rolagens privadas, visíveis somente para eles e para o destinatário escolhido.
- Mestres podem realizar rolagens ocultas, cujos resultados são visíveis somente para o próprio Mestre.


RN-20 — Histórico de mensagens e rolagens
- Mensagens públicas: não são armazenadas após a sessão. Quando a sessão for finalizada, as mensagens públicas são descartadas.
- Mensagens privadas: ficam salvas e podem ser consultadas posteriormente pelos participantes envolvidos.
- Mensagens privadas fora da sessão: jogadores podem enviar e receber mensagens privadas mesmo quando a campanha não estiver em andamento.
- Rolagens de dados: os resultados não são salvos após a finalização da sessão.
- Rolagens ocultas: também não são armazenadas após a finalização.
