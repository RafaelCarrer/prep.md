# COMANDO — SITE DO PREP + BATCH v0.2 (colar numa sessão com Opus 4.8)

PRÉ-REQUISITO: o Rafael já comprou o domínio do PREP e vai informá-lo na
mensagem junto com este comando (ex.: "domínio: prep.md, já na Vercel" ou
"domínio: prepmd.org, comprado no registrar X"). SEM domínio informado,
pare e pergunte.

Executa o rebrand do PREP de ponta a ponta. NÃO PARE até tudo publicado
e verificado, exceto em decisão que só o Rafael pode tomar. Se for
retomada, detecte o que já existe e continue.

FONTE DA VERDADE (ler antes de qualquer escrita):
C:\Users\sthef\Documents\prep\REBRAND_DESIGN.md — TODAS as decisões
(idioma, marca, domínio, mapa do site, monetização, lane, TOOLS.md,
sequência). SIGA-O EXATAMENTE. A memória persistente tem o histórico.

O QUE EXECUTAR, NA ORDEM:

1. BATCH v0.2 no repositório do padrão (C:\Users\sthef\Documents\prep):
   a. Inglês-only: deletar SPEC.pt-BR.md, prompt/prep.pt-BR.md,
      README.pt-BR.md; remover badges/links PT do README; adicionar
      "Translations are welcome via pull request."
   b. TOOLS.md como extensão opcional (SPEC seção 7 + prompt, texto
      exato no REBRAND_DESIGN item G).
   c. URL canônica nova em TODOS os lugares: linha de identificação
      (SPEC §4 e exemplos §2/§8, prompt regra do PREP flow, arquivos do
      example/), LICENSE, README. Formato:
      "> This project follows the PREP standard v0.2 — https://<dominio>"
   d. Versão: v0.1 → v0.2 (mudança de URL canônica + TOOLS.md justificam
      minor bump). Changelog na spec. Release v0.2 no GitHub com notas.
   e. Commit + push + release.

2. SITE DO PREP (novo projeto):
   a. Copiar o scaffold de C:\Users\sthef\Documents\ameti-site para
      C:\Users\sthef\Documents\prep-site (package.json, next.config,
      tsconfig, globals.css, componentes, testes — adaptar nomes).
   b. Rotas: / , /spec, /about. HOME REDESENHADA (decisão do Rafael —
      a página principal É o passo a passo, ação primeiro):
      1) Hero curto: headline + 1 linha ("Your projects, readable by
         any AI. Set up in one minute:") desembocando direto nos passos.
      2) OS 3 PASSOS, grandes e numerados:
         Step 1 — Download the starter folder → botão prep-starter.zip
         Step 2 — Unzip it and drop the Projects folder into your
                  cloud drive (works with Google Drive, Dropbox,
                  OneDrive — anywhere your AI can read files)
         Step 3 — Tell your AI: "Read my Projects folder" (works in
                  ChatGPT, Claude, Gemini — any chat with file access)
                  → o comando em bloco copiável de uma linha
      3) "What you just set up" — as frases de valor: switch chats or
         even switch AIs — the conversation continues; the memory
         belongs to the project, not the AI; nothing locked in one app.
      4) O slider das 3 ilustrações (quando existirem).
      5) A pasta num relance (árvore) + casos de uso curtos
         (Personal / Team / AI agents).
      6) "Prefer to start from a prompt?" — o copy-prompt como caminho
         alternativo para usuários avançados.
      7) Link para a spec + rodapé.
      /spec (SPEC.md renderizada — pode ser
      HTML gerado do markdown em build ou transcrição fiel), /about
      (Rafael/AMETI curto + contato GitHub Discussions + o e-mail
      hello@prep.md visível como contato + link para ameti.app).
      O e-mail hello@prep.md também vai no rodapé de todas as páginas. MUDANÇA DECIDIDA PELO RAFAEL: NENHUMA menção ao
      Digita em lugar algum do site do PREP (nem no /about, nem rodapé).
      Digita vive só no ameti.app.
   b2. SLIDER DE ILUSTRAÇÕES na home: um strip deslizante simples
      (CSS scroll-snap, sem biblioteca JS) com 3 imagens que o Rafael
      JÁ GEROU — estão em C:\Users\sthef\Documents\prep\slides\
      (slide-1.png, slide-2.png, slide-3.png; verificadas pelo Fable:
      1=Save in any AI, 2=The folder is the memory, 3=Open in any other
      AI, conjunto dourado consistente). Copiá-las para public/slides/
      do site — e OTIMIZAR antes (são ~1.7-1.9 MB cada; converter para
      WebP ou comprimir para <300 KB cada, mantendo 1920px de largura,
      senão a home fica pesada). A slide-1 vira og:image (PNG/JPG
      comprimido para OG, não WebP; legendas: "Save in any AI" / "The folder is the
      memory" / "Open in any other AI"). Se as imagens ainda não
      existirem no build, o slider não renderiza (graceful) — o site
      publica sem ele e o Rafael adiciona depois. A slide-1 também
      vira og:image quando existir.
   c. Share: OG tags + botões estáticos (X, LinkedIn, Reddit, WhatsApp,
      copy-link) — links de share são URLs simples, sem SDK.
   d. Rodapé: link discreto "Sponsor" (para o repo GitHub) + GitHub +
      "by Rafael Carrer (AMETI)".
   e. Prompt embutido char-exact do canônico (novo tamanho, teste).
   e2. STARTER FOLDER PARA DOWNLOAD (decidido pelo Rafael): gerar no
      build um zip estático public/prep-starter.zip contendo a pasta
      "Projects/" pronta: PREP.md-raiz (template com MAP vazio e a
      linha de identificação v0.2), LOG.md (entrada inicial "Projects
      root created from the starter kit"), memory/ vazia com .gitkeep,
      prep-prompt.md (CÓPIA EXATA do prompt canônico — gerada do
      arquivo fonte no build, nunca digitada) apontado pelo MAP como
      "operating instructions — any AI should read this first", e um
      README.txt de 5 linhas: "Unzip → drop the Projects folder into
      your cloud drive → tell your AI: read my Projects folder".
      Na home, seção própria e simples: "Download the starter folder"
      → botão de download + os 3 passos em uma linha. Teste: zip
      existe no build, contém os arquivos certos, prompt idêntico ao
      canônico. Nome estável (prep-starter.zip) para links nunca
      quebrarem; a versão vai anotada dentro.
   f. Testes verdes, build estático ok.
   g. Repo GitHub novo: RafaelCarrer/prep-site (público). Vercel:
      ATENÇÃO — os domínios prep.md e www.prep.md JÁ ESTÃO atribuídos e
      verificados no projeto provisório "prep-holding" (mesma conta,
      página "in development" no ar desde 14/07). Ao publicar o site
      completo: criar o projeto prep-site, deploy prod, e MOVER os dois
      domínios do prep-holding para o prep-site (remover lá via API,
      adicionar aqui — mesma conta, sem conflito). Depois, o projeto
      prep-holding pode ser apagado.
   g2. DNS DO E-MAIL (ImprovMX já configurado pelo Rafael, aguardando
      registros): adicionar via CLI ao DNS de prep.md na Vercel:
      - vercel dns add prep.md '@' MX mx1.improvmx.com 10
      - vercel dns add prep.md '@' MX mx2.improvmx.com 20
      - vercel dns add prep.md '@' TXT "v=spf1 include:spf.improvmx.com ~all"
      Verificar depois em improvmx.com que os ✗ viraram ✓.
   h. Habilitar GitHub Discussions no repo prep.md:
      gh api -X PATCH repos/RafaelCarrer/prep.md -F has_discussions=true

3. AJUSTAR ameti.app (C:\Users\sthef\Documents\ameti-site):
   a. Home: PREP vira o destaque — hero CTA principal aponta para o
      domínio novo; Digita desce para item normal da estante (manter na
      estante, sem CTA no hero).
   b. /prep: virar redirect 301 para o domínio novo (next.config
      redirects — nota: com output export, usar meta refresh +
      canonical na página, ou vercel.json redirects, que funciona
      mesmo com static export. Preferir vercel.json).
   c. Build, testes, deploy, verificação.

4. VERIFICAÇÃO FINAL (só então pode parar):
   - Site novo: todas as rotas 200 no domínio novo, botão copiar ok,
     share links ok.
   - Repo padrão: release v0.2, sem arquivos PT, URL nova em tudo.
   - ameti.app: 200 em tudo, /prep redirecionando.
   - OBRIGATÓRIO: https://the-old-star.ameti.app = 200 (o app do
     trabalho NUNCA cai).

PROIBIDO: anúncios/ads em qualquer página; formulário de contato com
backend; posicionamento de código-repo (lane do AGENTS.md — ver item F
do REBRAND_DESIGN); MEMORY.md e PLAYBOOK.md no padrão; divulgar posts
(isso é do Rafael); tocar no the-old-star-uatr.

ENTREGA FINAL: URLs verificadas com códigos HTTP; o que mudou no padrão
(v0.2); LISTA PARA RAFAEL (decisões tomadas onde o desenho era omisso +
ações que só ele pode fazer: GitHub Sponsors signup, handle de rede
social, DNS se pendente); o que ficou de fora e por quê.
