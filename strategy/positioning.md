# Positioning (rewritten 2026-10-28)

Replaces section 1 of `GTM.md`. Every claim below was checked against the released build
`v2026.10.11.1` (the one people download today) or a competitor's own README/docs on 2026-10-28.

## Why the old pitch failed

- Old pitch: "run agents in parallel, each in its own git worktree, no conflicts."
- That is Orca's headline feature, and Orca has 92k stars, is MIT-licensed and free. Leading with worktrees turns Ferryx into "a smaller, non-open-source Orca."
- Dropping worktrees and calling Ferryx "a terminal multiplexer" (the 10/28 X post) turns it into "tmux" or "cmux." It doesn't answer "why not the free one?" either. X readers were confused because neither framing says what Ferryx does that the others don't.

## Category

Ferryx is an **agent terminal**, in the same category as cmux. It is not an agent IDE like Orca.
It is a terminal with tabs and splits that knows which agent is waiting on you. Worktrees are a
supporting feature, not the headline.

## What is actually different (verified)

| | Ferryx (v2026.10.11.1) | cmux | Orca |
|---|---|---|---|
| Platforms | macOS, Windows (MS Store + .exe), Linux (AppImage, .deb) | **macOS only**. Linux request #330 is its most-reacted issue (220+). Windows request #1012 | macOS, Windows, Linux |
| App shell | Tauri + libghostty-vt + wgpu, no Electron | Swift/AppKit + libghostty | **Electron**. RAM/battery complaints (#7919, #7017) |
| Agents survive closing the app | **Yes**. A Rust daemon owns the PTYs, the GUI is a client, and output is replayed on reattach (tested in `daemon_persistence_contract.rs`) | **No**. The README says it restores layout/scrollback but does "not keep arbitrary live processes running" (#1663 open) | Yes, its terminals also live in a daemon. Update orphans daemons (#9138) |
| Remote machines | **Outbound relay**: `ferryx-cli` on the box, no SSH, no open port, no public IP | `cmux ssh` | SSH worktrees, or run `orca serve` on the box (Tailscale typical) |
| "Which agent needs me" | Status manifests for 11 agents in the release (16 on main) | Notification rings (its signature feature) | Yes |
| Phone | Web client after account sign-in | iOS beta (TestFlight) | iOS + Android apps |
| License | Source-available, free for individuals and small companies | GPL | MIT |

**Where Ferryx is the only option:** a native, non-Electron agent terminal on **Windows or Linux**
where **agents keep running after you close the app**. cmux can't do the first or the second. Orca
can do the second but is Electron. **Second wedge:** remote Linux boxes with no SSH and no open
port.

**Where Ferryx loses (say it before readers do):**
- Not open source. cmux is GPL and Orca is MIT.
- One developer.
- No editor and no diff review, which Orca has.
- No agent-scriptable browser, which cmux has.
- Phone access is a web client, not an app.

## One line

- EN: **"A native terminal for coding agents on macOS, Windows and Linux. Agents keep running when you close the app, and remote boxes connect without SSH."**
- KO: **"macOS·Windows·Linux에서 도는 코딩 에이전트용 네이티브 터미널. 앱을 닫아도 에이전트는 계속 돌고, 원격 서버는 SSH 없이 붙습니다."**

Do not name cmux, Orca or other products in the site copy or post headlines (owner rule, 2026-10-29). Comparisons live only on the site's `/compare/` pages and in replies to people who ask.

## Beachhead (first users to target)

1. **cmux users who can't use cmux.** Linux and Windows devs are the 220+ reactions on cmux #330. Reach them in threads asking "cmux for Linux/Windows?" on r/ClaudeAI, r/ClaudeCode, r/commandline comments, GeekNews and HN.
2. **Orca users who complain about Electron weight**, or who don't want an IDE around their terminal.
3. **People running agents on a remote box** who are tired of SSH and tmux reattach.

## Do not claim

- **The supervisor ("answers routine prompts like you").** It is not in the released build: the agent_control code first landed on 2026-10-21 and the release is from 10-11. The ferryx.dev hero and the main README already lead with it. Until a release ships it, launch posts must not mention it, and the site headline is a live mismatch (objection #12).
- Worktree isolation as the headline. It is fine as one line ("each tab can get its own worktree").
- Memory or speed comparisons. Nothing has been measured against cmux or Orca.
- "Open source."
- PIN/QR pairing. It is retired, and the released README still says it (fixed on main).
