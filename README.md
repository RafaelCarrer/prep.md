# PREP.md

> **Prepare once. Continue anywhere.**
> Project memory for any AI — prepare a folder once, and any AI picks up exactly where you left off.

![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-green)
![Works with](https://img.shields.io/badge/works%20with-ChatGPT%20·%20Claude%20·%20Gemini-blue)
![Standard](https://img.shields.io/badge/PREP-v0.3-orange)

**Home: [prep.md](https://prep.md)**

---

## The problem

Every AI keeps its own memory in its own way. A long ChatGPT conversation
grows heavy and starts to forget. Switch to Claude or Gemini and you start
over from nothing. The knowledge you built lives trapped inside one chat,
in one product, and vanishes when the tab closes.

## The idea

**PREP flips it: the memory belongs to the project, not to the AI.**

A project is just a folder in your cloud drive, arranged in a small,
predictable way:

```
Sunday Sourdough/
├── PREP.md      ← the entry point: what this is, where it stands, what to read
├── LOG.md       ← append-only history, one dated line per session
└── memory/      ← a full snapshot of each session
```

Any AI that can read the folder opens the project, sees exactly where
things stand, and continues — today in ChatGPT, tomorrow in Claude,
without losing a thing. The conversation becomes a temporary interface
over a permanent project.

It is not an app, a model, or a platform. It is a **convention**: a few
files with agreed names. If a folder follows it, any tool can support it.

## Quick start

The easiest way is **[PREP Save](https://save.prep.md)** — the reference
implementation. Work in any AI, paste the conversation's summary into PREP
Save, and it writes a verified snapshot into a project folder in your own
Google Drive. To pick the project back up later, tell any AI:

```
In your Google Drive, open the «project» folder inside PREP
and read PREP.md.
```

That open instruction is the standard's one required piece of user-facing
syntax. No plugin, no account with us, no backend — it's text and folders
in your own drive.

By hand: download the [starter folder](https://prep.md), drop it into your
cloud drive, and you're set. Prefer to run PREP inside a chat that can
write files? Paste **[prompt/prep.en.md](prompt/prep.en.md)** into a
Project's instructions in ChatGPT or Claude — an optional, prompt-based
way to drive the same flows with a small `prep …` command set.

PREP never nags you to save — you converse freely and save when you want.

## Read the standard

- **[SPEC.md](SPEC.md)** — the full specification
- **[example/](example/)** — a real project built in the standard, to read
  and copy

## Why it holds up

| Rule | Why it exists |
|---|---|
| **The memory is the project** | Switch models or devices freely; your work outlives any single AI. |
| **Boot light** | The `MAP` says what to read and when, so an AI never scans the whole folder — fast, even years in. |
| **Append-only log** | History is never rewritten; you can always see how a decision was made. |
| **Verify before "saved"** | An AI never claims it saved when it didn't. If it can't write, it hands you the text to save yourself. |
| **One root, recursive index** | All projects live in one folder whose catalogue is itself a PREP project. Find anything by name, by listing, or by topic. |
| **Secrets by reference** | PREP never stores passwords — only *where* they live. Plain text read into a chat is no place for a secret. |

## What it is not (by design)

No accounts, no sync, no rigid schemas, no required YAML. PREP standardises
**project memory** and nothing more — small enough to understand in five
minutes. Tools are built *on* the standard, not baked into it:
[PREP Save](https://save.prep.md) is the reference implementation, and the
folder is the contract for any other. See the
[out-of-scope section](SPEC.md#11-out-of-scope-by-design).

## How it relates to AGENTS.md and MCP

- **AGENTS.md** tells agents how to work in your *code*. **PREP tells them
  everything about your *project*** — the goal, the state, the history,
  the decisions. Different lane: work and life projects, not just
  codebases.
- **MCP** connects an AI to your *tools*. **PREP** connects an AI to your
  *project*. MCP is how an AI acts; PREP is how a project remembers. An
  optional `TOOLS.md` even lets a project list the MCP servers its agents
  can use.

## Part of AMETI

PREP is the foundation of [AMETI](https://ameti.app) — small tools that
guide you through one job at a time, over the AI models you already use.
The AMETI OS is built on this standard.

## Contributing

Translations are welcome via pull request. Questions and ideas: open a
[Discussion](https://github.com/RafaelCarrer/prep.md/discussions).

## License

[CC BY 4.0](LICENSE) — use, adapt, and build on it freely, with
attribution. Created by Rafael Carrer, a kitchen manager in London who
builds his own tools.
