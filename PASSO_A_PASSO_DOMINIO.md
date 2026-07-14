# prep.md — Passo a passo profissional (domínio, e-mail, DNS)

## 1. Comprar o domínio (hoje, ~10 min)

- Compre prep.md no registrar onde encontrou (~$20/ano) — se for casa
  conhecida (Porkbun, Gandi, Regery, 101domain, Namecheap), ok.
- Conta do registrar: usar carrer88@gmail.com (NUNCA e-mail do próprio
  domínio), senha forte no gerenciador, 2FA LIGADO.
- AUTO-RENEW LIGADO + lembrete no calendário 1 mês antes da renovação.
  (O domínio vira a identidade do padrão — a URL canônica em todo
  PREP.md do mundo. Perdê-lo por renovação esquecida é a morte mais
  boba possível. Trate como o alvará da empresa.)

## 2. DNS — nameservers da Vercel (AJUSTADO: o registrar .md não tem
     painel de DNS próprio, só delegação)

No formulário de registro (NS Delegation), preencher:
- Primary NS HostName:   ns1.vercel-dns.com
- Secondary NS HostName: ns2.vercel-dns.com

(Mesmo esquema do ameti.app — o DNS inteiro fica gerenciável pela
Vercel/CLI, que o Opus já opera.)

## 3. E-mail — redirecionamento grátis via ImprovMX (AJUSTADO)

- Criar conta grátis em improvmx.com (com o Gmail pessoal), adicionar o
  domínio prep.md e o alias: hello@prep.md → carrer88@gmail.com.
- Registros MX/SPF necessários no DNS da Vercel (o Opus adiciona via
  CLI, ou manualmente no painel):
  - MX @ → mx1.improvmx.com (prioridade 10)
  - MX @ → mx2.improvmx.com (prioridade 20)
  - TXT @ → "v=spf1 include:spf.improvmx.com ~all"
- Opcional fino (depois): no Gmail, "Configurações → Enviar e-mails como"
  hello@prep.md, para RESPONDER com o endereço da marca.
- REGRA DE OURO: hello@prep.md = contato público e cadastros
  não-críticos (redes sociais). Contas críticas (registrar, Vercel,
  GitHub) = sempre no Gmail pessoal.

## 4. Redes sociais (depois do forwarding funcionar)

- Garantir o handle (X: @prepmd ou próximo) usando hello@prep.md.
- Só garantir — não alimentar. A voz é a sua conta pessoal.

## 5. Rodar o Opus

- /model claude-opus-4-8
- Colar COMANDO_OPUS_PREP_SITE.md e informar na mesma mensagem:
  "domínio: prep.md, comprado no registrar X, DNS com A/CNAME
  apontando para a Vercel" (ou Cloudflare, se plano B).
- O Opus faz: batch v0.2 do padrão + site novo + domínio no projeto
  Vercel + ajustes no ameti.app + verificação completa.

## 6. Propagação

- DNS propaga de minutos a ~24h. A Vercel emite o certificado HTTPS
  sozinha quando o domínio verificar. Se o Opus reportar "domínio
  pendente de verificação", é só esperar e pedir para verificar de novo.

## Custos totais desta fase

- Domínio: ~$20/ano. Hospedagem: $0 (Vercel Hobby). E-mail: $0
  (forwarding). Total: ~$20/ano para a casa definitiva do padrão.
