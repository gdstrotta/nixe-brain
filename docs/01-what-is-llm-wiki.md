# What is the LLM Wiki Pattern?

## The Problem with RAG

Most AI knowledge systems today work like this:

1. You upload documents
2. The system indexes them (chunks + vectors)
3. At query time, relevant chunks are retrieved
4. The LLM synthesizes an answer

This works, but it has a fundamental flaw: **nothing accumulates**.

Ask a question that requires synthesizing five documents and the LLM finds and
pieces together the relevant fragments — from scratch, every single time. Ask the
same question tomorrow and it repeats the entire process. There is no memory, no
compounding, no learning from previous synthesis work.

## Karpathy's Insight

In April 2026, Andrej Karpathy (OpenAI co-founder, former Tesla AI Director)
published a pattern that reframes the problem. He called it the **LLM Wiki**.

The key shift: instead of indexing documents for retrieval, **an LLM agent reads
each new source and integrates it into a structured, interlinked wiki**.

The analogy he uses is from software engineering: **compilation**.

When you write source code, a compiler transforms it into an optimized artifact once.
You don't recompile from source every time you run the program. The compilation is
expensive, but it pays for itself across every subsequent use.

The LLM Wiki applies this to knowledge:

```
RAG:          source → [index] → retrieve at query time → answer
LLM Wiki:     source → [compile into wiki once] → query the wiki → answer
```

## What Gets Built

Every source you ingest gets compiled into:

- **Entity pages** — one page per person, organization, tool, or named thing
- **Concept pages** — one page per idea, method, framework, or principle
- **Synthesis pages** — cross-source analysis and integrated views
- **Archived responses** — valuable answers preserved for future reference

Each page contains:
- A definition/summary
- The main content
- **Cross-references** to related pages
- **Source provenance** (what was this derived from?)
- **Contradictions and gaps** explicitly tracked

## Why It Compounds

The power of the wiki pattern is that each new source doesn't just add a new page —
it enriches every relevant existing page. A new document about a topic you've already
ingested updates the existing pages, adds new connections, and flags any contradictions
with prior knowledge.

After 20–30 sources, asking a complex question doesn't require the LLM to reconstruct
knowledge from scratch. It reads the already-compiled wiki — structured, linked,
contradiction-aware — and synthesizes from a distilled view of everything you've fed
the system.

Karpathy's own research wiki on a single topic grew to approximately 100 articles and
400,000 words. At that scale, the system was still faster and more accurate than RAG
for his research use case.

## What Nixe Brain Adds

Nixe Brain implements this pattern with:

- **Notion as the wiki backend** (instead of local markdown files)
- **Claude via MCP** as the LLM agent that maintains the wiki
- **Structured templates** ready to copy and use
- **Multi-user support** with a full operator audit trail
- **Three operations** (INGEST, CONSULT, LINT) with clear triggers
- **Domain-specific examples** for Legal, Startup, and Research verticals

## Further Reading

- [Karpathy's original LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [Architecture deep dive](02-architecture.md)
- [What to ingest](08-what-to-ingest.md)
