# Day 1 — 2026-10-25 (Sun)

## Metrics (10:37 KST)

| Metric | Day 0 | Day 1 | Change | Goal | % of goal |
|---|---|---|---|---|---|
| Stars | 17 | 17 | 0 | 300 | 0% |
| 14-day unique visitors | 11 | 11 | 0 | 1,500 | 0% |
| Installer downloads (cumulative) | 393 | 406 | +13 | +600 | 2.2% |
| Discord members | 2 | 2 | 0 | 50 | 0% |
| Waitlist (issue #1) | 0 | 0 | 0 | 40 | 0% |
| External posts / mentions | 0 | 0 | 0 | 10 | 0% |

Other: 14-day clones 1,693 / 340 unique (Day 0: 1,741 / 319). Referrers: github.com 3 (unchanged).

Interpretation: no inbound channel has opened yet; downloads grow only from existing users and auto-discovery. Nothing has been posted since the baseline, so Day 1 results depend entirely on today's SHIP CONTENT step.

## What we did
| Time (KST) | Action | URL / commit |
|---|---|---|
| 10:37 | MEASURE: metrics/day-1.json | |
| 22:05 | Deployed ferryx.dev from ferryx@1fa4a6e6 (wrangler version 56395d36); live guide/landing/compare pages verified without PIN/QR copy | https://ferryx.dev/docs/guide/ |
| 22:00 | OBJECTION-FIX #10: verified copy against code. Agent count (16) and Gemini CLI were already fixed 10/24; removed the retired PIN/QR pairing copy from 24 site files. Show HN precondition met | [ferryx@1fa4a6e6](https://github.com/Indosaram/ferryx/commit/1fa4a6e6) |

## What we heard

- No external reactions to classify: HN exact search 0, no outside GitHub issues/PRs since 10/23, no new stars since 10/21. Reddit search returned 403 (unchecked). Nothing was posted yet, so this is expected.
- Fact (not a reaction): the site now claims 16 detected agents, but the downloadable release v2026.10.11.1 ships 11. See materials/day-1-brief.md.

## What worked / what didn't

## Decision rule check
| Rule (launch-7day.md) | Triggered? | Supporting numbers | Action |
|---|---|---|---|
| If HN front page fails, retry with a new angle | | | |
| (After 10/27) Under +20 stars/day for 2 consecutive days → replace headline | | | |
| Day 4 waitlist at 20 or more → start payment provider application review | | | |

## Loop changes

- The 10/24 objection #10 note itself was wrong (it prescribed "6-digit PIN pairing", which had already been retired). Rule: verify objection evidence against the current code, not against the strategy doc, before fixing copy.

## Tomorrow

- Before 10/26 22:00 KST: decide between cutting a release from main or stating "11 in release, 16 on main" in the Show HN text.
- The 10/24 list submissions (awesome-claude-code, Terminal Trove, Console.dev) show no trace; confirm or do them.
- Asia early release posts (GeekNews/Threads) were not posted on 10/25; human-written posts only.
