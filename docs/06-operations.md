# Operations

Nixe Brain has three operations, each triggered by a specific phrase.

---

## INGEST

**Trigger:** `"Ingest [source]"` or `"Process [source]"`

**What it does:** Reads a raw source and compiles it into the wiki.

**Full workflow:**

1. Identify the operator (multi-user: ask if not clear)
2. Read the source provided
3. Read the INDEX to check for duplicate pages
4. Create a summary page in Archived Responses/
5. Identify entities and concepts → create or update their pages
6. Update the INDEX with new or modified pages
7. Append to the LOG (required format — see below)
8. Report: pages created, pages updated, gaps identified

**What to expect:**

A single source typically touches 5–15 wiki pages. When a page already exists,
Claude enriches it rather than creating a duplicate. Contradictions between the
new source and existing pages are flagged in the "Contradictions or Gaps" section.

**LOG entry format for INGEST:**

```
## [YYYY-MM-DD] | [OPERATOR] | ingest | [source title]

- Pages created: [list]
- Pages updated: [list]
- Gaps identified: [list]
- Notes: [optional free text]
```

---

## CONSULT

**Trigger:** Any substantive question about your domain

**What it does:** Synthesizes an answer from the wiki's compiled knowledge.

**Full workflow:**

1. Identify the operator (multi-user)
2. Read the INDEX to find relevant pages
3. Read relevant pages
4. Synthesize an answer with citations to wiki pages
5. Ask: *"Should I archive this response in the wiki?"*
6. If yes: create page in Archived Responses/, update INDEX and LOG

**Key difference from RAG:** Claude synthesizes from the compiled wiki, not
from raw sources. If the knowledge isn't in the wiki yet, it says so — and
suggests ingesting the relevant sources first.

**LOG entry format for CONSULT:**

```
## [YYYY-MM-DD] | [OPERATOR] | consult | [question summary]

- Pages read: [list]
- Archived: yes / no
- Notes: [optional]
```

---

## LINT

**Trigger:** `"Run lint"` or `"Audit the wiki"`

**What it does:** Checks the wiki for structural problems and coverage gaps.
Reports findings **without making changes** unless explicitly instructed.

**What Claude checks:**

- **Orphan pages** — pages with no connections to other pages
- **Stale information** — pages referencing outdated facts
  (e.g., a project status that has changed)
- **Missing concept pages** — concepts mentioned in pages that don't have
their own dedicated page
- **Missing cross-references** — obvious connections between pages that aren't
linked
- **Coverage gaps by domain** — areas of your work that have little or no
wiki coverage
- **Suggested sources to ingest** — topics that would benefit from new ingestion

**LOG entry format for LINT:**

```
## [YYYY-MM-DD] | [OPERATOR] | lint | Audit

- Orphan pages: [list]
- Stale information: [list]
- Missing concept pages: [list]
- Coverage gaps: [list]
- Suggested ingestions: [list]
```

**Recommended frequency:** Every 10–15 ingestions, or monthly for active wikis.

---

## Operation Rules

- **Never invent:** Claude never fabricates information. If a fact isn't in a
source, it's recorded as a gap — not filled in.
- **Check INDEX first:** Every operation starts by reading the INDEX. This
prevents duplicate pages and keeps the wiki coherent.
- **LOG is immutable:** No LOG entry is ever deleted or edited. The LOG is the
permanent record of what happened.
- **Gaps are explicit:** The "Contradictions or Gaps" section of every page
is the system's honesty layer. If something is unknown, it says so.
