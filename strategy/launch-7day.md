# 7-day launch schedule (2026-10-24 ~ 10-31)

Premise: we have almost no existing followers or influence. Stars come only from algorithmic channels and other people's channels.

| Date (KST) | To do |
|---|---|
| 10/24 (Sat) | Measure baseline, publish waitlist (issue #1), README demo GIF, Windows SmartScreen notice, check HN/Reddit/GeekNews account requirements, submit to awesome-claude-code/Terminal Trove/Console.dev, contact creators, request Lobsters invite |
| 10/24~25 **Required before Show HN** | Resolve objection #10: remove QR wording from the Ferryx README and site ("6-digit PIN pairing"), Gemini CLI → Antigravity, unify agent count at 16, delete "never lose work" and "free and open" wording. Record commit links in objections.md. **If not done, postpone Show HN** |
| 10/25 (Sun) | Early release in Asia: GeekNews Show GN (only if the account is at least 1 week old), Korean dev communities, Threads, Qiita/Zenn, V2EX. Early stars from here are the base for GitHub Trending |
| 10/26 (Mon) | 22:00 KST Show HN (9 AM US Eastern, 13:00 UTC). Post body and comments written by a human. Reply to every comment for the next 6 hours. Reddit only in subs whose requirements we meet, such as r/ClaudeAI, 1 hour apart |
| 10/27~29 | Ship hotfixes addressing objections, retry a regular HN post with a benchmark post or technical post |
| 10/30~31 | Share newsletter/list mentions, retrospective post, final measurement |

## Mid-course decision rules

- If Show HN has not reached the front page by 10/27 01:00: leave the same post as is (no reposting), and retry on 10/28~29 with a new post from a different angle (benchmark, technical post on "8 agents in parallel").
- (Applies after 10/27) If daily star growth is under 20 for two days in a row: treat it as a messaging problem rather than a channel problem and change the headline A/B (parallel vs session persistence vs remote control).
- If the waitlist has 20+ people at the Day 4 retrospective, start the Paddle or Polar signup review. Opening payments itself happens in December per the 90-day plan.

## Why Phase 0 was cut short

Phase 0 in GTM.md (2~4 weeks: benchmarks, demo, guide) is originally a pre-launch stage. This time it was shortened because of the 7-day competition period. Only the copy cleanup (objection #10) is finished before Show HN; the benchmark (objection #11) and session persistence measurement (objection #1) move to material for the 10/27~29 retry posts.

## Expectations (empirical estimate, unverified)

- 7-day stars: 300~2,000. 10,000 is under 1%.
- Reference: the average gain for 138 AI repos posted on HN was +121 stars in 24 hours and +289 in 7 days. However, the sample's average starting point was 1,247 stars, which differs from a zero-follower case, and the median is much lower ([arXiv 2511.04453](https://arxiv.org/abs/2511.04453)).
- In posts, write "source-available" instead of "open source" (the license is not OSI-approved).

## Left out

- Product Hunt: judged low-impact for a launch with no followers. Postponed until after the 7 days.
- Asking for HN reposts, asking for votes: risk of rule violations.
- Posting directly to Lobsters: new accounts cannot self-promote for 70 days ([about](https://lobste.rs/about)). This week, comment participation only.
- r/opensource, r/commandline: not allowed under their license/AI project rules.

## After 7 days: 90-day plan (2026-11 ~ 2027-01)

Keep running the 7-day loop with the same 6 steps, but change the goals per stage. The numbers are hypotheses to be reset based on the 7-day results.

| Period | Focus | To do | Decision metrics (hypothesis) |
|---|---|---|---|
| Weeks 1~4 (November) | Rebuilding trust and activation | Resolve top 5 objections (clean up guarantee wording/Gemini/QR/"free and open" copy, security doc, publish benchmark), Windows signing, onboarding GIF, implement opt-in anonymous funnel instrumentation (install → 2+ agents running concurrently) | 1,000 stars, (after instrumentation ships) 40% run 2+ agents within 24 hours of install |
| Weeks 5~8 (December) | First revenue | Open Pro payments via Paddle or Polar, convert waitlist, 5 user case studies, Product Hunt (once we have followers) | 30 paid Pro users, 10% waitlist → paid conversion |
| Weeks 9~12 (January) | Team signals | Minimal Team admin features (invites/seats), reach out to companies with 3+ users on the same domain, 3 design partner teams | 3 Team design partner teams, 1 paid Team deal |

**Standing principles:** Record each weekly retrospective in `loop/CHANGELOG.md`. Do not write performance comparisons we have not measured. Mark roadmap items as "Coming soon".
