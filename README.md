# IceCubes Plugin for Claude Code

Meeting intelligence for Claude Code. Search transcripts, track action items, prep for meetings, and analyze deals — all from your IceCubes meeting data.

## Quick Install

### Option 1: Marketplace (recommended)

```bash
# In Claude Code:
/plugin marketplace add manuaws2026-maker/IceCubesClaudePlugin
/plugin install icecubes@icecubes-marketplace
```

### Option 2: One-line install

```bash
curl -sSL https://icecubes.app/api/plugin/install | bash
```

Then start Claude Code with:

```bash
claude --plugin-dir ~/.claude/plugins/icecubes
```

## Prerequisites

1. **Claude Code** — Install from [claude.ai/claude-code](https://claude.ai/claude-code) (version 1.0.33 or later)
2. **An IceCubes account** — Sign up at [icecubes.app](https://icecubes.app) if you don't have one

On first use, Claude Code will open your browser to sign in to IceCubes via OAuth. After you approve access, the plugin is ready — no API key or environment variable needed.

### Alternative: API Key Authentication

If you prefer not to use the browser-based OAuth flow, you can authenticate with an API key instead. Create one from [Settings > Developer](https://icecubes.app/settings?section=developer), then add the MCP server manually:

```bash
claude mcp add --transport http icecubes https://icecubes.app/api/mcp \
  --header "Authorization: Bearer ik_your_key_here"
```

## Slash Commands

| Command | Description |
|---------|-------------|
| `/icecubes:meeting-prep <person or company>` | Prepare for a meeting by reviewing past interactions |
| `/icecubes:search <query>` | Search across all transcripts, summaries, and notes |
| `/icecubes:action-items` | Review open action items across meetings |
| `/icecubes:weekly-recap` | Summarize this week's meetings and decisions |
| `/icecubes:deal-review <company>` | Full deal analysis with MEDDIC, timeline, and risks |

## MCP Tools

The plugin connects to IceCubes' MCP server, exposing these tools:

- `get_user` — Your profile and meeting stats
- `get_meetings` — List/filter meetings by date, keyword, participant, tag, or CRM deal/opportunity
- `get_meeting` — Full meeting details with summary and action items
- `get_transcript` — Complete transcript with speaker labels and timestamps
- `search_meetings` — Full-text search across all meeting content
- `get_insights` — Sales insights (MEDDIC, objections, competitors, sentiment)
- `get_action_items` — Action items across meetings
- `create_action_item` — Create a new action item
- `update_action_item` — Update or complete an action item
- `get_notes` — Meeting notes
- `update_notes` — Update meeting notes
- `get_contacts` — Contacts from your meetings
- `get_tags` — Available tags (org and personal)

## Examples

```
> /icecubes:meeting-prep sarah@pinnacle.com
# Returns a prep brief with past meeting history, open action items, and suggested talking points

> /icecubes:search "budget approval"
# Finds every mention of budget approval across all your meetings

> /icecubes:deal-review Pinnacle Corp
# Full MEDDIC analysis, timeline, objections, and recommended next steps

> /icecubes:weekly-recap last week
# Summary of all meetings, decisions, and new action items from last week
```

## Documentation

Full documentation: [IceCubes Claude Code Plugin Docs](https://icecubes.app/docs/integrations/claude-code)

## License

MIT
