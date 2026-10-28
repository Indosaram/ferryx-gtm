# Show HN (10/26 22:00 KST)

- HN bans LLM-written posts and comments. Read it once and change wording to how you talk.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.
- Answer every comment yourself for 6 hours.

**Submit link:** https://news.ycombinator.com/submitlink?u=https%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx&t=Show%20HN%3A%20Ferryx%20%E2%80%93%20Native%20terminal%20for%20coding%20agents%2C%20on%20Windows%20and%20Linux%20too

---

Title:

Show HN: Ferryx – Native terminal for coding agents, on Windows and Linux too

URL: https://github.com/Indosaram/ferryx

Text (first comment right after submitting):

Ferryx is a desktop terminal for running a bunch of coding agents (Claude Code, Codex, OpenCode, etc.) in tabs and splits. It runs on macOS, Linux and Windows.

Two things it does that I couldn't get elsewhere:

1. Agents survive closing the app. A Rust daemon owns the PTYs and the window is just a client, so you can quit and reopen and reattach to the same running sessions, with the output you missed replayed.
2. Remote Linux boxes without SSH. Install ferryx-cli on the box and it connects out through a relay, so no open port or public IP. The relay can be self-hosted.

It also shows which agent is waiting on you and notifies you, lets you check sessions from a phone browser, and can give each tab its own git worktree. Tauri + libghostty + wgpu, no Electron.

Caveats: source-available, not open source (free for individuals and small companies), and it's a solo project. Also not an IDE, so there's no editor or diff review like Orca has.

https://github.com/Indosaram/ferryx/releases/latest

If you run several agents in a terminal today, I'd like to hear what annoys you about it.
