# Ferryx Go-To-Market Strategy

Written: 2026-10-24 (Section 4 decisions applied: 2026-10-24)
Sources: Ferryx repository README, LICENSE (Ferryx License 1.0, source-available; earlier releases are SUL-1.0), site copy, 2026-09 internal competitive analysis, 2026-10-24 external research (links in body)
Legend: ✅ available now · 🟡 partially implemented / not wired up · 🔮 future plan (not available now)

---

## 1. Positioning

**One-line definition**
> Ferryx is a native workspace for running multiple AI coding agents side by side on one screen, and for continuing to direct them from your phone after you close your laptop.

**Category:** Not a "terminal" but an **Agent Operations Workspace**. It does not compete with terminals (Ghostty, Warp); it occupies the "agent control" layer on top of them.

**Three core messages**
1. **Parallel, without conflicts** — automatic Git worktree per agent ✅, split panes ✅, live status ✅
2. **Sessions that stay up** — the daemon owns sessions, so processes keep running after the GUI closes ✅ (they end when the daemon stops or the machine reboots. There have been past cases of loss during updates, so no guarantee language until measurements are published — objections #1)
3. **Direct from anywhere** — 6-digit PIN phone pairing ✅, Linux server connection with no SSH and no open ports ✅

**Secondary message (hypothesis, unmeasured):** "Zero bloat" — no Electron, GPU rendering. Memory advantage over competitors has not been measured yet. Do not use competitor numbers in posts until a reproducible benchmark (objections #11) is published.

**Vendor-neutral:** Supports status detection for 16 agents including Claude Code, Codex, OpenCode, Aider, Cline, Cursor CLI, Copilot CLI, and Antigravity (per README). Not being a tool from a specific model company is an advantage from an IT purchasing perspective.

---

## 2. Target Audience

### 2-1. Segments by priority (hypothesis, before interviews)

| Rank | Segment | Characteristics | Core pain | What Ferryx provides |
|---|---|---|---|---|
| **1 (beachhead)** | Power-user individual developers / indie hackers | Run 3+ Claude Code/Codex sessions in parallel daily, Max/Pro subscribers | Window-switching fatigue, branch conflicts, not knowing whether an agent is waiting for input | Worktree automation, status display, completion notifications |
| **2** | Developers working on remote servers / GPU boxes | Homelab, cloud VMs, ML engineers | SSH disconnects, manual tmux, can't check while away | `ferryx-cli` + relay, persistent sessions, mobile |
| **3** | Startup teams adopting AI (5–50 people) | Several agents per engineer as standard practice | No team-level agent visibility, cost, or security policy | 🔮 team dashboard, shared workspaces, policies |
| **4** | Enterprise platform/DevEx teams | Security, audit, on-premises requirements | Cannot audit agent actions, reject external cloud | 🔮 self-hosted relay/hub, SSO, audit logs |

### 2-2. Key personas (hypothesis: not yet validated by interviews)

- **"Parallel Minsu" (segment 1):** Full-stack developer in their 30s, spends $100–200/month on AI subscriptions. Worn out from running 4 agents with tmux + iTerm. Gets tool information from X, Hacker News, Threads. *Decision criterion: a noticeable difference within 5 minutes of installing.*
- **"Server Jieun" (segment 2):** ML engineer. Training and agent jobs run on a remote GPU server; wants to check progress on the commute home. *Decision criteria: connection stability, security.*
- **"Lead Hyunwoo" (segment 3):** Engineering manager. Does not know how much or how team members use agents. *Decision criteria: visibility, per-seat price, passing security review.*

### 2-3. Not targeting now
- General terminal users who do not use AI agents (would mean competing head-on with Ghostty/Warp)
- Non-developers (the product assumes CLI agents)

---

## 3. Competitive Landscape

### 3-1. 2026-10-24 research (stars from GitHub API, prices from each site's link)

| Product | Form | Price | License | Stars | Threat to Ferryx |
|---|---|---|---|---|---|
| [Orca](https://orca.dev) | Electron, worktree per agent, mobile/remote | Free | MIT | 104,215 | Very high: nearly identical features and the largest community |
| [Herdr](https://herdr.dev) | Rust server owns terminals, clients attach | Free (Cloud waitlist) | Apache-2.0 | 45,599 | Very high: already owns "sessions that survive closing the app" |
| [Warp](https://www.warp.dev/pricing) | Native agent terminal, Factories | $0 / $18 / $200, Business $50 | AGPL-3.0 | 65,670 | Medium: centered on its own agent |
| [T3 Code](https://t3.codes) | Electron chat-style control panel, mobile | Free | MIT | 29,711 | High: large audience |
| [cmux](https://cmux.com) | Swift + libghostty, macOS only, iOS beta | $0 / Pro $40 / Team $60 | GPL-3.0 + BUSL | 28,378 | High: overlapping native claim |
| [Vibe Kanban](https://www.vibekanban.com/blog) | Kanban + worktrees | Company shut down (2026-04), community-maintained | Apache-2.0 | 28,442 | Low: opportunity to absorb departing users |
| [Superset](https://superset.sh/pricing) | Electron, 100+ agents, SOC 2 | $0 / Pro $20 / Team $60 | ELv2 | 15,506 | High: team/security buyers |
| [Conductor](https://www.conductor.build/pricing) | macOS, cloud VMs, multiplayer | $0 / Pro $50 / Teams $60 | Proprietary | — | High: commercial leader |
| Claude Code itself | [`--worktree`](https://code.claude.com/docs/en/common-workflows), [Remote Control](https://code.claude.com/docs/en/remote-control), [cloud sessions](https://code.claude.com/docs/en/claude-code-on-the-web) | Included in subscription | Proprietary | — | Very high |
| Codex (ChatGPT app) | [Worktrees](https://developers.openai.com/codex/app/worktrees.md), [start/approve from mobile](https://developers.openai.com/codex/app.md) | Included in subscription | Proprietary | — | Very high |

**Conclusions**
- Worktrees, phone control, and persistent sessions are now table stakes. They alone do not differentiate.
- The intersection where Ferryx can win: **native (non-Electron) + mixing 16 agents + daemon sessions + remote Linux without open ports + low price**. Orca, T3, and Superset are Electron; cmux is macOS only; Herdr is a TUI; vendor features only work with their own agent.
- Price: most competitor paid plans in the table above are $18–60/month, so Pro $8 and Team $12 are aggressive. In exchange, be clear that there are no cloud VMs.
- The [Herdr comparison page](https://herdr.dev/compare) argues that desktop apps only work while the app is open, so the Ferryx daemon must rebut this **with measurements** (linked to objection #1).

### 3-2. By type

| Type | Examples | Ferryx differentiation |
|---|---|---|
| Agent management apps | cmux, Orca, Herdr, Vibe Kanban, T3 Code | Native (non-Electron) + daemon-persisted sessions + mobile/remote servers in one product |
| AI terminal | Warp | No forced login, not tied to a specific AI, worktree-centric |
| General terminals/multiplexers | Ghostty, tmux, Zellij | Uses the same engine (libghostty) and adds agent status, worktrees, and remote control |
| Cloud agents | Codex (ChatGPT app), Devin, [Cursor Cloud Agents](https://cursor.com/docs/cloud-agent), [Copilot cloud agent](https://docs.github.com/en/copilot/concepts/agents/cloud-agent/about-cloud-agent) | Code and execution stay on my machine / my server (privacy and cost control) |

**Positioning map:** Horizontal axis "local ↔ cloud", vertical axis "single agent ↔ multi-agent operations". Ferryx occupies the **"local-first + multi-agent operations"** quadrant, and brings cloud-like convenience through remote control.

---

## 4. Revenue Model, License, Pricing (decided: 2026-10-24)

> Opening payments is on hold. The decisions below and the repository preparation (pricing table, license draft, CLA) are done and will be used as-is when payments open.

### 4-1. Current status
- Paid plans are not on sale yet. Only prices are published (Pro $8, Team launch price $12 / list price $16).
- The billing basis changed from "number of connected machines" to "right to use for company work + seats + management features" (4-3). The previous license allowed free internal company use, so companies had no reason to pay, and the plans had no management/security features a team would pay for.

### 4-2. License (changed, 2026-10-24)
1. **Core app: commercial license based on company size** (Docker Desktop model)
   - Free: individuals, education, open-source projects, nonprofits, companies with **fewer than 50 employees and contractors and under $5M annual revenue**
   - Work use by other companies: requires Team or higher subscription
   - Source remains available
2. **Team/business feature code: separate commercial license** (n8n's `.ee` model). SSO, audit logs, policy engine, etc. live in the `ee/` directory and are enabled by a license key.
3. **Self-hosted relay: remains free for everyone** (including large companies). Keeps the site's "free forever" promise.
   - Item 1 already blocks circumvention. Even if a large company runs its own relay, using the app for work requires Team or higher.
   - The loss of trust from reversing the promise outweighs the revenue gained.

**Why the free threshold is 50 people / $5M:** 10 people / $1M is too tight. Docker only introduced its [250 people / $10M threshold](https://www.docker.com/legal/docker-subscription-service-agreement/) in 2021, after its install base became huge. Ferryx is still in the spreading stage; blocking the path where startup developers bring it into their company and spread it costs more. Tightening the threshold later is possible, but blocking from the start loses the growth path.

**Alternatives compared**
| Option | Can bill companies? | Notes |
|---|---|---|
| Keep current SUL + feature billing only | Weak | Companies not using team features keep using it for free |
| FSL / Elastic License 2.0 | Weak | Both allow internal use. Intended to block competing SaaS |
| **Company-size threshold + separate commercial features (adopted)** | **Strong** | Backlash mitigated by small-company free tier, free relay, and grace period |
| Fully closed commercial | Strong | Loses source-available trust asset; not recommended |

**Repository changes** (applied to Ferryx main, 2026-10-24)
- Replaced `LICENSE` with **Ferryx License 1.0**. Applies from the next release; already distributed versions remain under SUL.
- **Transition grace period:** Large companies can use it for work for free until 90 days after Team plan sales start. While payments are on hold, nobody needs to pay.
- Replaced all SUL wording in the README (English and Chinese), Cargo metadata, and site (hero, FAQ, facts, about, pricing, comparison pages, 12 blog posts).
- `docs/legal/LICENSE_TRANSITION.md`: what changed, risks accepted, remaining work.
- `CLA.md`, `CONTRIBUTING.md`, `.github/workflows/cla.yml`: new contributions require a CLA signature.

**Legal review:** License wording gets legal review before the first paid Team sale. New contributions are accepted under the CLA.

### 4-3. Plan structure (decided, applied to site `pricing.json`)

| Plan | Price | Availability | Includes |
|---|---|---|---|
| **Free** | $0 | Available now | Individuals, education, OSS, nonprofits, small companies. All local features, 1 managed relay machine, phone connection |
| **Pro** | $8/month · $80/year | Upcoming price published | Individual power users. 10 machines + add-on packs, 🔮 mobile push, 🔮 settings sync |
| **Team** | Launch price $12/seat/month · $120/year → list price $16 · $160, minimum 3 seats | Upcoming price published | **Right to use for company work**, machine pool, org/invites/admin roles 🟡, 🔮 shared templates, 🔮 team dashboard |
| **Business** | Not published | Waitlist | 🔮 SSO, 🔮 audit logs, 🔮 policy engine, 🔮 cost reports. Minimum 10 seats |
| **Enterprise** | Quote | Contact | 🔮 SCIM, 🔮 on-premises accounts/hub, invoice billing, SLA |

- **Why Team has a launch price:** Right now Team effectively sells only "the right to use it for work". When management features ship, the price rises to list price, and launch-price subscribers are notified in advance.
- **Why Business has no price:** All its core features are 🔮. Use the waitlist to measure real demand and willingness to pay first.
- **Value basis shift:** "number of machines" → **"right to use for company work + seats + management/security features"**. Machine count remains only as a secondary basis for Pro.

### 4-4. Transition execution order
1. ~~Pricing table overhaul, license replacement, CLA introduction~~ (completed 2026-10-24, applied to main)
2. Publish the change announcement. Get legal review and consent from past external contributors
3. Activate the CLA workflow (create signature repository and secrets)
4. **[On hold] Open payments.** When opening, start with Pro. Re-select the payment provider between Paddle and Polar (4-5). Validate the payment flow and make the first revenue.
5. Ship minimal Team management features (invite/remove members, seat management)
6. Start the **90-day grace period** with the start of Team sales (already in the license). Existing users and early supporters get 50% off the first year
7. Business: waitlist → design partners → ship SSO, audit logs, policy engine in that order while publishing the price

**Billing principles:** Never lock local features for individuals. The self-hosted relay is free for everyone. What is billed is "work use by large companies" and "team management/security features".


### 4-5. Decisions revisited against external benchmarks (2026-10-24 research)

**Price position.** Comparable developer tools charge $10–20 for individual paid plans and $15–60 per seat for team plans: [Termius](https://termius.com/pricing) Pro $10 / Team $20, [Raycast](https://www.raycast.com/pricing) Pro $10 / Team $15, [Tailscale](https://tailscale.com/pricing) Standard $8, [Docker](https://www.docker.com/pricing/) Team $16, [Warp](https://www.warp.dev/pricing) Business $50, [Conductor](https://www.conductor.build/pricing)·[cmux](https://cmux.com/pricing) Team $60. Pro $8 and Team $12 (list $16) sit at the bottom of this range. With no high-cost features like cloud VMs, this position is right. But do not use "cheap" as the message; use "runs on my machine".

**Precedents for company-size thresholds.** The [Docker subscription agreement](https://www.docker.com/legal/docker-subscription-service-agreement/) is free for fewer than 250 employees and under $10M revenue. [PolyForm Small Business](https://github.com/polyformproject/polyform-licenses/blob/76a278c402bc43b8d2b561da140b0f3e17263015/PolyForm-Small-Business-1.0.0.md#L35-L37) is fewer than 100 people and under $1M. Ferryx's 50 people / $5M falls between them and stays within industry precedent.

**Lessons from license-change backlash.** Major backlash came when projects changed after growing a community under an OSI license: HashiCorp's switch to BSL drew [632 points and 731 comments on HN](https://news.ycombinator.com/item?id=37081306) and led to the OpenTofu fork, and Redis went through the [Valkey fork](https://www.linuxfoundation.org/press/linux-foundation-launches-open-source-valkey-community). n8n, which was fair-code from the start, [drew almost no reaction](https://news.ycombinator.com/item?id=30723477). Ferryx changed at 17 stars and its previous license (SUL) was also not OSI, so we consider the risk low (estimate). However, given the 9/14 MIT → SUL change history, the announcement must clearly promise "we will not change it again" and that rights to previous versions are preserved.

**Payment provider (MoR) review.** The current payment code targets Lemon Squeezy, but in its [2026-01 announcement](https://www.lemonsqueezy.com/blog/2026-update) Lemon Squeezy acknowledged slower support and updates and announced a migration to Stripe Managed Payments. However, [Stripe Managed Payments does not support Korean businesses](https://docs.stripe.com/payments/managed-payments/eligibility). So when opening payments, consider [Paddle](https://www.paddle.com/pricing) (5% + 50¢) or [Polar](https://polar.sh/resources/pricing) (5% + 50¢, 3.8% + 40¢ from the $20/month plan, supports Korean payouts) first. Keep an adapter boundary in the payment integration so the provider can be swapped.

**Conversion benchmarks.** For self-serve freemium, Free → paid conversion of 3–5% is good and 6–8% is excellent ([Lenny's Newsletter, 2023](https://www.lennysnewsletter.com/p/what-is-a-good-free-to-paid-conversion), based on ~1,000 B2B SaaS companies). The Pro conversion target of 3–5% in Section 8 follows this benchmark. No public figures specific to developer terminal tools were found.

---

## 5. Product Roadmap (for marketing and sales)

### 5-1. Packaging current features as "stories" ✅

| Story | Supporting features |
|---|---|
| "A worktree per agent, no branch conflicts" | Automatic worktree per agent, path-escape prevention |
| "Close the laptop and the agents keep working" | Daemon-owned sessions, output replay on reconnect, zero-downtime daemon replacement |
| "Press the approve button on the subway" | Mobile PIN pairing, remote web client |
| "Direct a GPU server without opening a single port" | `ferryx-cli` + relay + direct QUIC connection |
| "Point at it in the browser and ask the agent to fix it" | Design Mode: select element → capture/note → send to agent terminal (macOS, local sessions) |
| "Pick up last week's conversation" | Search and resume past agent conversations |
| "See only what's waiting, at a glance" | Attention Inbox across all workspaces (desktop) |

### 5-2. Future plans 🔮 (published on the roadmap page and in sales materials)

**Now (0–3 months) — for converting individual users**
- 🔮 **Mobile push notifications** "Your agent is waiting for you" (subscription store exists, no sender 🟡)
- 🔮 **Native mobile approval/chat screen** (one-tap approval of permission requests on the phone)
- 🔮 **Worktree disk dashboard / cleanup** (scoping document exists)
- 🔮 **Agent status watchdog** (automatic detection of stuck agents)

**Next (3–6 months) — strengthening Pro value**
- 🔮 **Agent cost/token dashboard** — usage and estimated cost per agent and project
- 🔮 **Agent orchestration templates** — recipes that chain "plan → implement → review" agents in sequence (reusing the existing DAG viewer)
- 🔮 **Public control API / CLI** — create, start, and stop agents externally (`ferryx_scope/control` not wired up 🟡)
- 🔮 **Result comparison view** — give the same task to 2–3 agents, compare diffs side by side, and adopt one
- 🔮 **Session share links** — share an in-progress agent session read-only with a colleague

**Later (6–12 months) — for Team/Enterprise sales**
- 🔮 **Team dashboard** — team-wide agent activity, wait time, bottlenecks
- 🔮 **Policy engine** — block or require approval for risky commands (`rm -rf`, `git push --force`, secret access)
- 🔮 **Audit logs** — record and export which agent ran which command
- 🔮 **Self-hosted hub**, SSO/SCIM (self-hosted relay already exists ✅)
- 🔮 **ferryx-hub managed service** — "fix this issue" in Slack/Discord → assigned to an agent on a team member's machine
- 🔮 **Cloud execution nodes (optional)** — managed Linux workers that keep running when my machine is off

> **Roadmap labeling rule:** In marketing materials, 🔮 items must always be marked "Coming soon / Roadmap". Enterprise contracts must not include future features as binding commitments. Presenting unreleased features as current creates trust and legal risk.

---

## 6. GTM Execution Plan by Phase

### Phase 0 — Preparation (2–4 weeks)
- **Build evidence:** publish a benchmark against Orca, cmux, and Warp for memory, startup time, and 8 agents running concurrently (with reproduction scripts)
- **Site cleanup:** 30-second demo video (4 agents in parallel → close laptop → approve on phone), comparison page, privacy statement page, public roadmap
- Publish a **headless Linux server guide** (the feature exists but is not known)
- **Instrumentation:** install → first agent run → first worktree → first remote pairing funnel (opt-in, anonymous)

### Phase 1 — Community launch (1–3 months) · Goal: acquire individual users
- **Show HN** (title per skills/channel-post.md), qualifying subreddits (r/ClaudeAI, etc.). Product Hunt is postponed until there is a following (launch-7day.md)
- **Ride the agent ecosystem:** expose Ferryx naturally in Claude Code/Codex tips content. Search-traffic articles such as "Guide to running Claude Code in parallel"
- **Target the Korean market at the same time:** Threads, GeekNews, Discord communities. Build-in-public with the developer personally sharing the build process
- **Creators:** reach out to AI coding YouTubers/streamers. Promise a free 1-year Pro code when payments open (Pro not currently on sale)
- **Open Discord:** bug reports and feature voting → publicly reflected in the roadmap

### Phase 2 — Monetization (3–6 months) · Goal: validate Pro conversion
- Open Pro alongside the managed relay and push notification launch
- In-app upsell points: when adding a third remote server, when connecting from a phone on an external network for the first time
- 5 user case studies (indie hacker, ML engineer, startup CTO)

### Phase 3 — Team expansion (6–12 months) · Goal: bottom-up → team contracts
- **PLG signal:** 3+ users with the same company email domain → sales outreach
- Team plan 14-day free trial, self-serve payment
- Co-design the team dashboard and policy engine with 5 design-partner teams (validate by pre-selling roadmap features)
- Security review materials: data flow diagram, what data the relay can/cannot see, SOC 2 roadmap

### Phase 4 — Enterprise (after 12 months)
- Enterprise with self-hosting, SSO, audit logs
- Partners: AI adoption consultancies, cloud marketplaces (AWS/Azure)
- Distribution channels such as the Microsoft Store (submission prep document already exists)

---

## 7. Sales Materials

**Pitch flow (5-minute demo)**
1. Problem: "Agents got fast, but the human is the bottleneck" — window switching, conflicts, waiting
2. Demo: 4 agents running concurrently → automatic worktrees → status display
3. Demo: close laptop → approve a waiting agent from the phone
4. Demo: connect a remote GPU server without opening ports
5. Roadmap: team dashboard, policies, audit logs 🔮 → "We're looking for partners to design this with"

**Handling objections**
| Objection | Response |
|---|---|
| "tmux is enough" | tmux only keeps sessions alive. Worktrees, agent status, and mobile control you have to build yourself |
| "Claude Code is already adding parallel features" | Ferryx is not tied to a specific company. It fits teams that mix Codex and OpenCode |
| "Doesn't code leave through the relay?" | Direct connection (QUIC) is used when possible, and the self-hosted relay is free for everyone. Data flow documentation to be published 🔮 |
| "A product from a small team feels risky" | Source available, public roadmap, published stability record such as zero-downtime daemon replacement |

---

## 8. Key Metrics (North Star and supporting metrics)

> All targets below are hypotheses. They will be reset based on the 7-day loop results (metrics/). The 3–5% conversion rate follows the [self-serve freemium benchmark](https://www.lennysnewsletter.com/p/what-is-a-good-free-to-paid-conversion).

- **North Star:** weekly "parallel agent hours" — total time during which 2+ agents ran concurrently
- Activation: share of installs that run 2+ agents concurrently within 24 hours (target 40%)
- Retention: week-4 weekly active user rate (target 35%)
- Remote adoption: share of users who connected mobile or a remote server
- Revenue: Free → Pro conversion rate (target 3–5%), number of Team domain signals
- 12-month goals (hypothesis): 10K weekly actives, 400 paid Pro users, 10 Team contracts

---

## 9. Risks and Responses

| Risk | Response |
|---|---|
| Model companies ship parallel execution/mobile themselves | Differentiate with vendor neutrality + remote servers + team policy layer |
| Community backlash to the license change | Keep individuals/small companies free, 90-day grace period, discount for existing users, explain the reasons in a public post (Section 4) |
| Billing circumvention via self-hosting | The app license is based on company size, so large companies need Team or higher even if they run their own relay. The relay itself stays free |
| Overmarketing future features | Mandatory 🔮 labeling, no future-feature commitments in contracts |
| Cross-platform quality gaps (Design Mode is macOS only) | Publish a per-platform feature table on the site |
| Inconsistent repository URL / doc versions (`ferryx/ferryx` vs `Indosaram/ferryx`, protocol v5/v6) | Clean up before launch |
| Support burden for a solo/small team | Discord community support, priority support for paid plans only |

---

## 10. Next 4 Weeks

0. License change announcement, activate the CLA workflow (pricing table, license replacement, and CLA documents are done, 4-4). Opening payments is on hold
1. Publish comparison benchmark scripts and results
2. 30-second demo video + replace landing page messaging
3. Public roadmap page (Now/Next/Later, 🔮 labels)
4. Headless server guide + privacy page
5. Confirm Show HN / GeekNews schedule (Product Hunt after gaining followers)
6. Pro waitlist + publish Early Supporter pricing

---

## 11. Link to This Week's GTM Loop

[loop/LOOP.md](../loop/LOOP.md) is the procedure for actually running Phases 0–1 of this strategy over 7 days, and the Section 9 risks and the objection list in [objections.md](objections.md) are the loop's inputs. Launch copy principles: "source-available" instead of "open source", no guarantee language, "Coming soon" for unreleased features.

### Unverified assumptions
- Prices are decided but not market-validated. Metric targets and segment sizes are **hypotheses** set without market research. They need validation through a waitlist and 10–20 interviews.
- Stars and prices in the 3-1 table were rechecked on 2026-10-24. User complaints in Sections 2 and 3-2 cite the 2026-09 internal analysis and were not rechecked.
- Current features were confirmed only from documentation and code structure; they were not built or run.
