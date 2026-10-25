# Show HN (10/26 22:00 KST)

- HN bans LLM-written posts and comments. Read it once and change wording to how you talk.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.
- Answer every comment yourself for 6 hours.

**Submit link:** https://news.ycombinator.com/submitlink?u=https%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx&t=Show%20HN%3A%20Ferryx%20%E2%80%93%20Run%20Claude%20Code%2C%20Codex%20and%20other%20agents%20in%20parallel%20worktrees

---

Title:

Show HN: Ferryx – Run Claude Code, Codex and other agents in parallel worktrees

URL: https://github.com/Indosaram/ferryx

Text (first comment right after submitting):

I've been running Claude Code and Codex on the same repo at the same time for a while now. Two things kept going wrong. They'd edit the same files in one checkout and I'd end up untangling the mess by hand. And if I closed the terminal app, or it crashed, whatever was running died with it.

So I built Ferryx. Each agent gets its own git worktree and branch. The terminals are owned by a background daemon written in Rust, not by the window, so closing the app doesn't kill anything. When you open it again you get the output you missed.

It also tells you which agent is working, which one is idle and which is waiting on you, and pings you when one needs an answer. That works for Claude Code, Codex, Cursor, OpenCode, Copilot CLI and a few others. You can check in from your phone too: sign in there and the desktop connects out through a relay, so there's no port to open. The relay can be self-hosted.

It's Tauri with a libghostty terminal core and wgpu rendering, so no Electron.

Some things you should know. It's source-available, not open source: free for individuals and for companies under 50 people / $5M revenue. The Windows build isn't code-signed yet, so SmartScreen complains. No ARM64 builds for Linux or Windows. And it's just me working on it.

No signup to download: https://github.com/Indosaram/ferryx/releases/latest

If you already do this with plain worktrees or tmux, I'm curious whether this would replace that for you or not.
