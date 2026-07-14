# PREP — Especificação v0.1

> Um padrão aberto para pastas de projeto legíveis por IA.
> Prepare seu projeto uma vez; qualquer IA continua exatamente de onde você parou.

**Status:** Rascunho v0.1 · **Autor:** Rafael Carrer ([AMETI](https://ameti.app)) · **Licença:** CC BY 4.0
**Site:** https://ameti.app/prep

As palavras-chave DEVE (MUST), NÃO DEVE (MUST NOT), DEVERIA (SHOULD),
NÃO DEVERIA (SHOULD NOT) e PODE (MAY) seguem a [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

---

## 1. O problema

Cada modelo de linguagem guarda a própria memória do próprio jeito. Uma
conversa longa no ChatGPT fica pesada e começa a esquecer. Você troca para
o Claude ou o Gemini e recomeça do zero. O conhecimento que você construiu
fica preso dentro de uma conversa, dentro de um produto, e some quando a
aba fecha.

O PREP inverte isso. A memória pertence ao **projeto**, não à IA. Um
projeto é uma pasta comum no seu drive, organizada de um jeito pequeno e
previsível. Qualquer IA que consiga ler essa pasta abre o projeto, entende
onde as coisas estão, e continua — hoje no ChatGPT, amanhã no Claude, sem
perder nada. A conversa vira uma interface temporária sobre um projeto
permanente.

O PREP não é mais um modelo de IA, app ou plataforma. É uma convenção: um
punhado de arquivos com nomes combinados, numa ordem combinada. Se uma
pasta segue o padrão, qualquer ferramenta pode dar suporte.

## 2. Um projeto num relance

Este é um projeto PREP completo e válido:

```
Sunday Sourdough/
├── PREP.md
├── LOG.md
└── memory/
    └── 2026-07-14-session.md
```

**PREP.md** — o ponto de entrada. O primeiro arquivo que qualquer IA lê.

```markdown
> This project follows the PREP standard v0.1 — https://ameti.app/prep

# Sunday Sourdough

## ABOUT
Um pequeno projeto paralelo de padaria de fim de semana: vender pães de
fermentação natural para os vizinhos. Dono: Rafael. Meta atual — 10 pães
firmes todo domingo, com clientes que voltam.

## STATUS
Updated: 2026-07-14
State: Receita estável; testando fermentação a frio mais longa para sabor.
Next action: Definir o preço final antes de avisar a lista do WhatsApp.
Last session: memory/2026-07-14-session.md

## MAP
- LOG.md — histórico datado; leia para saber como chegamos aqui.
- memory/ — notas completas de sessão; leia a mais recente para o detalhe.
- knowledge/recipe.md — a receita de trabalho (leia ao assar ou ajustar).

## RULES
- Conselhos práticos e baratos; isto é um projeto paralelo, não uma padaria.
```

**LOG.md** — histórico append-only. Uma entrada datada por sessão ou evento.

```markdown
# Log — Sunday Sourdough

## 2026-07-14
Decidido testar fermentação a frio de 24h. Primeiro preço para vizinho a
£5/pão, a confirmar. Próximo: fechar preço.

## 2026-07-07
Primeiros 10 pães esgotaram. Dois vizinhos pediram encomenda fixa.
```

**memory/2026-07-14-session.md** — o retrato completo de uma sessão.

```markdown
# Session — 2026-07-14

## Context
Trabalhando no Sunday Sourdough. Foco de hoje: sabor e preço.

## What happened
Comparei fornada no mesmo dia vs. fermentação a frio de 24h. A frio ficou
com sabor melhor e encaixou na rotina de sábado à noite / domingo de manhã.

## Decisions
- Adotar fermentação a frio de 24h como método padrão.
- Preço-alvo £5/pão; ainda falta conferir o custo dos ingredientes por pão.

## Current state
Receita estável. Preço ainda não anunciado.

## Next steps
1. Calcular o custo por pão.
2. Confirmar £5 ou ajustar.
3. Avisar a lista do WhatsApp com a oferta.

## Open questions
- Os vizinhos querem encomenda fixa semanal? Dois já pediram.
```

É essa a ideia inteira. Tudo abaixo é precisão.

## 3. O núcleo obrigatório

Um projeto PREP DEVE conter:

1. **`PREP.md`** — o ponto de entrada (Seção 4).
2. **`LOG.md`** — um histórico append-only (Seção 5).
3. **`memory/`** — um diretório de retratos por sessão (Seção 6).

Nada mais é obrigatório. Um projeto PODE adicionar componentes opcionais
(Seção 7), mas um leitor NÃO DEVE depender da existência de nenhum deles.

Nomes de arquivos e seções (`PREP`, `ABOUT`, `STATUS`, `MAP`, `RULES`,
`LOG`, `memory`) DEVEM estar em inglês para compatibilidade universal. O
**conteúdo** DEVERIA estar no idioma do usuário.

Os arquivos DEVEM ser texto puro (Markdown recomendado), para sobreviver a
qualquer ferramenta e a qualquer modelo futuro.

## 4. PREP.md — o ponto de entrada

O `PREP.md` DEVE começar com uma única linha de identificação, para que
qualquer leitor saiba a convenção em uso e onde aprendê-la:

```
> This project follows the PREP standard v0.1 — https://ameti.app/prep
```

Depois, contém estas seções, nesta ordem:

- **ABOUT** (DEVE) — o que é o projeto e para quem, em poucas linhas.
  Estável; muda pouco.
- **STATUS** (DEVE) — onde o projeto está *agora*: uma data `Updated:`, o
  estado atual, a próxima ação e um ponteiro para o arquivo mais recente
  em `memory/`. É a única seção que muda a cada sessão, e DEVE ser curta.
- **MAP** (DEVE) — um índice do que existe na pasta e *quando* ler cada
  parte (ex.: "leia `knowledge/recipe.md` só ao assar"). O MAP é o que
  permite carregar leve em vez de varrer tudo.
- **RULES** (PODE) — instruções específicas do projeto para a IA: tom,
  proibições, fontes da verdade, um papel a assumir.

A seção `STATUS` DEVE carregar uma data `Updated:` para que a defasagem
fique visível num relance.

## 5. LOG.md — histórico append-only

O `LOG.md` é a linha do tempo escaneável. Cada entrada é datada e curta
(uma a cinco linhas): o que aconteceu, decisões, próximo passo. O detalhe
mora em `memory/`; o log é o índice para ele.

O `LOG.md` DEVE ser append-only. Quem escreve NÃO DEVE editar ou apagar
entradas existentes. O histórico nunca é reescrito.

## 6. memory/ — retratos de sessão

O `memory/` guarda um arquivo por sessão, nomeado `YYYY-MM-DD-session.md`
(acrescente `-2`, `-3` para várias sessões no mesmo dia).

Cada arquivo é um **bloco de continuação**: objetivo/contexto, o que
aconteceu, decisões, estado atual, próximos passos e questões em aberto —
o suficiente para uma IA nova, em qualquer plataforma, retomar sem a
conversa original.

Quem escreve NÃO DEVE sobrescrever um arquivo de sessão anterior. O
histórico completo é preservado.

## 7. Componentes opcionais

Um projeto PODE incluir, quando precisar, usando estes nomes padronizados
para que qualquer leitor os reconheça. Quando presentes, DEVEM constar no MAP.

- `knowledge/` — material de referência.
- `documents/` — produtos do trabalho.
- `TASKS.md` — lista de tarefas viva.
- `DECISIONS.md` — registro de decisões estruturado, quando o `LOG.md` não
  basta.
- `data/`, `assets/`, `code/` — conforme o projeto.

## 8. A pasta-raiz e o índice-raiz

Todos os projetos PREP de um usuário DEVERIAM morar numa única
**pasta-raiz** (nome padrão: `Projects/`). É assim que a pessoa reencontra
o próprio trabalho sem ter que lembrar onde está cada coisa.

A pasta-raiz é, ela mesma, um projeto PREP. Seu `PREP.md` descreve a
coleção, e seu **MAP é o catálogo**: uma linha por projeto — nome, assunto
em poucas palavras, status, última atualização.

```markdown
## MAP
- Sunday Sourdough — pão de fim de semana — active — 2026-07-14
- Chihuahua — pesquisa de cuidados do cão novo — active — 2026-07-13
- Kitchen Rota — notas de escala da equipe — perennial — 2026-07-12
```

Sempre que um projeto é salvo, a linha dele no MAP-raiz TAMBÉM DEVE ser
atualizada (e a escrita verificada). É o que mantém o catálogo verdadeiro.

## 9. Comportamento para quem implementa

Uma implementação do PREP (um prompt, uma ferramenta, um app) DEVERIA
seguir estes fluxos. É o que transforma a convenção de arquivos numa
experiência usável.

### 9.1 Abrir

Para abrir um projeto: leia o `PREP.md`, depois o arquivo mais recente em
`memory/`, e então **apenas** os arquivos que o MAP indica para a tarefa.
Um leitor NÃO DEVE varrer a pasta inteira ao abrir — o MAP existe para
evitar isso. Confirme em uma linha onde as coisas estão, e trabalhe.

O usuário DEVE conseguir voltar de três formas: por nome ("abre o
Chihuahua"), por listagem ("o que eu tenho?" → ler o MAP-raiz) ou por
assunto (buscar no conteúdo da pasta-raiz).

### 9.2 Salvar

Para salvar: escreva um novo arquivo de sessão em `memory/`; acrescente
uma entrada ao `LOG.md`; atualize apenas a seção `STATUS` do `PREP.md`;
promova fatos duráveis (9.4); atualize a linha do projeto no MAP-raiz.
Então **verifique cada escrita e informe onde as coisas foram salvas, em
palavras claras.**

Uma implementação NÃO DEVE reportar um save como concluído sem verificá-lo.
Se uma escrita falhar ou a ferramenta não tiver acesso a arquivos, ela
DEVE entregar o conteúdo dos arquivos na conversa para salvamento manual —
trabalho nunca se perde em silêncio.

Algumas plataformas conseguem criar arquivos mas não editá-los no lugar.
Nelas, uma atualização deixa a versão anterior ao lado da nova: o arquivo
mais recente com um dado nome é o válido. Uma implementação DEVE avisar
quando isso acontecer e DEVERIA oferecer a limpeza das duplicatas
desatualizadas durante o check.

### 9.3 Nome e sem duplicatas

Um projeto novo DEVE receber um nome antes de ser salvo; uma implementação
DEVERIA propor um nome curto a partir do assunto e deixar o usuário
confirmar ou trocar. Antes de criar um projeto, uma implementação DEVE
consultar o MAP-raiz e, se um projeto igual ou parecido existir, oferecer
abri-lo em vez de criar duplicata.

### 9.4 Promoção de fatos duráveis

Preferências duradouras, decisões que ficam e aprendizados permanentes
DEVERIAM ser promovidos para o `PREP.md` (ABOUT/RULES) ou `DECISIONS.md`
na hora de salvar, e não deixados enterrados num arquivo de sessão antigo
onde um boot leve não os veria.

### 9.5 Verificar e arquivar

Uma implementação DEVERIA oferecer um **check** (verificar se os arquivos
do MAP existem e se o catálogo-raiz bate com a realidade; reportar
inconsistências, corrigir só com permissão) e um **archive** (mover um
projeto encerrado para `archive/` dentro da raiz e atualizar o catálogo;
nada é apagado).

## 10. Segurança

Pastas PREP são texto puro e são lidas para dentro da conversa a cada
abertura — o conteúdo passa pelos servidores do provedor de IA e pode
aparecer em logs de chat e arquivos de sessão.

Por isso, uma implementação NÃO DEVE escrever segredos em arquivos PREP:
senhas, códigos de recuperação, chaves privadas, tokens de autenticação ou
números completos de cartão. Se o usuário fornecer um, ela DEVE recusar e
oferecer guardar uma **referência** — qual conta, qual e-mail e *onde* o
segredo mora (um gerenciador de senhas dedicado) — nunca o segredo em si.

PREP não é criptografia nem cofre. A privacidade de um projeto equivale à
segurança da conta de nuvem que o guarda; os usuários DEVERIAM ativar
verificação em duas etapas nessa conta. Uma implementação NÃO DEVE apoiar
usos inseguros em silêncio: o que o padrão não protege, ele diz com
clareza.

## 11. Fora de escopo (por decisão)

Os itens abaixo estão deliberadamente fora da v0.1 para manter o padrão
compreensível em cinco minutos. São registrados aqui para que a ausência
soe como escolha, não como esquecimento.

- **Concorrência / locking** entre sessões simultâneas. O PREP usa
  último-a-escrever-vence; o `LOG.md` append-only limita o dano.
  Coordenação formal de múltiplos escritores está fora de escopo.
- **Um ciclo de vida formal de componentes** (specified → active etc.). O
  `STATUS` em texto livre basta.
- **Papéis ou agentes como schema.** Um projeto que quer que a IA assuma
  um papel declara isso em `RULES`.
- **Uma base de conhecimento global** entre projetos.
- **Um sistema formal de upgrade.** A especificação é versionada; a
  orientação de migração viaja com a linha de versão.
- **Cabeçalhos de metadados por arquivo.** O MAP é a única fonte de
  localização e propósito.
- **Criação de apps ou automações.** O PREP padroniza a *memória* de
  projeto; construir ferramentas sobre isso é assunto separado, para uma
  versão futura.

## 12. Versionamento

Esta é a PREP v0.1. A versão aparece na linha de identificação de todo
projeto. Mudanças são registradas no changelog abaixo. Mudanças
incompatíveis DEVEM incrementar a versão.

## Changelog

- **v0.1 — 2026-07-14.** Primeiro rascunho público. Núcleo obrigatório
  (PREP.md, LOG.md, memory/), pasta-raiz e índice-raiz recursivo,
  comportamento de abrir/salvar/verificar/arquivar, promoção de fatos
  duráveis, anti-duplicação, segurança por referência e o registro de fora
  de escopo. Emendado no mesmo dia, após o primeiro uso real do padrão:
  comportamento em plataformas que só criam arquivos (o arquivo mais
  recente com o mesmo nome é o válido; avisar sobre cópias deixadas para
  trás; limpar durante o check).

---

PREP é um padrão aberto de Rafael Carrer, um kitchen manager em Londres que
constrói as próprias ferramentas. Faz parte da [AMETI](https://ameti.app).
Licenciado sob [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) —
use, adapte e construa sobre ele livremente, com atribuição.
