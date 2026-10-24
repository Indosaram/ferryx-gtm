# Daily GTM Loop — Master Skill

This file is the procedure that humans and agents run in the same order every day. It starts once a day (9 AM KST), and on days with a post, a human personally takes the REPLY step after posting.

## Runtime environment

Open the `ferryx-gtm` workspace in Ferryx and bring up the panels below. Each panel uses its own worktree, so agents don't overwrite each other's files.

| Panel | Agent | Skill |
|---|---|---|
| A | Claude Code | skills/measure.md → skills/retro.md |
| B | Codex | skills/listen.md |
| C | Claude Code | skills/objection-fix.md |
| D | Codex | skills/channel-post.md |
| Human | — | skills/reply.md, final post button |

Record the screen while the loop runs and use it as content material.

## Order

1. **MEASURE** (`skills/measure.md`): `bun scripts/snapshot.ts` → `metrics/day-N.json`. Compute change from the previous day.
2. **LISTEN** (`skills/listen.md`): Gather comments on yesterday's posts, GitHub issues, Discord and mention search results, and classify them as objections, requests or praise.
3. **OBJECTION → FIX → STORY** (`skills/objection-fix.md`): Pick today's biggest objection from `strategy/objections.md`, fix it (small fix or docs) or honestly acknowledge it, and turn the result into material for the next post.
4. **SHIP CONTENT** (`skills/channel-post.md`): The agent gathers today's channel rules, material and factual evidence → **a human writes the text personally** → check against `channels/rules.md` → a human posts.
5. **REPLY** (`skills/reply.md`): For 6 hours after posting, a human answers every comment. Agents only do fact checks and draft replies.
6. **RETRO** (`skills/retro.md`): Write `log/day-N.md`. What worked, and one thing to change tomorrow. If the loop itself changed, record it in `loop/CHANGELOG.md`.

## Invariant rules

- No asking for votes or stars, no multiple accounts, no reposting the same post.
- Don't describe unreleased features as current features (roadmap items are "Coming soon").
- No guarantee language like "never lose work". Only state numbers for what we measured.
- Humans write and post posts and comments personally. Never post agent-written sentences as-is (HN and others ban LLM-written posts).
- Before screen recording, check that no tokens, emails or private paths are visible.
- Commit daily in the format `day-N: <one-line loop change>`.
