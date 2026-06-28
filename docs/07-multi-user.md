# Multi-User Setup

Nixe Brain supports teams of 2–5 people operating the same wiki. The shared
memory lives in Notion — each team member has their own Claude account pointing
at the same Notion workspace.

## Architecture for Teams

```
Team Member A               Team Member B               Team Member C
(own Claude account)        (own Claude account)        (own Claude account)
        │                           │                           │
        │ Notion MCP                │ Notion MCP                │ Notion MCP
        └───────────────────────────┼───────────────────────────┘
                                    │
                             Shared Notion
                              Workspace
                            (single source
                              of truth)
```

The wiki is the shared memory. Claude is just the interface.

## Step 1 — Notion Sharing

The wiki owner (whoever created the Notion pages) must share them with team members:

1. Open the root wiki page in Notion
2. Click **Share** (top right)
3. Type each team member's email address
4. Set permission to **Full access**
5. Send invitation
6. Team members accept via email and join the workspace

> Child pages inherit access from the root page. One share operation covers all
> 7 subpages.

## Step 2 — Each Member Connects Notion MCP

Each team member independently:
1. Opens Claude.ai
2. Goes to Settings → Integrations → Connect Notion
3. Authenticates with their own Notion account
4. Selects the shared workspace

## Step 3 — Each Member Creates Their Own Claude Project

Each team member:
1. Creates a new Claude project
2. Pastes the [multi-user template](../templates/project-instructions/multi-user.md)
3. Replaces all `{{PLACEHOLDER}}` values with the **same Notion page IDs**
   (provided by the wiki owner)
4. Adds their own operator ID to the operators table

## Operator IDs

Each team member has a short, unique ID used in the LOG. This is what makes the
audit trail work.

**Choosing good operator IDs:**
- 2–4 characters, uppercase
- Usually initials: `JAN`, `MAR`, `ALE`
- Consistent across all sessions — never change your ID once set

**LOG audit by operator:**
To see everything a specific operator did, search the LOG page for their ID:
`| JAN |` shows all entries where JAN was the operator.

## Step 4 — Identify Yourself Each Session

At the start of every session, state your operator ID:

```
I'm [OPERATOR_ID]. Read the INDEX and tell me what's in the wiki.
```

This ensures the LOG accurately tracks who did what.

## Conflict Resolution

If two operators ingest conflicting information:
- Both ingestions are recorded in the LOG with their respective operator IDs
- The "Contradictions or Gaps" section of affected pages flags the conflict
- The team resolves which source takes precedence and instructs Claude to update

**The LOG is always the tiebreaker** — it shows exactly who ingested what and when.

## Recommended Team Conventions

- Designate one person to run LINT (prevents duplicate audit entries)
- Agree on a naming convention before the first ingestion
- Share the PROTOCOL page URL with all team members so everyone can read the rules
  directly in Notion, without needing Claude
