# Central Discord

Bot em Node.js que mantém somente dois comandos de barra:

- `/setup` cria cargos, categorias, canais de texto, salas de voz e suas permissões.
- `/gerenciar` publica os painéis de tickets, solicitações ou boas-vindas.

Os atendimentos criados pelos painéis são privados: apenas a pessoa que abriu, os cargos de equipe e o bot conseguem visualizá-los. O `/setup` é repetível e não exclui recursos do servidor.

## Instalação

1. Instale o Node.js 20 ou mais recente.
2. No terminal da pasta do projeto, execute `npm install`.
3. Copie `.env.example` para `.env` e preencha `DISCORD_TOKEN`. Defina também `GUILD_ID` para que os comandos apareçam na hora durante os testes.
4. No [Discord Developer Portal](https://discord.com/developers/applications), convide o bot com os escopos `bot` e `applications.commands`.
5. Nas permissões do convite, conceda ao bot: **Gerenciar cargos**, **Gerenciar canais**, **Ver canais**, **Enviar mensagens** e **Incorporar links**. Mantenha o cargo do bot acima dos cargos que ele criará.
6. Execute `npm start` e, no servidor, use `/setup`.

## Uso

`/setup nome:Minha Comunidade` prepara a estrutura inicial, incluindo os grupos **BEM-VINDO**, **REUNIÃO ILEGAL**, **BAQUES**, equipe, tickets e voz. Também cria os cargos territoriais BarreiraDoVasco, Bato, Campinho, Chapadao, CpxDoAlemao, CpxDaPenha, CpxDo18, Fuba, Gardenia, Pedreira, Providencia e Serrinha — cada um com variações de Líder, Frente e Gerente na mesma cor. Esses cargos territoriais não recebem permissões administrativas globais automaticamente.

Cada localidade também recebe uma categoria privada com os canais **avisos**, **chat-liderança**, **sugestões** e **roupas**. Os quatro cargos daquela localidade podem ver e enviar mensagens nesses canais; equipe e bot também têm acesso.

A opção `sincronizar_permissoes:true` reaplica as permissões apenas nos recursos que o bot já registrou como seus.

Depois, use `/gerenciar painel:Tickets` e `/gerenciar painel:Solicitações`. Sem informar `canal`, cada painel vai para o canal criado pelo setup; também é possível escolher qualquer canal de texto.

Somente membros com **Gerenciar servidor** podem executar os dois comandos. Isso também é validado pelo bot, não apenas pela interface do Discord.
