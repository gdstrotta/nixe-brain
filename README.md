<div align="center">

# 🧠 Nixe Brain

**A compounding knowledge base pattern for Claude + Notion**
*Based on Andrej Karpathy's LLM Wiki — April 2026*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](CHANGELOG.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Pattern: LLM Wiki](https://img.shields.io/badge/pattern-LLM%20Wiki-purple.svg)](docs/01-what-is-llm-wiki.md)

</div>

---

## What is Nixe Brain?

Nixe Brain is an open pattern for building a **persistent, compounding knowledge base**
using [Claude AI](https://claude.ai) and [Notion](https://notion.so), connected via
MCP (Model Context Protocol).

Instead of retrieving from raw documents at query time (RAG), an LLM agent
**compiles and maintains a structured wiki** that grows smarter with each new source.
Every ingestion enriches the entire network — concepts link, contradictions surface,
gaps are tracked automatically.

> *"Obsidian is the IDE. The LLM is the programmer. The wiki is the codebase."*
> — Andrej Karpathy

## Why Not Just Use RAG?

| RAG (standard approach) | Nixe Brain |
|---|---|
| Retrieves from raw docs every query | Pre-compiles sources into structured wiki |
| Nothing accumulates between sessions | Knowledge compounds over time |
| Synthesizing across many docs is expensive | Cross-references built at ingestion time |
| Contradictions go undetected | Contradictions explicitly tracked per page |
| Rediscovers the same knowledge repeatedly | Builds on prior work incrementally |
| Single-user by default | Multi-user with full operator audit trail |

## Prerequisites

- [Claude.ai](https://claude.ai) account (Free or Pro)
- [Notion](https://notion.so) account (Free tier works)
- Notion MCP connected to Claude → [setup guide](docs/03-prerequisites.md)

## Quick Start

**Step 1 — Create the Notion structure**

Create 7 pages in Notion (hierarchy matters):

```
📁 Your Wiki Name/
├── ⚙️ PROTOCOL
├── 📑 INDEX
├── 📋 LOG
├── 📁 Entities/
├── 📁 Concepts/
├── 📁 Syntheses/
└── 📁 Archived Responses/
```

Full instructions: [Notion Setup Guide](docs/04-notion-setup.md)

**Step 2 — Choose your template**

| Template | When to use |
|---|---|
| [Single-user](templates/project-instructions/single-user.md) | Personal knowledge base |
| [Multi-user](templates/project-instructions/multi-user.md) | Team of 2–5 people |

**Step 3 — Configure Claude project**

1. Open [Claude.ai](https://claude.ai) → Create new Project
2. Open Project Instructions
3. Paste your chosen template
4. Replace all `{{PAGE_ID}}` placeholders with your actual Notion page IDs
   ([How to find page IDs](docs/04-notion-setup.md#finding-page-ids))

**Step 4 — Connect Notion MCP**

Claude.ai → Settings → Integrations → Connect Notion → Authenticate

**Step 5 — Ingest your first source**

Inside your Claude project, type:

```
Ingest [paste your source here]. Follow the PROTOCOL.
```

That's it. Your wiki is now live and growing.

## Documentation

| Guide | Description |
|---|---|
| [01 — What is LLM Wiki](docs/01-what-is-llm-wiki.md) | The Karpathy pattern and why it matters |
| [02 — Architecture](docs/02-architecture.md) | The 3-layer design in depth |
| [03 — Prerequisites](docs/03-prerequisites.md) | Accounts, MCP setup, requirements |
| [04 — Notion Setup](docs/04-notion-setup.md) | Building the Notion structure step by step |
| [05 — Claude Setup](docs/05-claude-setup.md) | Configuring your Claude project |
| [06 — Operations](docs/06-operations.md) | INGEST, CONSULT, LINT explained |
| [07 — Multi-user](docs/07-multi-user.md) | Team setup with audit trail |
| [08 — What to Ingest](docs/08-what-to-ingest.md) | Growing your knowledge base |

## Templates

| Template | Description |
|---|---|
| [Single-user instructions](templates/project-instructions/single-user.md) | Project instructions for solo use |
| [Multi-user instructions](templates/project-instructions/multi-user.md) | Project instructions for teams |
| [Notion pages](templates/notion-pages/) | Ready-to-use page content for Notion |

## Examples by Domain

| Domain | Description |
|---|---|
| [Legal](examples/legal/) | Law firms and legal professionals |
| [Startup](examples/startup/) | Startup teams and founders |
| [Research](examples/research/) | Academic and independent researchers |

## How It Works

```
You provide:          Claude compiles:         You get:
─────────────         ─────────────────        ──────────────────
Raw sources     →     Entity pages      →      Answers with citations
(immutable)           Concept pages            Cross-referenced network
                      Syntheses                Contradiction tracking
                      Archived responses       Compounding knowledge
                      LOG entries              Full audit trail
                      INDEX updates
```

## Contributing

Contributions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Acknowledgments

This project implements the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
published by [Andrej Karpathy](https://github.com/karpathy) in April 2026.

## License

MIT — see [LICENSE](LICENSE) for details.

---

<div align="center">
Built on Karpathy's insight · Powered by Claude + Notion
</div>
