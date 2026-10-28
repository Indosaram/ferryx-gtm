# Show HN (10/26 22:00 KST)

- HN bans LLM-written posts and comments. Read it once and change wording to how you talk.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.
- Answer every comment yourself for 6 hours.

**Submit link:** https://news.ycombinator.com/submitlink?u=https%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx&t=Show%20HN%3A%20Ferryx%20%E2%80%93%20A%20native%20terminal%20multiplexer%20for%20running%20coding%20agents%20side%20by%20side

---

Title:

Show HN: Ferryx – A native terminal multiplexer for running coding agents side by side

URL: https://github.com/Indosaram/ferryx

Text (first comment right after submitting):

Ferryx is a terminal multiplexer. Tabs and split panes like tmux, but as a desktop app, built around having several coding agents (Claude Code, Codex, etc.) open at once.

The terminals are owned by a background daemon written in Rust, not by the window, so closing the app doesn't kill your shells or whatever agent is running in them. Open it again and you reattach where you left off.

Each pane shows whether the agent in it is working, idle, or waiting on you, and pings you when one needs an answer. That works for Claude Code, Codex, Cursor, OpenCode, Copilot CLI and a few others. You can check in from your phone too: sign in there and the desktop connects out through a relay, so there's no port to open. The relay can be self-hosted.

It's Tauri with a libghostty terminal core and wgpu rendering, so no Electron.

Some things you should know. It's source-available, not open source: free for individuals and for companies under 50 people / $5M revenue. The Windows build isn't code-signed yet, so SmartScreen complains. No ARM64 builds for Linux or Windows. And it's just me working on it.

No signup to download: https://github.com/Indosaram/ferryx/releases/latest

If you run a bunch of agents in tmux or another terminal today, I'm curious what bugs you about it.
