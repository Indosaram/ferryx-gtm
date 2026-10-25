# Show HN (10/26 22:00 KST)

- HN bans LLM-written posts and comments. Rewrite in your own words before posting.
- Stay for 6 hours after posting and answer every comment yourself.

**Submit link:** https://news.ycombinator.com/submitlink?u=https%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx&t=Show%20HN%3A%20Ferryx%20%E2%80%93%20Run%20Claude%20Code%2C%20Codex%20and%20other%20agents%20in%20parallel%20worktrees

---

Title:

Show HN: Ferryx – Run Claude Code, Codex and other agents in parallel worktrees

URL: https://github.com/Indosaram/ferryx

Text (posted as the first comment after submitting, or in the text field):

Hi HN, I'm the solo developer of Ferryx. It's a desktop terminal workspace for running several CLI coding agents on the same repository at once.

The problem I kept hitting: two agents in one checkout step on each other's files and commits, and when I closed the terminal app, the runs died with it. Ferryx gives each agent its own git worktree and branch, and the terminals belong to a background Rust daemon rather than the window, so closing or crashing the UI doesn't stop a running agent. When you reattach, the output you missed is replayed.

What it does today:
- One git worktree and branch per agent
- Status detection (working / waiting for you / idle) for Claude Code, Codex, Cursor, OpenCode, Copilot CLI and others, with a notification when an agent needs a decision
- Check on or type into a session from a phone or browser: sign in to your account there; the host connects out through a relay, so no inbound port or public IP is needed. You can self-host the relay.
- Native: Rust, Tauri v2, a libghostty terminal core and a wgpu renderer. No Electron.

Honest limits: it's source-available (Ferryx License), not open source. It's free for individuals and for companies under 50 people and $5M revenue. The Windows installer isn't code-signed yet, so SmartScreen will warn. There are no ARM64 builds for Linux or Windows. It's a one-person project.

Downloads for macOS, Windows and Linux need no signup: https://github.com/Indosaram/ferryx/releases/latest

I'd especially like to hear from people who already juggle worktrees by hand or with tmux: what would make you switch, or what makes this unnecessary for you?
