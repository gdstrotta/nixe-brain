# Prerequisites

## What You Need

### 1. Claude.ai Account

Any plan works, but consider:

| Plan | Suitable for |
|---|---|
| Free | Getting started, light use |
| Pro ($20/month) | Regular use, higher message limits |
| Team ($25+/seat/month) | Shared projects across 5+ people |

For teams smaller than 5: use individual Pro accounts pointing at the same Notion
workspace. The wiki is the shared memory — Claude is just the interface.

### 2. Notion Account

The free tier is sufficient for most wikis. Notion Plus ($10/month) adds version
history and larger file uploads if needed.

### 3. Notion MCP Connection

This is the bridge that lets Claude read and write to your Notion pages.

**Steps to connect:**

1. Open [Claude.ai](https://claude.ai)
2. Click your profile icon (bottom left) → **Settings**
3. Go to **Integrations** (may also appear as Connectors or Tools)
4. Find **Notion** → click **Connect**
5. A Notion authorization window opens
6. Click **Allow access**
7. Select the workspace where your wiki will live
8. Confirm

**Verify the connection works:**

In any Claude conversation, type:
```
Search Notion for "test"
```
If Claude returns results (even "no results found"), the connection is active.

### 4. Google Drive (Optional but Recommended)

For storing raw sources (Layer 1). Any cloud storage works, but Google Drive
integrates well if you also connect its MCP.

---

## Common Issues

**"Object not found" errors when Claude tries to access a Notion page**

This means the Notion integration doesn't have explicit permission to that page.
Fix: Open the page in Notion → click `···` (top right) → **Connections** →
select your Claude/Notion integration. Repeat for each root page.

**Claude says it can't find the wiki**

Check that the page IDs in your project instructions match the actual IDs of your
Notion pages. IDs change if you duplicate a page. Re-fetch the IDs from the page
URLs.

**Multi-user: one operator's changes aren't visible to others**

All operators must be connected to the same Notion workspace. The Notion integration
authenticates per user — make sure each team member connects their own Notion account
(which has access to the shared workspace) through their own Claude settings.
