# r/ClaudeAI

- 10/30: the first post was rejected by the modbot under Showcase criterion (b), because how Claude helped was too vague. This version adds commit-backed specifics. Repost at least 1h after the rejection.

- Needs more than 50 karma.
- "How Claude helped" is based on commit trailers (252 commits co-authored by the omo agent). If you want to name Claude Code specifically, confirm it is true first.

**Submit link:** https://www.reddit.com/r/ClaudeAI/submit?type=self&title=I%20made%20a%20terminal%20for%20running%20several%20Claude%20Code%20sessions%2C%20on%20Mac%2C%20Windows%20and%20Linux&text=Disclosure%3A%20I%20made%20this.%0A%0AI%20run%20a%20few%20Claude%20Code%20sessions%20at%20once%20in%20terminal%20tabs%2C%20so%20I%20built%20Ferryx%20for%20that.%20It%20runs%20on%20macOS%2C%20Windows%20and%20Linux.%0A%0AClosing%20the%20app%20doesn't%20kill%20Claude.%20A%20background%20daemon%20owns%20the%20terminals%2C%20so%20you%20reopen%20and%20you're%20back%20in%20the%20same%20running%20sessions%20with%20the%20output%20you%20missed.%20It%20shows%20which%20session%20is%20waiting%20on%20you%20and%20pings%20you%2C%20and%20there's%20a%20phone%20browser%20view%20too.%0A%0AIf%20you%20run%20Claude%20on%20a%20remote%20Linux%20box%2C%20ferryx-cli%20connects%20out%20through%20a%20relay%2C%20so%20no%20SSH%20or%20open%20port%20needed.%0A%0AHow%20Claude%20helped%3A%0A%0A-%20Most%20of%20the%20code%20was%20written%20by%20agent%20sessions%20running%20inside%20Ferryx%20itself.%20It's%20a%20mix%20of%20Claude%20and%20GPT%20models%2C%20I%20write%20the%20task%20and%20review%20the%20diff.%0A-%20Claude%20Code%20fixed%20a%20macOS%20font%20bug%3A%20CoreText%20never%20fails%20when%20you%20ask%20for%20a%20font%20that%20isn't%20installed%2C%20it%20quietly%20hands%20back%20Helvetica.%20So%20on%20some%20Macs%20the%20terminal%20grid%20was%20measured%20from%20a%20proportional%20font.%20The%20fix%20checks%20the%20resolved%20font%20name%20and%20falls%20back%20to%20Menlo%2C%20and%20the%20commit%20has%20the%20before%2Fafter%20cell%20sizes.%0A-%20Claude%20Opus%20did%20a%20review%20pass%20on%20some%20of%20the%20riskier%20changes%2C%20e.g.%20cleaning%20up%20the%20built-in%20browser%20when%20tab%20creation%20times%20out.%0A-%20The%20%22waiting%20on%20you%22%20detection%20for%20Claude%20Code%20reads%20its%20terminal%20title%20(spinner%20while%20working%2C%20%E2%9C%B3%20when%20idle)%20plus%20screen%20fixtures%20for%20the%20approval%20prompt.%0A%0AFree%20for%20individuals%2C%20no%20signup%20to%20download.%20Source-available%2C%20not%20open%20source.%0A%0Ahttps%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx%0A%0ALinux%2FWindows%20folks%2C%20curious%20what%20you're%20using%20now.%20tmux%3F

---

Title:

I made a terminal for running several Claude Code sessions, on Mac, Windows and Linux

Body:

Disclosure: I made this.

I run a few Claude Code sessions at once in terminal tabs, so I built Ferryx for that. It runs on macOS, Windows and Linux.

Closing the app doesn't kill Claude. A background daemon owns the terminals, so you reopen and you're back in the same running sessions with the output you missed. It shows which session is waiting on you and pings you, and there's a phone browser view too.

If you run Claude on a remote Linux box, ferryx-cli connects out through a relay, so no SSH or open port needed.

How Claude helped:

- Most of the code was written by agent sessions running inside Ferryx itself. It's a mix of Claude and GPT models, I write the task and review the diff.
- Claude Code fixed a macOS font bug: CoreText never fails when you ask for a font that isn't installed, it quietly hands back Helvetica. So on some Macs the terminal grid was measured from a proportional font. The fix checks the resolved font name and falls back to Menlo, and the commit has the before/after cell sizes.
- Claude Opus did a review pass on some of the riskier changes, e.g. cleaning up the built-in browser when tab creation times out.
- The "waiting on you" detection for Claude Code reads its terminal title (spinner while working, ✳ when idle) plus screen fixtures for the approval prompt.

Free for individuals, no signup to download. Source-available, not open source.

https://github.com/Indosaram/ferryx

Linux/Windows folks, curious what you're using now. tmux?
