> **This document defines how Claude operates the wiki. Any operator should read
> this before starting a maintenance session.**

---

## 1. Architecture — Three Layers (Karpathy Pattern, 2026)

- **Layer 1 — Raw Sources (immutable):** Original documents. Claude reads; never modifies.
- **Layer 2 — The Wiki (LLM-maintained):** Pages in Notion. Claude is the sole author.
- **Layer 3 — This protocol (the rules):** Defines conventions, formats, and workflows.

**Golden rule:** Never modify or create files in raw sources. All writing
occurs exclusively in the wiki.

---

## 2. Knowledge Domain

> *(Describe what this wiki covers — replace this with your domain description)*

---

## 3. Wiki Structure

```
{{WIKI_NAME}}/
├── ⚙️ PROTOCOL              ← this file
├── 📑 INDEX                 ← catalog of all pages
├── 📋 LOG                   ← immutable operations record
├── Entities/                ← people, orgs, tools, named things
├── Concepts/                ← ideas, methods, frameworks, principles
├── Syntheses/                ← cross-source analysis
└── Archived Responses/      ← preserved consultation answers
```

---

## 4. Operators

| Operator | Role | LOG ID |
|---|---|---|
| *(add team members here)* | | |

**Identification rule:** Ask at the start of each session if it is not clear
who is operating. Record operator ID in every LOG entry and page metadata.

---

## 5. Page Format

```
**Type:** Entity | Concept | Synthesis | Archived Response
**Tags:** [tags]
**Sources:** [raw sources]
**Created:** YYYY-MM-DD | [operator]
**Updated:** YYYY-MM-DD | [operator]
**Version:** N

---

## Definition / Summary

## Main Content

## Connections

## Contradictions or Gaps
```

---

## 6. Operations

### INGEST — trigger: "Ingest [source]"
1. Identify operator
2. Read source
3. Read INDEX (check duplicates)
4. Create summary in Archived Responses/
5. Create/update entity and concept pages
6. Update INDEX
7. Append to LOG
8. Report

### CONSULT — trigger: substantive question
1. Identify operator
2. Read INDEX
3. Read relevant pages
4. Synthesize with citations
5. Offer to archive
6. If yes: create page, update INDEX and LOG

### LINT — trigger: "Run lint"
Check and report without fixing:
- Orphan pages
- Stale information
- Missing concept pages
- Missing cross-references
- Coverage gaps
- Suggested ingestions

---

## 7. LOG Format

```
## [YYYY-MM-DD] | [OPERATOR] | [operation] | [title]

- Pages created: [list]
- Pages updated: [list]
- Gaps identified: [list]
- Notes: [text]
```

Operations: `ingest` | `consult` | `lint` | `update`

---

## 8. Naming Conventions

| Type | Format |
|---|---|---|
| Person | Full name + role |
| Organization | Official name + acronym |
| Framework | Name + short label |
| Document | `[Type] — [Title] — [YYYY-MM]` |

---

## 9. Tags

*(Define your domain-specific tags here)*

---

## 10. What NOT to Do

- Do not write to raw sources
- Do not duplicate pages — check INDEX first
- Do not leave pages without connections when obvious relations exist
- Do not invent information — record as a gap
- Do not delete LOG entries
- Do not answer consultations without reading INDEX first
- Do not perform operations without identifying the operator

---

## 11. Protocol Evolution

This document co-evolves with the wiki. When a convention changes, the operator
instructs Claude to update this page. Every protocol update generates a LOG entry:

`## [YYYY-MM-DD] | [ID] | update | Protocol — [description of change]`

---

*Version 1.0 — {{DATE}}*
*Based on the LLM Wiki pattern (Karpathy, 2026)*
