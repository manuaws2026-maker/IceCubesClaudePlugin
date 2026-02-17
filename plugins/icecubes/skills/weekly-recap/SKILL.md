---
name: weekly-recap
description: Generate a weekly summary of all meetings, key decisions, and action items. Use when asked for a weekly recap, weekly summary, or end-of-week review.
---

# Weekly Recap

The user wants a summary of their meetings from the past week.

**Input**: $ARGUMENTS (optional — "this week", "last week", or a specific date range)

## Steps

1. **Determine date range** — Default to the current week (Monday to today). If "last week" is specified, use the previous Monday to Friday. Parse any specific dates mentioned.

2. **Fetch meetings** — Use `get_meetings` with `from_date` and `to_date` for the date range. Set `limit: 50` to capture all meetings.

3. **Get details** — For each meeting, use `get_meeting` to pull summaries and action items. Batch the most important meetings (by participant count or duration).

4. **Get open action items** — Use `get_action_items` with `completed: false` to find outstanding follow-ups.

## Output Format

### Weekly Recap: [Date Range]

**Overview**: X meetings, Y total hours, Z action items generated

**Day-by-Day**

For each day with meetings:
#### [Day, Date]
- **[Meeting Title]** ([duration], [participants])
  - Key decisions: [1-2 sentences]
  - Action items: [count] new

**Key Decisions This Week**
- Bulleted list of the most important decisions across all meetings

**Open Action Items**
- Grouped by priority/meeting

**Highlights**
- Notable patterns, frequently discussed topics, or items needing attention
