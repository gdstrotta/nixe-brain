# Page Format Templates

Reference for all four page types used in the wiki.
Claude uses these formats when creating and updating pages during INGEST operations.

---

## Entity Page

Use for: people, organizations, tools, named products, specific projects

```
**Type:** Entity
**Tags:** [tags]
**Sources:** [raw sources]
**Created:** YYYY-MM-DD | [operator]
**Updated:** YYYY-MM-DD | [operator]
**Version:** 1

---

## Definition / Summary

[2–5 line objective description. What is it, what does it do, why does it matter.]

## Main Content

[Development with subsections as needed. Facts, history, key attributes, current status.]

## Connections
- [[Related entity or concept]] — reason for connection
- [[Another page]] — reason for connection

## Contradictions or Gaps

[Source conflicts, open questions, what needs investigation. Leave empty if none.]
```

---

## Concept Page

Use for: ideas, methods, frameworks, principles, patterns, processes

```
**Type:** Concept
**Tags:** [tags]
**Sources:** [raw sources]
**Created:** YYYY-MM-DD | [operator]
**Updated:** YYYY-MM-DD | [operator]
**Version:** 1

---

## Definition / Summary

[2–5 line definition. What is this concept, where does it apply, what does it enable.]

## Main Content

### Description
[Full explanation of the concept.]

### How It's Applied
[How this concept is actually used in the domain.]

### Examples
[Concrete examples from ingested sources.]

## Connections
- [[Related concept]] — how they relate
- [[Entity that uses this concept]] — usage context

## Contradictions or Gaps

[Competing definitions, known limitations, what remains unclear.]
```

---

## Synthesis Page

Use for: cross-source analysis, comparative views, integrated knowledge

```
**Type:** Synthesis
**Tags:** [tags]
**Sources:** [all raw sources synthesized]
**Created:** YYYY-MM-DD | [operator]
**Updated:** YYYY-MM-DD | [operator]
**Version:** 1

---

## Definition / Summary

[What this synthesis covers and what question it answers.]

## Main Content

[The synthesized analysis. Can use subsections, comparisons, timelines as needed.
Always attribute claims to their source pages.]

## Connections
- [[Entity pages synthesized]]
- [[Concept pages applied]]

## Contradictions or Gaps

[Where sources disagree. What was deliberately excluded. What would improve this synthesis.]
```

---

## Archived Response Page

Use for: valuable answers to consultations, preserved for future reference

```
**Type:** Archived Response
**Tags:** [tags]
**Sources:** [wiki pages consulted to produce this answer]
**Created:** YYYY-MM-DD | [operator]
**Updated:** YYYY-MM-DD | [operator]
**Version:** 1

---

## Question

[The original question that prompted this response.]

## Response

[The full answer, with citations to wiki pages.]

## Connections
- [[Wiki pages cited in this response]]

## Contradictions or Gaps

[Caveats, limitations, what was unknown at the time of this response.]
```
