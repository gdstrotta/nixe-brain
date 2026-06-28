# Notion Setup Guide

## Step 1 — Create the Wiki Root Page

1. Open Notion
2. Click `+ New page` in the sidebar
3. Give it a name (e.g., "My Knowledge Base" or any name you prefer)
4. This is your wiki root — everything else lives inside it

## Step 2 — Create the 7 Child Pages

Inside your root page, create these 7 pages **in this exact order**
(click `+` inside the root page to add subpages):

| Icon | Name | Purpose |
|---|---|---|
| ⚙️ | `PROTOCOL` | Operational rules — how Claude maintains the wiki |
| 📑 | `INDEX` | Navigation map of all wiki pages |
| 📋 | `LOG` | Immutable audit trail of all operations |
| 📁 | `Entities` | People, organizations, tools, named things |
| 📁 | `Concepts` | Ideas, methods, frameworks, principles |
| 📁 | `Syntheses` | Cross-source analysis and integrated views |
| 📁 | `Archived Responses` | Valuable answers preserved from consultations |

## Step 3 — Populate Pages with Templates

For each page, paste the corresponding template from the
[templates/notion-pages/](../templates/notion-pages/) folder:

- `PROTOCOL` → paste content from `protocol.md`
- `INDEX` → paste content from `index.md`
- `LOG` → paste content from `log.md`
- `Home` (root page) → paste content from `home.md`
- `Entities`, `Concepts`, `Syntheses`, `Archived Responses` → leave empty
  (Claude will populate them during INGEST operations)

## Step 4 — Grant MCP Access to Pages

For Claude to read and write to your pages, the Notion integration must have
explicit access:

1. Open each of the 7 pages (and the root page) in Notion
2. Click `···` in the top right corner
3. Select **Connections** (or **Add connections**)
4. Find and select your Claude/Notion integration
5. Repeat for all 8 pages (root + 7 children)

> **Pro tip:** If you grant access at the root page level and the integration
> supports inheritance, child pages may inherit access automatically. Test this
> before granting access to each page individually.

## Step 5 — Find Your Page IDs {#finding-page-ids}

Each Notion page has a unique ID that Claude uses to access it directly (faster
and more reliable than searching by name).

**How to find a page ID:**

1. Open the page in Notion
2. Click **Share** → **Copy link** (or just copy the URL from your browser)
3. The URL looks like: `https://notion.so/workspace/Page-Title-abc123def456`
4. The ID is the last 32 characters after the final `-`: `abc123def456...`
5. Format it with dashes as a UUID: `abc12345-6789-abcd-ef01-234567890abc`

**Collect IDs for all 8 pages:**

| Page | Your ID |
|---|---|
| Root (Home) | `{{YOUR_HOME_ID}}` |
| PROTOCOL | `{{YOUR_PROTOCOL_ID}}` |
| INDEX | `{{YOUR_INDEX_ID}}` |
| LOG | `{{YOUR_LOG_ID}}` |
| Entities | `{{YOUR_ENTITIES_ID}}` |
| Concepts | `{{YOUR_CONCEPTS_ID}}` |
| Syntheses | `{{YOUR_SYNTHESES_ID}}` |
| Archived Responses | `{{YOUR_ARCHIVED_ID}}` |

Keep these IDs — you'll paste them into your Claude project instructions.

## Step 6 — Verify Structure

Your Notion sidebar should look like this:

```
📁 My Knowledge Base (root)
├── ⚙️ PROTOCOL
├── 📑 INDEX
├── 📋 LOG
├── 📁 Entities
├── 📁 Concepts
├── 📁 Syntheses
└── 📁 Archived Responses
```

You're ready for [Claude Setup](05-claude-setup.md).
