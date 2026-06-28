# Architecture — The Three Layers

Nixe Brain is built on a strict three-layer architecture. Each layer has a distinct
role and a clear ownership model. Mixing these layers is the most common mistake —
understanding them clearly is the foundation for a healthy wiki.

---

## Layer 1 — Raw Sources (Immutable)

**What:** Your original documents. PDFs, articles, meeting transcripts, book notes,
exported conversations, web clips, contracts, research papers — any text you want
the system to learn from.

**Where:** A raw sources folder (Google Drive recommended) that acts as your
intake layer.

**Ownership:** You curate, Claude reads. Claude **never** modifies raw sources.

**Why immutable?** Immutability is a deliberate design choice. It means you can
always re-derive the wiki from scratch if needed. The raw sources are the ground
truth from which everything else is derived.

**Formats that work well:**
- PDF (research papers, books, contracts)
- Plain text / Markdown (articles, notes, web clips)
- Exported chat conversations
- Meeting transcripts

---

## Layer 2 — The Wiki (LLM-Maintained)

**What:** A structured, interlinked collection of Notion pages. Entity pages, concept
pages, syntheses, and archived responses. This is what Claude builds and maintains.

**Where:** Notion — 7 root pages under a single parent.

**Ownership:** Claude writes. You read, navigate, and query.

**The structure:**

```
Your Wiki/
├── ⚙️ PROTOCOL          ← The rules (Layer 3 made visible)
├── 📑 INDEX             ← Navigation map of all pages
├── 📋 LOG              ← Immutable audit trail
├── 📁 Entities/         ← People, organizations, tools, named things
├── 📁 Concepts/         ← Ideas, methods, frameworks, principles
├── 📁 Syntheses/        ← Cross-source analysis
└── 📁 Archived Responses/ ← Valuable answers preserved
```

**Every page follows the same format:**

```
Type: Entity | Concept | Synthesis | Archived Response
Tags: [applicable tags]
Sources: [which raw sources this was derived from]
Created: YYYY-MM-DD | [operator ID]
Updated: YYYY-MM-DD | [operator ID]
Version: N

---

## Definition / Summary

## Main Content

## Connections
- [[Related page 1]] — reason for connection
- [[Related page 2]] — reason for connection

## Contradictions or Gaps
```

---

## Layer 3 — The Schema (The Rules)

**What:** The configuration that tells Claude how to structure the wiki, how to
ingest sources, and how to format responses. This is the brain of the system.

**Where:** Two places simultaneously:
1. **Claude project instructions** (the Project Instructions field in Claude.ai) —
   loaded automatically at the start of every session
2. **⚙️ PROTOCOL page in Notion** — human-readable, visible to any team member
   who opens Notion directly

**Ownership:** You and Claude co-evolve this layer. When conventions change, you
instruct Claude to update the PROTOCOL page, and the LOG records the change.

---

## How the Layers Interact

```
LAYER 1 (Raw Sources)          LAYER 3 (Schema/Rules)
Google Drive                   Claude Project Instructions
     │                                    │
     │ Claude reads                       │ Claude follows
     ▼                                    ▼
                    CLAUDE
                      │
                      │ compiles and maintains
                      ▼
               LAYER 2 (Wiki)
                  Notion
```

**The key invariant:** Information only flows in one direction — from raw sources
into the wiki. The raw sources are never touched. The schema only evolves when you
explicitly instruct it to.

---

## The LOG as Audit Infrastructure

The LOG is the backbone of the audit trail. Every operation Claude performs on
the wiki generates a LOG entry:

```
## [YYYY-MM-DD] | [OPERATOR] | [operation] | [title]

- Pages created: [list]
- Pages updated: [list]
- Gaps identified: [list]
- Notes: [free text]
```

Valid operations: `ingest` | `consult` | `lint` | `update`

The LOG is **append-only**. No entry is ever deleted or modified. This makes it
a reliable audit trail for compliance, team accountability, and system evolution.

---

## Design Principles

**Immutability of sources** — Raw sources are never touched. This is not a
limitation; it is a guarantee. You can always reconstruct the wiki.

**Single author for the wiki** — Claude is the only writer in Layer 2. This
prevents inconsistency and ensures the wiki maintains a coherent structure.

**Explicit contradiction tracking** — The "Contradictions or Gaps" section of
every page is not optional. When sources disagree, the wiki records it. This
makes the system honest.

**Compounding by design** — Every new source updates existing pages, not just
creates new ones. The wiki grows denser, not just larger.
