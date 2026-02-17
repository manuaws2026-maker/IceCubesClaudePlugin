---
name: search
description: Search across all meeting transcripts, summaries, action items, and notes. Use when the user wants to find a specific quote, topic, discussion, or decision from their meetings.
---

# Meeting Search

The user wants to find something across their meetings.

**Input**: $ARGUMENTS (search query)

## Steps

1. **Search** — Use `search_meetings` with the user's query. If the query mentions a specific type (transcript, summary, action item, note), pass the appropriate `content_type` filter. If a speaker is mentioned, use the `speaker` filter.

2. **Expand results** — For the most relevant 2-3 results, use `get_meeting` to pull the full meeting context (title, date, participants, summary).

3. **Get exact quotes** — If the user needs exact wording, use `get_transcript` on the relevant meeting to find the precise quote with speaker attribution and timestamp.

## Output Format

Present results organized by relevance:

### Search Results: "[query]"

For each match:
- **Meeting**: [Title] — [Date]
- **Context**: [Who said it / where it appears]
- **Excerpt**: The relevant text with key terms highlighted
- **Full context**: Brief summary of the surrounding discussion

If multiple meetings match, group them chronologically and note patterns across meetings.
