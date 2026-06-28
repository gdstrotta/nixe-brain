# What to Ingest — Growing Your Knowledge Base

## The Core Principle

The wiki is only as good as what you feed it. The best sources are:
1. **Specific** — about real entities and concepts in your domain
2. **Authoritative** — primary sources over summaries of summaries
3. **Yours** — documents you've actually created or worked with, not generic content
4. **Actionable** — things you'll actually query about later

## Ingestion Priority Order

**Tier 1 — Ingest immediately (highest return)**

Your own documents: meeting notes, decisions, proposals, analyses you've written.
These generate the most specific, useful wiki content because they reflect your
actual work context.

**Tier 2 — Ingest early (foundational knowledge)**

Core reference material for your domain: anchor legislation, key frameworks,
foundational papers, methodologies you use regularly.

**Tier 3 — Ingest progressively (deepening coverage)**

Articles, reports, case studies, secondary references. These enrich existing pages
rather than creating foundational ones.

**Tier 4 — Avoid or use sparingly**

Generic content, Wikipedia articles, broad introductory texts. These create noise
more than signal in a specialized wiki.

## Reducing Before Ingesting

A key principle: **reduce the universe before processing with AI**.

Don't give Claude 50 documents and ask it to find the relevant parts.
Instead: you curate the 5 most relevant documents, Claude compiles them deeply.

Example:
- ❌ "Ingest everything about topic X from this 200-page report"
- ✅ "Here are the 3 sections of this report relevant to X — ingest them"

## Source Formats That Work Well

| Format | Notes |
|---|---|
| Plain text / Markdown | Best — Claude reads natively |
| Pasted content | Excellent — reliable and fast |
| PDF text (copy-paste) | Good — works for most PDFs |
| Meeting notes | Excellent — very high signal per page |
| Email threads | Good — but clean up irrelevant parts first |
| Exported chat conversations | Good — especially strategy conversations |

## Growing the Wiki Strategically

**Start with entities** — ingest the documents that define your core people, organizations,
clients, and tools first. Everything else will reference these.

**Then ingest concepts** — frameworks, methodologies, principles. These become the
conceptual spine that connects entities.

**Then ingest syntheses** — documents that analyze and compare multiple entities or
concepts. These generate the richest cross-references.

**Run LINT after every 10–15 ingestions** — it reveals what's missing and what to
ingest next.

## Signs Your Wiki is Maturing

- A consultation returns answers that cite 3+ different wiki pages
- New ingestions update existing pages more than they create new ones
- LINT finds fewer orphan pages each time
- You ask a question you haven't thought about in months, and the wiki answers correctly
