# PENDENTE — só depois que prep.md propagar (~17:00 Londres, 14/07)

O site do PREP está construído, publicado e atribuído ao domínio. Falta
apenas a propagação do DNS da zona .md (fora do nosso controle) e um passo
que depende dela.

## 1. Verificar que prep.md acendeu (automático)
Abrir https://prep.md a partir das 17:00. Deve mostrar o site novo
(hero "The memory belongs to the project, not the AI." + os 3 passos).
Testar também: https://prep.md/spec, https://prep.md/about,
https://prep.md/prep-starter.zip (baixa o zip).

## 2. Registros de e-mail (MX/SPF) — precisam da zona ativa
Enquanto prep.md não resolve, a Vercel diz "not a DNS zone".
Depois que propagar, rodar (ou me pedir para rodar):

  vercel dns add prep.md "@" MX mx1.improvmx.com 10
  vercel dns add prep.md "@" MX mx2.improvmx.com 20
  vercel dns add prep.md "@" TXT "v=spf1 include:spf.improvmx.com ~all"

Depois conferir no improvmx.com que os ✗ viraram ✓ e mandar um teste
para hello@prep.md.

## Já está 100% pronto (não precisa fazer nada)
- Padrão v0.2 publicado: github.com/RafaelCarrer/prep.md (release v0.2)
- Site: repo github.com/RafaelCarrer/prep-site, deploy na Vercel,
  domínio prep.md + www atribuídos e verificados
- ameti.app: hero destaca PREP, /prep faz 308 → prep.md
- App do trabalho (the-old-star.ameti.app): intocado, 200
- Projeto Vercel antigo "prep-holding" pode ser apagado quando quiser
  (o domínio já saiu dele; a página provisória não é mais usada)
