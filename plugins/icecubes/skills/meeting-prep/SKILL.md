---
name: meeting-prep
description: Prepare for an upcoming meeting by analyzing past meetings with the same participants. Use when asked to prep for a meeting, review meeting history with someone, or get ready for a call.
---

# Meeting Prep

The user wants to prepare for a meeting. Use IceCubes MCP tools to research past interactions.

**Input**: $ARGUMENTS (participant name, email, or company name)

## Steps

1. **Find past meetings** — Use `get_meetings` with the participant email or keyword to find all previous meetings involving the specified person or company. Try `search_meetings` if the initial results are limited.

2. **Gather details** — For the most recent 3-5 relevant meetings, use `get_meeting` to pull summaries, key points, and action items.

3. **Check outstanding action items** — Use `get_action_items` to find any open items related to these meetings.

4. **Pull insights** — For sales-relevant meetings, use `get_insights` to get MEDDIC fields, objections, competitor mentions, and sentiment.

## Output Format

Present a concise meeting prep brief:

### Meeting Prep: [Person/Company]

**Relationship Summary**
- Number of past meetings, date range, key participants

**Recent Meeting Highlights**
- Last 2-3 meetings with key decisions and outcomes

**Outstanding Action Items**
- Open items assigned to you or the other party

**Key Context**
- Budget/pricing discussions, timeline commitments, objections raised
- Competitor mentions, decision criteria, champion identification

**Suggested Talking Points**
- 3-5 specific points based on past discussion history
