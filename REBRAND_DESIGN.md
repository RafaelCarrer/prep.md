# PREP — Decisões de Rebrand e Foco (2026-07-14)
<!-- Pensado no Fable com o Rafael; fonte da verdade para o Opus executar.
     Greenlights já dados pelo Rafael: TOOLS.md ✅, site PREP-first ✅,
     pacote de lançamento ✅, inglês-only (decisão dele) ✅. -->

## A. IDIOMA — inglês-only (DECIDIDO pelo Rafael)

- O PREP inteiro vira inglês-only: spec, prompt, README, site.
- REMOVER: SPEC.pt-BR.md, prompt/prep.pt-BR.md, README.pt-BR.md do repo.
- Adicionar ao README: "Translations are welcome via pull request."
  (transforma o corte de custo em convite à comunidade — padrão do setor)
- Digita NÃO muda (já publicado, congelado, custo zero se não tocar).
- Racional: padrão que quer virar substantivo é English-first; manter
  duas línguas dobra o custo de toda mudança para uma pessoa só.

## B. MARCA — NÃO renomear a AMETI; o PREP ganha casa própria

- AMETI continua sendo o ESTÚDIO (a estante, a história do fundador,
  o guarda-chuva). PREP é o PRODUTO/padrão com site próprio.
- Racional: fundir a empresa com um produto repete o erro clássico —
  se o PREP falhar, a AMETI continua; se vencer, "by AMETI" viaja junto.
  Padrões adotam melhor quando parecem neutros/independentes.
- Assinatura em tudo: "PREP — an open standard by Rafael Carrer (AMETI)".

## C. DOMÍNIO — prep.md (verificado: DNS inexistente em 2026-07-14)

- PRIMEIRA ESCOLHA: prep.md (TLD da Moldávia, mesmo padrão do agents.md,
  que vive em agents.md — precedente confirmado por DNS).
- AÇÃO DO RAFAEL: verificar disponibilidade real e comprar num registrar
  de .md (nic.md oficial; revendedores: Gandi, 101domain, Regery).
  Atenção: nomes de 4 letras podem ter preço "premium" — mesmo até
  ~US$100/ano vale, porque o nome vira o endereço.
- FALLBACKS em ordem: prepmd.org · prepstandard.org · prep-md.com.
- PLANO B (sem domínio novo): ameti.app vira o site do PREP (home 100%
  PREP; estúdio move para /about). Funciona, mas é segunda opção.
- URGÊNCIA REAL: a linha de identificação de todo PREP.md aponta hoje
  para ameti.app/prep. Trocar a URL canônica é barato AGORA (dia 2 do
  padrão) e caro depois. Decidir domínio ANTES de qualquer divulgação.
- Com o domínio novo: ameti.app/prep vira redirect permanente (301)
  para o site novo — nenhum link antigo quebra.

## D. O SITE DO PREP — mapa (pequeno de propósito)

Rotas:
- `/` — hero: "The open standard for AI-readable project folders" +
  subtítulo "Your projects, readable by any AI or agent — context in
  seconds." Problema (memória presa no chat) → a pasta num relance
  (árvore) → TRÊS casos de uso em destaque (pedido do Rafael):
  1. Personal work (as chihuahuas, o pão de domingo)
  2. Team work (um projeto que qualquer colega abre com qualquer IA)
  3. AI agents (o gancho da era dos agentes: agente sem contexto chuta;
     PREP é o onboarding em segundos)
  → botão copiar o prompt → link para a spec.
- `/spec` — a especificação completa renderizada (fonte: SPEC.md).
- `/about` — Rafael/AMETI em curto (a cozinha, 3 linhas), contato,
  e o link DISCRETO para Digita e ameti.app (pedido do Rafael:
  complementar, não visível demais).
- 404 padrão. NADA além disso.

Funcionalidades:
- Share: OG tags completas + botões estáticos de compartilhar
  (X, LinkedIn, Reddit, WhatsApp, copy-link). Sem SDK de terceiros.
- Contato: GitHub Discussions do repo prep.md como canal principal
  (público, zero manutenção, vira base de conhecimento) + um e-mail.
  SEM formulário com backend (violaria o próprio minimalismo).
- Redes sociais: GARANTIR o handle (@prepmd ou próximo) por proteção,
  postar só o anúncio de lançamento; a voz contínua é a conta pessoal
  do Rafael. NÃO criar boca nova para alimentar (uma pessoa só).

Visual: REUSAR o design system do ameti-site inteiro (tokens verde de
pub/serifa/latão, componentes, CopyPromptButton, testes, pipeline
Vercel). Zero design novo. A identidade conecta ao estúdio.

## E. MONETIZAÇÃO — decidido com honestidade

- ANÚNCIOS: NÃO. Ads em site de padrão destroem a credibilidade
  (imagine a página de um RFC com banner). Receita seria centavos;
  o custo é a marca. Veto firme.
- DOAÇÃO: SIM, discreto — GitHub Sponsors no repositório + um link
  pequeno no rodapé do site. Expectativa honesta: doação a padrão
  rende quase nada; o valor é sinalizar "mantido por uma pessoa real".
  (Sponsors exige cadastro do Rafael no GitHub — ação dele, opcional.)
- A monetização REAL é o longo prazo, fora do padrão: produtos em cima
  (o OS, ferramentas, "PREP for Teams", serviços). O padrão é
  distribuição e nome; nunca poluí-lo.

## F. LANE DO POSICIONAMENTO (guardrail de marketing)

- NÃO posicionar como contexto de repositório de código — faixa do
  AGENTS.md (ocupada). A faixa do PREP: projetos de VIDA e TRABALHO.
- Linha oficial de diferenciação:
  "AGENTS.md tells agents how to work in your code.
   PREP tells them everything about your project."
- Complementar ao MCP (já na spec) e complementar ao AGENTS.md (nova).

## G. TOOLS.md — extensão opcional aprovada

Adicionar à seção 7 da SPEC (extensões opcionais):
"TOOLS.md — a catalogue of the tools, APIs, MCP servers and
integrations available to agents working on this project."
E a linha correspondente no prompt (lista de opcionais).
REJEITADOS (não incluir): MEMORY.md (duplica memory/ + promoção),
PLAYBOOK.md (workflows = camada do OS, não do padrão).

## H. SEQUÊNCIA DE EXECUÇÃO

0. RAFAEL: comprar o domínio (prep.md; fallbacks acima). Sem domínio
   confirmado, nada de divulgação.
1. OPUS: construir o site do PREP (rotas acima, reuso do scaffold).
2. OPUS: batch único de mudanças no padrão (para evitar churn duplo):
   inglês-only (remover PT) + TOOLS.md + URL canônica nova na linha de
   identificação (spec §4, prompt regra PREP, exemplos) + regenerar
   prompt do site + testes + commits + release notes.
3. OPUS: ajustar ameti.app — PREP vira o destaque da home (hero CTA →
   site novo), Digita desce para item de estante normal; /prep vira
   redirect 301 para o domínio novo.
4. FABLE (quando resetar) ou OPUS: pacote de lançamento do PREP
   (Show HN + posts, gancho dos agentes, lane guardrail do item F).
