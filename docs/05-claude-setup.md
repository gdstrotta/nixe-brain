# Claude Project Setup

## Step 1 — Create a New Project

1. Open [Claude.ai](https://claude.ai)
2. In the left sidebar, find **Projects** → click **New Project**
3. Name it (e.g., "My Knowledge Base" — same name as your Notion wiki)

## Step 2 — Choose Your Template

| Your situation | Template to use |
|---|---|
| Solo user | [single-user.md](../templates/project-instructions/single-user.md) |
| Team of 2–5 people | [multi-user.md](../templates/project-instructions/multi-user.md) |

For domain-specific calibration, see [examples/](../examples/).

## Step 3 — Paste into Project Instructions

1. Inside your project, look for **Project Instructions** (or **Custom Instructions**)
2. Click to open the instructions field
3. Paste the entire template you chose
4. Do not save yet — you need to replace placeholders first

## Step 4 — Replace All Placeholders

Search for `{{` in the instructions. Every placeholder must be replaced:

| Placeholder | Replace with |
|---|---|
| `{{HOME_ID}}` | Your Notion Home page ID |
| `{{PROTOCOL_ID}}` | Your Notion PROTOCOL page ID |
| `{{INDEX_ID}}` | Your Notion INDEX page ID |
| `{{LOG_ID}}` | Your Notion LOG page ID |
| `{{ENTITIES_ID}}` | Your Notion Entities page ID |
| `{{CONCEPTS_ID}}` | Your Notion Concepts page ID |
| `{{SYNTHESES_ID}}` | Your Notion Syntheses page ID |
| `{{ARCHIVED_ID}}` | Your Notion Archived Responses page ID |
| `{{WIKI_NAME}}` | Your wiki's name |
| `{{DOMAIN}}` | Your domain (e.g., "legal practice", "startup operations") |
| `{{TAGS}}` | Your custom tag list |

For multi-user template, also replace:
| `{{OPERATOR_1_NAME}}` | First team member's name |
| `{{OPERATOR_1_ID}}` | Short ID for LOG (e.g., `JAN`) |
| `{{OPERATOR_2_NAME}}` | Second team member's name |
| `{{OPERATOR_2_ID}}` | Short ID for LOG (e.g., `MAR`) |

## Step 5 — Save and Test

1. Save the project instructions
2. Start a new conversation inside the project
3. Type:

```
Read the INDEX and tell me the current state of the wiki.
```

Claude should access Notion, read the INDEX page, and report back.
If it returns an error, see the [troubleshooting section](03-prerequisites.md#common-issues).

## Step 6 — Run Your First Ingest

Paste any document, article, or text and type:

```
Ingest the content above. Follow the PROTOCOL.
```

Claude will:
1. Ask who is operating (multi-user only)
2. Read the INDEX to check for duplicates
3. Create pages in Notion
4. Update the INDEX
5. Append to the LOG
6. Report what was created, updated, and what gaps were identified

## Tips for Better Results

**Be explicit about sources:** Paste the full text rather than linking to external
pages when possible. Claude reads pasted content more reliably than fetching URLs.

**Identify yourself in multi-user setups:** Start every session with your operator
ID to ensure the LOG is accurate.

**Ingest before consulting:** The more you've ingested, the richer the answers.
Don't expect deep synthesis from an empty wiki.

**Run LINT periodically:** After every 10–15 ingestions, run a LINT to catch
orphan pages, missing connections, and coverage gaps.
