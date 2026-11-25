# IceCubes

The `icecubes` MCP server gives you the user's recorded meetings (Google Meet, Zoom, Microsoft Teams) from IceCubes.

- To find meetings by date, title, participant or tag, use `get_meetings`.
- For one meeting's summary, action items and notes, use `get_meeting`. Use `get_transcript` only when exact wording or quotes are needed.
- To find where something was mentioned, use `search_meetings`. For an analysed answer across several meetings, use `query_meetings` (it can take up to a minute and uses one IceCubes AI credit).
- For sales calls, `get_insights` returns objections, next steps, pricing, MEDDIC points and competitor mentions.
- Only create or change action items and notes (`create_action_item`, `update_action_item`, `update_notes`) when the user explicitly asks.
- Cite meetings by title and date.

If a tool reports that authentication is needed, tell the user to run `/mcp auth icecubes` and sign in to IceCubes in the browser.
