# Reasons not to use Ferryx — objection list and response status

Written before launch from the perspective of a skeptical developer, CTO, and security lead. Each day in the LISTEN step, map real comments here and increment "Seen"; in the OBJECTION-FIX step, reduce them one at a time.
Baseline: Ferryx main 2026-10-24.

| # | Objection | Severity | Evidence (current facts) | Response plan | Status | Seen |
|---|---|---|---|---|---|---|
| 1 | "I'm scared to trust it with my sessions" — sessions were lost during past updates and force-quits, yet the site guarantees "never lose work" | Critical | "never lose work" removed 2026-10-24 ([6962b674](https://github.com/Indosaram/ferryx/commit/6962b674)); FAQ, landing and README now state the daemon limit (stopping the daemon or rebooting ends sessions) | Delete the guarantee wording; publish an honest post about the loss incidents and the structural fixes | Copy done; incident post (human-written) pending | 0 |
| 2 | "tmux + git worktree, or the vendor's own features, are enough" | Critical | Claude Code and Codex are absorbing worktree and remote features | Demo showing vendor neutrality (mixing 16 agents), status detection, mobile, and remote servers in one product | Pending | 0 |
| 3 | "It's not open source" | High | Ferryx License 1.0 (source-available, free for small use) | State source-available in posts, delete "free and open" wording | In progress (site wording removed 2026-10-24) | 0 |
| 4 | "One-person project, bus factor 1" | High | 1 maintainer; ROADMAP.md and CHANGELOG.md are public and linked from README | Build trust via public roadmap/changelog and Discord response speed | In progress | 0 |
| 5 | "Hard to pass security review" | High | Security doc published: relay visibility, agent control defaults, retention, updater trust chain (ferryx.dev/docs/security, last edit [776f7421](https://github.com/Indosaram/ferryx/commit/776f7421)) | Security doc (data flow, what the relay sees), review defaults | Done (2026-10-25) | 0 |
| 6 | "Can't buy a paid plan / Free is limited to 1 remote" | High | Payments on hold | Measure demand via waitlist; if 20+ by Day 4, start payment provider (Paddle/Polar) signup review; payments open in December (launch-7day.md 90-day plan) | In progress | 0 |
| 7 | "Installation is a hassle" | High | Windows still unsigned, x64 only; SmartScreen notice on landing and FAQ, platform table in README | SmartScreen notice, publish platform table | Notice done; signing pending | 0 |
| 8 | "It creates .orca-worktrees and orca/* branches in my repo" | High | New worktrees use .ferryx-worktrees and ferryx/* with a configurable prefix; legacy orca names only recognized ([a8a77130](https://github.com/Indosaram/ferryx/commit/a8a77130), main only, not in release v2026.10.11.1) | Publish renaming plan, consider a location setting option | Fixed on main; ships with next release | 0 |
| 9 | "Too many features and concepts" | Medium-high | Hub, design mode, DAG view, etc. | Onboarding GIF showing only the first-5-minutes path | Pending | 0 |
| 10 | "The marketing doesn't match reality" | Medium-high | Site's Gemini CLI / 11 agents / QR+PIN pairing claims didn't match the code (PIN/QR control was retired 2026-09-25; pairing is account sign-in + enrollment code) | Fix copy before launch | Done (2026-10-25) | 0 |
| 11 | "Memory and disk cost" | Medium | No published measurements | Publish a reproducible benchmark script | Pending | 0 |

### #12. "The site sells a feature I can't download" (opened 2026-10-28)

- **Fact:** ferryx.dev's hero ("Parallel agents, supervised your way") and the main-branch README lead with the supervisor that "answers routine prompts the way you would." The released build v2026.10.11.1 (10/11) has no agent_control/supervisor code: it first landed on main on 10/21 and is default-off since 1fc72124 (10/25).
- **Risk:** visitors from GN/HN/Reddit download the release and can't find the headline feature.
- **Response:** either ship a release containing the supervisor, or change the site hero and README headline to the positioning line (cmux-like, Windows/Linux, agents survive quit, no-SSH remote) until it ships. Launch posts already avoid the supervisor.
- **Status:** open. Owner decision needed: release first, or headline first.

## Response impact log

| Date | Objection # | What was done (commit/doc URL) | Post URL that used it | Star change 24h after posting | Main referrer |
|---|---|---|---|---|---|
| 2026-10-24 | 10 | Agent list generated from the 16 detection manifests, Gemini CLI claims dropped ([5376ddd9](https://github.com/Indosaram/ferryx/commit/5376ddd9)) | | | |
| 2026-10-24 | 3, 10 | "free and open" pricing copy replaced with license-accurate wording ([82b0c424](https://github.com/Indosaram/ferryx/commit/82b0c424)) | | | |
| 2026-10-25 | 10 | Retired PIN/QR pairing removed from landing, docs, compare pages and 15 remote blog posts; pairing described as account sign-in ([1fa4a6e6](https://github.com/Indosaram/ferryx/commit/1fa4a6e6)) | | | |
