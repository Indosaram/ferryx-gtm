# Per-channel rules and prohibitions

Checked each official page on 2026-10-24 (Reddit via 2026-07~08 archived copies). Re-check right before posting.

| Channel | Key rules (source) | Our approach |
|---|---|---|
| Hacker News (Show HN) | Only things people can actually try; no landing or signup pages. No asking friends for votes or comments. **No LLM-written posts or comments**. No company account names. No deleting and reposting the same post ([showhn](https://news.ycombinator.com/showhn.html), [guidelines](https://news.ycombinator.com/newsguidelines.html), [dang's tips](https://news.ycombinator.com/item?id=22336638)) | Written by a human. No license terms in the title; state source-available in the first paragraph of the body (moderators correct "open source": [example](https://news.ycombinator.com/item?id=42824568)). Email listed in profile. 10/26 22:00 KST = 13:00 UTC, within the 12~17 UTC window research finds favorable ([arXiv 2511.04453](https://arxiv.org/abs/2511.04453)) |
| HN retry | A small number of reposts allowed for posts that got little attention within a year ([FAQ](https://news.ycombinator.com/newsfaq.html)). Second-chance pool suggestions go to hn@ycombinator.com ([explanation](https://news.ycombinator.com/item?id=26998308)) | A post from a different angle instead of reposting the same one. If needed, one second-chance request email |
| r/ClaudeAI | Promoting Claude-related tools you built is allowed; explain how Claude helped, state that it can be tried for free; **posting to the feed requires more than 50 karma** ([rules copy](http://web.archive.org/web/20260823233716/https://old.reddit.com/r/ClaudeAI/about/rules/)) | Only after confirming the karma requirement |
| r/LocalLLaMA | Self-promotion at most 10% of activity, disclose affiliation, no LLM-generated posts ([copy](http://web.archive.org/web/20260807221923/https://old.reddit.com/r/LocalLLaMA/about/rules/)) | Only when there is a local model (Ollama, etc.) integration story |
| r/ChatGPTCoding | Promotional posts go in the self-promotion thread ([copy](http://web.archive.org/web/20260727134012/https://old.reddit.com/r/ChatGPTCoding/about/rules)) | Self-promotion thread only |
| r/rust | Must be on a Rust topic; low-quality and AI-generated posts removed ([copy](http://web.archive.org/web/20260811152833/https://old.reddit.com/r/rust/about/rules)) | Only technical posts on libghostty/wgpu/daemon architecture |
| r/programming | **No "I made this" project promotion**, technical posts only ([copy](http://web.archive.org/web/20260811153143/https://old.reddit.com/r/programming/about/rules)) | Technical posts only (benchmark methodology, etc.), after 10/27 |
| r/commandline | No generative-AI-related projects (only well-known exceptions), no projects under 30 days old ([copy](http://web.archive.org/web/20260811152913/https://old.reddit.com/r/commandline/about/rules)) | **Not used** |
| r/opensource | Linked code **must have an OSI license** ([copy](http://web.archive.org/web/20260726134356/https://old.reddit.com/r/opensource/about/rules/)) | **Not used** (Ferryx License is not OSI) |
| Lobsters | **No self-promotion posts for 70 days after joining**; new accounts cannot post previously unseen domains or use the show tag; invite-only ([about](https://lobste.rs/about), [code](https://github.com/lobsters/lobsters/blob/407536444934ac7d78f4ce1c18f228e3891a8663/app/models/user.rb#L178)) | Comment participation only this week. Only if an existing member posts it on their own judgment |
| GeekNews | **Links can be submitted starting 1 week after signup**. Own products must go through Show GN, title "Project name - key feature"; no asking acquaintances for upvotes, no multiple accounts; the same project cannot be resubmitted for a set period ([guidelines](https://news.hada.io/guidelines), [Show GN](https://news.hada.io/blog/show)) | First check whether the account is at least 1 week old. If not, postpone rather than having an acquaintance post on our behalf |
| Product Hunt | Posting it yourself is not a disadvantage; no asking for votes (asking for visits/comments is OK); front-page placement is editorially selected ([launch guide](https://www.producthunt.com/launch/before-launch)) | Postponed until after the 7 days (no followers) |

## Lists and newsletters

| Target | Requirements (source) | Decision |
|---|---|---|
| [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | 14+ days of steady commits or 100+ stars, issue form only, written by a human ([CONTRIBUTING](https://github.com/hesreallyhim/awesome-claude-code/blob/15a8bf8626eaa14ad52ff118e53ace29a4cca244/CONTRIBUTING.md)) | Commit history requirement met → submit 10/24 |
| [Terminal Trove](https://terminaltrove.com/post/) | Preview image/GIF required, non-open licenses also OK (site blocks automated access with 403, so verified via [2026-07 archived copy](http://web.archive.org/web/20260713020823/https://terminaltrove.com/post/)) | Submit 10/24 |
| [Console.dev](https://console.dev/selection-criteria) | For developers, self-serve signup, good docs. Submit by email | Submit 10/24 |
| [Changelog News](https://changelog.com/news/submit) | Submitting your own work is welcome; commercial products excluded | Not applicable (commercial product with public paid pricing). If a technical post such as benchmark methodology comes out, consider submitting just that post |
| awesome-cli-apps | Free/open-source license required ([contributing](https://github.com/agarrharr/awesome-cli-apps/blob/1f85964177eefd08469005b0c47d09c7c729cfd6/contributing.md)) | Not applicable |
| awesome-tuis | Repo at least 6 months old | Not applicable (also not a TUI) |

## Prohibited everywhere

- Writing "open source" → use "source-available"
- Posting agent-written posts or comments as is
- Presenting unreleased features as current features; unmeasured competitor performance numbers
- Asking for votes, multiple accounts, auto-posting bots
