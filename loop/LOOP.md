# Daily GTM Loop — 마스터 스킬

이 파일은 사람과 에이전트가 매일 같은 순서로 실행하는 절차다. 하루 한 번(오전 9시 KST) 시작하고, 게시가 있는 날은 게시 후 REPLY 단계를 사람이 직접 맡는다.

## 실행 환경

Ferryx 안에서 워크스페이스 `ferryx-gtm`을 열고 아래 패널을 띄운다. 패널마다 별도 워크트리를 쓰므로 에이전트끼리 파일을 덮어쓰지 않는다.

| 패널 | 에이전트 | 스킬 |
|---|---|---|
| A | Claude Code | skills/measure.md → skills/retro.md |
| B | Codex | skills/listen.md |
| C | Claude Code | skills/objection-fix.md |
| D | Codex | skills/channel-post.md |
| 사람 | — | skills/reply.md, 최종 게시 버튼 |

루프 실행 화면은 녹화해서 콘텐츠 소재로 쓴다.

## 순서

1. **MEASURE** (`skills/measure.md`): `bun scripts/snapshot.ts` → `metrics/day-N.json`. 전날 대비 증감 계산.
2. **LISTEN** (`skills/listen.md`): 어제 게시물의 댓글, GitHub 이슈, Discord, 언급 검색 결과를 모아 반론·요청·칭찬으로 분류.
3. **OBJECTION → FIX → STORY** (`skills/objection-fix.md`): `strategy/objections.md`에서 오늘 가장 큰 반론 하나를 골라 고치거나(작은 수정·문서) 정직하게 인정하고, 결과를 다음 게시물 소재로 만든다.
4. **SHIP CONTENT** (`skills/channel-post.md`): 에이전트가 오늘 채널의 규칙·소재·사실 근거를 정리 → **사람이 본문을 직접 씀** → `channels/rules.md` 점검 → 사람이 게시.
5. **REPLY** (`skills/reply.md`): 게시 후 6시간 동안 모든 댓글에 사람이 답한다. 에이전트는 사실 확인과 답변 초안만.
6. **RETRO** (`skills/retro.md`): `log/day-N.md` 작성. 무엇이 효과 있었는지, 내일 바꿀 것 하나. 루프 자체를 바꿨으면 `loop/CHANGELOG.md`에 기록.

## 불변 규칙

- 투표·스타 요청, 다중 계정, 같은 글 재게시 금지.
- 출시되지 않은 기능을 현재 기능처럼 쓰지 않는다 (로드맵 항목은 "Coming soon").
- "never lose work" 같은 보장 표현 금지. 측정한 것만 수치로 말한다.
- 게시물과 댓글은 사람이 직접 쓰고 직접 게시한다. 에이전트가 쓴 문장을 그대로 올리지 않는다(HN 등 LLM 글 금지).
- 화면 녹화 전 토큰·이메일·사설 경로가 보이지 않는지 점검한다.
- 매일 `day-N: <루프 변경 한 줄>` 형식으로 커밋한다.
