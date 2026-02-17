---
name: deal-review
description: Analyze a deal or account by reviewing all meetings with a company. Use when asked to review a deal, analyze an account, or assess pipeline health for a specific company.
---

# Deal Review

The user wants a comprehensive review of a deal or account.

**Input**: $ARGUMENTS (company name, deal name, or contact name)

## Steps

1. **Find all related meetings** — Use `get_meetings` with keyword matching the company/deal name. Also use `search_meetings` to find mentions in transcripts and summaries.

2. **Get contacts** — Use `get_contacts` with domain filtering (e.g., `domain: "pinnacle.com"`) to identify all stakeholders.

3. **Gather meeting details** — For each relevant meeting, use `get_meeting` for summaries and `get_insights` for MEDDIC analysis, objections, competitor mentions, and sentiment.

4. **Track action items** — Use `get_action_items` to find open and completed items across related meetings.

5. **Analyze transcripts** — For critical moments (budget discussions, objections, decisions), use `get_transcript` to pull exact quotes.

## Output Format

### Deal Review: [Company/Deal Name]

**Deal Overview**
- Meetings: X meetings over Y weeks
- Key contacts: [Names and roles from participant data]
- Current stage assessment based on meeting progression

**MEDDIC Analysis**
- **Metrics**: What success metrics have been discussed?
- **Economic Buyer**: Identified? Access level?
- **Decision Criteria**: Technical and business requirements surfaced
- **Decision Process**: Timeline, approvals, procurement steps mentioned
- **Identify Pain**: Core problems driving the evaluation
- **Champion**: Who is advocating internally?

**Timeline**
- Chronological progression of meetings with key milestones

**Budget & Pricing**
- All budget mentions with exact quotes and context

**Competitive Landscape**
- Competitor mentions, comparisons, and win/loss factors

**Risk Assessment**
- Open objections, unresolved concerns, stalled items
- Action items that are overdue or unaddressed

**Recommended Next Steps**
- 3-5 specific, actionable recommendations based on the analysis
