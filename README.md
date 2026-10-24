# Ferryx GTM Agentic Loop

> Submission repo for Clone Loop Day in Seoul · Run period 2026-10-24 (Sat) to 2026-10-31 (Sat) 18:00 KST

[Ferryx](https://github.com/Indosaram/ferryx) is a native desktop workspace for running multiple CLI coding agents, such as Claude Code and Codex, in parallel on one screen. Each agent gets its own Git worktree, a daemon keeps sessions alive, and you can direct agents from your phone or a remote Linux server. It does not use Electron.

This repo is not a program you run. It is the **methodology of a GTM loop that we run by hand, repeatedly, for 7 days**: Markdown skills, a metrics collection script and daily logs.

## 7-day goals (as of 2026-10-31 18:00 KST)

The baseline was measured with `gh api` at 2026-10-24 17:07 KST ([metrics/baseline.json](metrics/baseline.json)).

| Metric | Baseline (10/24) | Goal | Stretch |
|---|---|---|---|
| GitHub stars | 17 | **300** | 1,000 |
| GitHub 14-day unique visitors (traffic uniques) | 11 | 1,500 | 5,000 |
| Cumulative installer downloads (excluding auto-update latest.json, signatures and checksums) | 393 | +600 | +2,000 |
| Discord members | 2 | 50 | 150 |
| Pro/Team waitlist (leading indicator for revenue) | 0 | 40 | 100 |
| External posts and mentions (HN/Reddit/GeekNews/newsletters) | 0 | 10 | 25 |

The waitlist counts unique users who left a comment or 👍 on [issue #1](https://github.com/Indosaram/ferryx-gtm/issues/1) (maintainer excluded). Each day's measure step records it in `manual.waitlist` of `metrics/day-N.json`.

**Being honest about revenue:** paid plans are not on sale yet (only pricing is public: Pro $8/month, Team launch price $12/seat/month). So the 7-day revenue goal is $0, and **waitlist signups** serve as the leading indicator for revenue instead. If the waitlist passes 20 by Day 4, we start the application review with a payment provider (Paddle or Polar); payments themselves open in December ([strategy/GTM.md](strategy/GTM.md) chapter 4, [launch-7day.md](strategy/launch-7day.md)).

## The loop on one page

```
 ┌─ 1. MEASURE ── metrics snapshot (scripts/snapshot.ts) ─────────┐
 │                                                                 │
 │  2. LISTEN ── collect comments on yesterday's posts, issues,    │
 │     and "reasons not to use it"                                 │
 │                                                                 │
 │  3. OBJECTION → FIX → STORY  (the core of this loop)            │
 │     top objection → fix product/docs → use that fix as the      │
 │     material for the next post                                  │
 │                                                                 │
 │  4. SHIP CONTENT ── 1-3 posts that follow each channel's rules  │
 │     (agents check facts and gather material; a human writes     │
 │     the text)                                                   │
 │                                                                 │
 │  5. REPLY ── a human answers every comment for 6 hours after    │
 │     posting                                                     │
 │                                                                 │
 └─ 6. RETRO ── write log/day-N.md, adjust next day's hypotheses ──┘
              and channels
```

### What makes this loop different

1. **The product is the loop's runtime (dogfooding loop).** The loop's agents (channel research, fact checking, objection review, metrics analysis) run in parallel inside Ferryx, one per panel and worktree. Screen recordings of the loop running become demo videos and post material as-is. "An agent tool promoted by agents" is proven with the tool itself.
2. **Objections are the fuel (objection-driven loop).** Before launch, we wrote 11 "reasons not to use Ferryx" from a skeptical user's point of view (history of lost sessions, non-OSI license, vendors absorbing the feature, and so on). Each day we actually fix, or honestly acknowledge, the biggest objection, and publish that process as content. This tests the hypothesis that developer communities respond to honest disclosure of limits more than to hype.
3. **Assumes zero followers.** With no existing reach, we use only algorithmic channels (HN front page, Reddit, GeekNews, GitHub Trending) and other people's channels (newsletters, awesome lists, creators). Each channel's posting rules (account age, self-promotion ratio, Lobsters invite-only, etc.) are spelled out in the skills so we don't lose accounts to rule violations.

## Repo structure

| Path | Contents |
|---|---|
| [strategy/GTM.md](strategy/GTM.md) | Full GTM strategy: positioning, target, competition, pricing and licensing, roadmap, phased plan, risks |
| [strategy/launch-7day.md](strategy/launch-7day.md) | This 7-day schedule and mid-course decision rules |
| [strategy/objections.md](strategy/objections.md) | The "reasons not to use it" list and response status (updated daily by the loop) |
| [loop/LOOP.md](loop/LOOP.md) | Daily loop procedure (the master skill agents read and execute) |
| [skills/](skills/) | Per-step skills: measure, listen, objection-fix, channel-post, reply, retro |
| [channels/rules.md](channels/rules.md) | Posting rules and prohibitions per channel |
| [scripts/snapshot.ts](scripts/snapshot.ts) | GitHub metrics snapshot (`bun scripts/snapshot.ts`) |
| [metrics/](metrics/) | Baseline and daily snapshots |
| [log/](log/) | Daily operation logs and retros |

## Division of roles between humans and agents

Hacker News bans posts and comments written with LLMs, and r/LocalLLaMA and r/rust also block AI-generated/LLM posts (channels/rules.md). So **a human writes posts and comments directly**, and agents handle only measurement, collecting reactions, fact checking and responding to objections (code and doc fixes). This separation is itself part of the loop design.

## Mapping to the judging criteria

| Judging criterion | Where to check in this repo |
|---|---|
| Is the strategy right for the product and customers? | strategy/GTM.md chapters 1-3, channels/rules.md |
| Was it actually run repeatedly? | log/day-*.md, metrics/*.json (committed daily) |
| Did interim results improve the loop? | The "Loop changes" section of each log, loop/CHANGELOG.md |
| Results against goals | Goals table above ↔ metrics/day-7.json |
