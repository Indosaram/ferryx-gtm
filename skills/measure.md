# skill: measure

Purpose: capture metrics the same way every day so the loop's effects are comparable.

1. `bun scripts/snapshot.ts > metrics/day-N.json` (requires gh CLI login; the traffic API requires repo admin permission).
2. Record manual metrics in the `manual` field of the same file:
   - Discord: `curl -s 'https://discord.com/api/v9/invites/Z2hBkQEHUG?with_counts=true' | jq .approximate_member_count`
   - Waitlist (unique users, maintainer excluded):
     `(gh api --paginate repos/Indosaram/ferryx-gtm/issues/1/comments --jq '.[].user.login'; gh api --paginate repos/Indosaram/ferryx-gtm/issues/1/reactions --jq '.[].user.login') | grep -vx Indosaram | sort -u | wc -l`
   - Number and URLs of external posts and mentions
3. Put a table of change from the previous day and progress toward the 7-day goals at the top of `log/day-N.md`.
4. Look at the top 5 referrers and note which channel drove traffic.

Output: metrics/day-N.json, the "Metrics" section of log/day-N.md.
