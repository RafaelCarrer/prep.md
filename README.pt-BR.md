# PREP.md

> **Memória de projeto para qualquer IA. Prepare seu projeto uma vez; qualquer IA continua exatamente de onde você parou.**

🇬🇧 [Read in English](README.md)

![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-green)
![Funciona com](https://img.shields.io/badge/funciona%20com-ChatGPT%20·%20Claude%20·%20Gemini-blue)
![Padrão](https://img.shields.io/badge/PREP-v0.1-orange)

---

## O problema

Cada IA guarda a própria memória do próprio jeito. Uma conversa longa no
ChatGPT fica pesada e começa a esquecer. Você troca para o Claude ou o
Gemini e recomeça do zero. O conhecimento que você construiu fica preso
dentro de uma conversa, dentro de um produto, e some quando a aba fecha.

## A ideia

**O PREP inverte: a memória pertence ao projeto, não à IA.**

Um projeto é só uma pasta no seu drive, organizada de um jeito pequeno e
previsível:

```
Sunday Sourdough/
├── PREP.md      ← o ponto de entrada: o que é, onde está, o que ler
├── LOG.md       ← histórico append-only, uma linha datada por sessão
└── memory/      ← um retrato completo de cada sessão
```

Qualquer IA que consiga ler a pasta abre o projeto, vê exatamente onde as
coisas estão, e continua — hoje no ChatGPT, amanhã no Claude, sem perder
nada. A conversa vira uma interface temporária sobre um projeto permanente.

Não é um app, um modelo ou uma plataforma. É uma **convenção**: alguns
arquivos com nomes combinados. Se uma pasta segue o padrão, qualquer
ferramenta pode dar suporte.

## Comece em 3 passos

1. Copie o prompt PREP: [Português](prompt/prep.pt-BR.md) · [English](prompt/prep.en.md)
2. Cole nas instruções de um Projeto no ChatGPT ou Claude (qualquer chat
   com acesso ao seu drive na nuvem).
3. Diga *"salva isto como um projeto"*, ou *"abre meu projeto Sourdough"*,
   ou só *"o que eu tenho?"* — e digite a partir daí.

Sem plugin, sem conta, sem backend. É texto e pastas.

## Leia o padrão

- **[SPEC.pt-BR.md](SPEC.pt-BR.md)** — a especificação completa (Português)
- **[SPEC.md](SPEC.md)** — the full specification (English)
- **[example/](example/)** — um projeto real montado no padrão, para ler e
  copiar

## Por que ele se sustenta

| Regra | Por que existe |
|---|---|
| **A memória é o projeto** | Troque de modelo ou dispositivo à vontade; seu trabalho sobrevive a qualquer IA. |
| **Boot leve** | O `MAP` diz o que ler e quando, então a IA nunca varre a pasta inteira — rápido, mesmo anos depois. |
| **Log append-only** | O histórico nunca é reescrito; dá sempre para ver como uma decisão foi tomada. |
| **Verificar antes de "salvo"** | A IA nunca diz que salvou sem ter salvado. Se não consegue escrever, te entrega o texto para você salvar. |
| **Uma raiz, índice recursivo** | Todos os projetos moram numa pasta cujo catálogo é, ele mesmo, um projeto PREP. Ache qualquer coisa por nome, por lista ou por assunto. |
| **Segredos por referência** | O PREP nunca guarda senhas — só *onde* elas moram. Texto puro lido num chat não é lugar para segredo. |

## O que ele não é (por decisão)

Sem criação de apps, sem contas, sem sincronização, sem schemas rígidos,
sem YAML obrigatório. O PREP padroniza **memória de projeto** e nada mais —
pequeno o bastante para entender em cinco minutos. Veja a
[seção de fora de escopo](SPEC.pt-BR.md#11-fora-de-escopo-por-decisão).

## Como se relaciona com o MCP

O Model Context Protocol conecta a IA às suas **ferramentas**. O PREP
conecta a IA ao seu **projeto**. São complementares: o MCP é como a IA
age; o PREP é como um projeto lembra.

## Parte da AMETI

O PREP é a fundação da [AMETI](https://ameti.app) — ferramentas pequenas
que guiam você por uma tarefa de cada vez, sobre os modelos de IA que você
já usa. O AMETI OS é construído sobre este padrão.

## Licença

[CC BY 4.0](LICENSE) — use, adapte e construa sobre ele livremente, com
atribuição. Criado por Rafael Carrer, um kitchen manager em Londres que
constrói as próprias ferramentas.
