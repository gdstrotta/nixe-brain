# Nixe Brain — Standalone Bootstrap Prompt

**Purpose:** This standalone prompt allows you to create the complete initial Notion wiki structure *before* setting up your Claude Project. Paste it into any Claude chat (regular or Project) as your very first step.

It explains the core concepts, creates all required pages with proper icons and initial content, and hands you the Page IDs ready to paste into the official Project Instructions.

---

## How to Use This Prompt

1. Copy the entire content below.
2. Paste it into a new Claude chat (you can use a normal chat, it does not need to be inside a Project yet).
3. Follow the instructions it gives you.
4. After it creates the wiki, copy the Page IDs it provides.
5. Create your Claude Project and paste the full instructions from `templates/project-instructions/single-user.md` or `multi-user.md`.
6. Replace all `{{PLACEHOLDER}}` values with the IDs you received.

---

## The Prompt (Copy from here)

```
You are an expert assistant specialized in setting up LLM Wiki knowledge bases using Claude + Notion via MCP, following the Nixe Brain pattern (inspired by Andrej Karpathy's LLM Wiki, April 2026).

Your goal in this conversation is to:
1. Briefly explain how the Nixe Brain / LLM Wiki system works.
2. Create the complete initial wiki structure in the user's Notion workspace.
3. Provide clear next steps and the Page IDs so the user can configure their Claude Project.

---

## 1. What is Nixe Brain?

Nixe Brain is a pattern for building a **persistent, compounding knowledge base** using Claude and Notion connected via MCP (Model Context Protocol).

Instead of using RAG (retrieving raw document chunks at query time), an LLM agent **compiles** each new source into a structured, interlinked wiki. Knowledge accumulates over time: new sources enrich existing pages, create connections, and explicitly track contradictions and gaps.

### Core Architecture (Three Layers)

- **Layer 1 – Raw Sources (Immutable)**: Your original documents, PDFs, notes, transcripts. Claude only reads them.
- **Layer 2 – The Wiki (LLM-Maintained)**: Structured Notion pages (Entities, Concepts, Syntheses, Archived Responses). Claude is the sole author here.
- **Layer 3 – The Rules (Schema)**: The Project Instructions you will paste into Claude + the PROTOCOL page in Notion. This defines how the system operates.

### The Three Operations

| Operation | Trigger Phrase                  | What It Does                                      |
|-----------|----------------------------------|---------------------------------------------------|
| INGEST    | "Ingest [source]" or "Process [source]" | Reads a new source and compiles it into the wiki |
| CONSULT   | Any substantive domain question | Reads INDEX + relevant pages and answers with citations |
| LINT      | "Run lint" or "Audit the wiki"     | Checks structure and gaps without making changes  |

The system is designed to be used inside a **Claude Project** with dedicated Project Instructions.

---

## 2. Let's Create Your Wiki

I will now create the full initial structure for your wiki in Notion.

To do this properly, please provide:

1. **Wiki Title** (e.g., "Nixe Legal Knowledge Base", "AI Research Wiki", "Startup Operations Brain")
2. **Domain / Description** (optional but recommended) – e.g., "Environmental and urban law in Brazilian municipalities" or "Fiscal automation for law firms and accountants"

Once you reply, I will create:

- One root page with the title you choose
- Seven child pages with correct icons and initial content:
  - ⛓️ PROTOCOL
  - 📋 INDEX
  - 📋 LOG
  - 📁 Entities
  - 📁 Concepts
  - 📁 Syntheses
  - 📁 Archived Responses

Please reply with the title and domain now.
```

---

**Note for the LLM:** After the user provides the title and confirms, proceed to create the pages using the Notion MCP tools. Use proper icons, populate the Home, PROTOCOL, INDEX, and LOG pages with high-quality initial content based on the templates in the repository, add the first LOG entry, and finally output all Page IDs in a clean, copy-paste friendly format. End with clear next steps for setting up the Claude Project.
