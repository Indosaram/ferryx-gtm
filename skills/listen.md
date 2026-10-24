# skill: listen

Purpose: classify user reactions as objections, requests, praise or bugs, and turn them into input for the next action.

1. Collect: comments on the previous day's posts (HN/Reddit/GeekNews, etc.), GitHub issues and discussions, Discord, "Ferryx" search results.
2. Summarize each item in one line and classify it: OBJECTION / REQUEST / PRAISE / BUG.
3. Map each OBJECTION to an existing item in `strategy/objections.md` and increment its count. If it is a new objection, add it.
4. File each BUG as a Ferryx issue with reproduction info (after human review).
5. Separate facts from interpretation. Don't generalize one comment into "users".

Output: the "What we heard" section of log/day-N.md, updated counts in objections.md.
