---
name: action-items
description: Review, create, or manage action items from meetings. Use when asked about follow-ups, tasks, to-dos, or action items from meetings.
---

# Action Items

The user wants to work with action items from their meetings.

**Input**: $ARGUMENTS (optional — meeting name, "open", "overdue", or a new action item to create)

## Steps

### Reviewing action items
1. Use `get_action_items` to fetch items. Filter by `completed: false` for open items.
2. If a specific meeting is mentioned, first use `get_meetings` with keyword to find the meeting ID, then filter action items by `meeting_id`.
3. Group items by meeting and highlight any with past due dates.

### Creating action items
1. Find the meeting using `get_meetings` with keyword search.
2. Use `create_action_item` with the meeting_id, text, and optional assignee_email and due_date.
3. Confirm creation with the item details.

### Updating action items
1. Use `get_action_items` to find the item.
2. Use `update_action_item` to mark complete or update text.

## Output Format

### Open Action Items

For each item:
- [ ] **[Action text]**
  - From: [Meeting title] ([date])
  - Assigned to: [name/email]
  - Due: [date] [OVERDUE badge if past due]

**Summary**: X open items across Y meetings. Z are overdue.
