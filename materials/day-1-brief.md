# Day 1 material brief (agent-gathered, humans write the posts)

Prepared 2026-10-25 22:10 KST for the Asia early release (10/25) and Show HN (10/26 22:00 KST).
Per `skills/channel-post.md`: this is material and evidence only. Do not paste sentences from here into a post.

## Blocker to resolve before Show HN: site vs downloadable binary

| Claim on ferryx.dev (deployed 10/25 22:05) | Latest release users download (v2026.10.11.1, built from a86df627) | Status |
|---|---|---|
| Status detection for 16 agents | 11 manifests. aider, crush, droid, omp, pi were added after the release | **Mismatch** |
| Phone pairing = account sign-in | Account sign-in present, PIN/QR control retired (268977c4, fa0b5973 are in the release) | OK |
| No Gemini CLI detection | Release has no gemini manifest either | OK |

Show HN readers download the release, not main. Options:
1. Cut a release from main before 10/26 22:00 KST (local multi-host runbook: docs/releases/LOCAL_RELEASE_RUNBOOK.md). A local 2026.1025.4 build exists in ~/ferryx-releases, but nothing is published.
2. Or say "11 agents in the current release, 16 on main" in the post and keep the site as is.

## Angles with evidence

| Angle | Fact to cite | Evidence |
|---|---|---|
| Parallel agents, one worktree each | Each agent runs in its own git worktree; detection manifests for 11 (release) / 16 (main) agents | src-tauri/src/agent_detect/manifests/, site /docs/facts/ |
| Sessions survive app restarts | PTYs owned by a background daemon, not the window | AGENTS.md (daemon owns PTY master fds), /docs/architecture/ |
| Check in from a phone | Sign in to the Ferryx account on the phone; outbound relay, no inbound port | /blog/pair-ferryx-with-phone/, /docs/guide/ |
| Not Electron | Rust + Tauri, libghostty-vt core, wgpu rendering | README, /docs/architecture/ |
| Honest limits (put in the first paragraph) | Source-available (Ferryx License), Windows installer not code-signed, no Linux/Windows ARM64 binaries, no editor/LSP | README L34, L156; compare/orca.md |

## Channel readiness (things only the account owner can confirm)

- GeekNews Show GN: the account must be at least 1 week old. Not verifiable from here.
- HN: post as a personal account with an email in the profile. Text written by a human.
- r/ClaudeAI: more than 50 karma required. Not verifiable from here.
- Threads/X: own accounts. Korean copy for Threads, English for X.

## LISTEN snapshot (22:08 KST)

- HN (Algolia, exact "ferryx"): 0 hits. Reddit search API: 403, not checked.
- GitHub: 17 stars (last new star 10/21), 4 forks, 0 issues/PRs from outside since 10/23, no new stars on 10/24~25.
- External mentions: only an AppImage catalog PR (2026-09-28). awesome-claude-code: no Ferryx submission found, although launch-7day.md had it for 10/24.
