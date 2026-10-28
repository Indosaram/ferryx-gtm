# Supervisor launch (post on the day the release that contains it ships)

- Do not post before a release containing agent_control / supervisor ships. The current download, v2026.10.11.1, does not have it.
- The "answers routine prompts for you" wording is false. Since b2639480 (10/25) the hub never answers for the owner: `security.rs::auto_answer` always returns EscalateOwner or Hold. If that changes before the release, rewrite this file to match the code.
- Re-check each line below against the release tag on the day.
- GeekNews: a repost needs a "big change". Post it as a new feature announcement, not the same intro.

---

## X (EN)

New in Ferryx: a supervisor for your agent tabs.

When Claude Code or Codex stops to ask something, it sends the question to your phone or Slack. Reply there and it types the answer into that tab, then checks the agent actually picked it up. It never answers for you.

https://github.com/Indosaram/ferryx

## GeekNews / Threads (KO)

Ferryx에 supervisor를 넣었습니다.

Claude Code나 Codex가 멈추고 뭘 물어보면, 그 질문을 폰이나 Slack으로 보내줍니다. 거기서 답하면 해당 탭에 대신 입력하고, 에이전트가 실제로 다음 작업을 시작했는지까지 확인합니다. 제가 고르지 않은 답을 알아서 입력하는 일은 없습니다.

탭마다 목표를 걸어 두면 지금 어디까지 왔고 다음에 뭘 할지도 보여줍니다. 제가 키보드를 치고 있으면 끼어들지 않고, Take over 누르면 바로 멈춥니다.

https://github.com/Indosaram/ferryx

## Claims to verify on release day

| Claim | Where to check |
|---|---|
| Questions forwarded to phone/Slack/Inbox | `7724e38f` (Inbox), `1d85bb29` (phone home), hub Slack routing `44c0f3de` |
| Confirms the instruction started a turn | `9123ede8`, `agent_control/delivery.rs` |
| Never auto-answers | `crates/ferryx-hub/src/security.rs` `auto_answer` |
| Pauses while the human types; Take over | `HUMAN_TYPING_WINDOW_MS` in `agent_control/policy.rs` |
| Lane goal and next step | `d1404c91`, `29355ae7` |
| Default off, toggle in Settings | `1fc72124` (users must turn it on; mention this in replies) |
