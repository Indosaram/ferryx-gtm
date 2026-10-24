# Ferryx GTM Agentic Loop

> Clone Loop Day in Seoul 제출 레포 · 운영 기간 2026-10-24(토) ~ 2026-10-31(토) 18:00 KST

[Ferryx](https://github.com/Indosaram/ferryx)는 Claude Code·Codex 같은 CLI 코딩 에이전트 여러 개를 한 화면에서 병렬로 돌리는 네이티브 데스크톱 작업 공간입니다. 에이전트마다 Git 워크트리를 따로 쓰고, 데몬이 세션을 붙잡아 두며, 휴대폰이나 원격 리눅스 서버에서도 지휘할 수 있습니다. Electron은 쓰지 않습니다.

이 레포는 실행 프로그램이 아니라, 7일 동안 **직접 반복 운영하는 GTM 루프의 방법론**(Markdown 스킬 + 지표 수집 스크립트 + 일일 로그)입니다.

## 7일 목표 (2026-10-31 18:00 KST 기준)

기준선은 2026-10-24 17:05 KST에 `gh api`로 측정했습니다([metrics/baseline.json](metrics/baseline.json)).

| 지표 | 기준선 (10/24) | 목표 | 스트레치 |
|---|---|---|---|
| GitHub 스타 | 17 | **300** | 1,000 |
| GitHub 14일 순방문자 (traffic uniques) | 11 | 1,500 | 5,000 |
| 릴리스 누적 다운로드 | 2,692 | +600 | +2,000 |
| Discord 신규 멤버 | 측정 시작 | 50 | 150 |
| Pro/Team 대기 명단 (매출 선행지표) | 0 | 40 | 100 |
| 외부 게시물·언급 (HN/Reddit/GeekNews/뉴스레터) | 0 | 10 | 25 |

**매출에 대해 솔직하게:** 유료 플랜은 아직 판매 전입니다(가격만 공개: Pro $8/월, Team 출시가 $12/좌석/월). 그래서 7일 매출 목표는 $0이고, 대신 **대기 명단 가입**을 매출 선행지표로 씁니다. 결제를 이번 주에 열지 여부는 Day 4 회고에서 대기 명단 수치를 보고 결정합니다([strategy/GTM.md](strategy/GTM.md) 4장).

## 루프 한 장 요약

```
 ┌─ 1. MEASURE ── 지표 스냅샷 (scripts/snapshot.ts) ──────────────┐
 │                                                                 │
 │  2. LISTEN ── 어제 게시물 댓글·이슈·"안 쓰는 이유" 수집         │
 │                                                                 │
 │  3. OBJECTION → FIX → STORY  (이 루프의 핵심)                   │
 │     가장 많이 나온 반대 이유 1개 → 제품/문서 수정 → 그 수정을   │
 │     다음 게시물의 소재로 사용                                    │
 │                                                                 │
 │  4. SHIP CONTENT ── 채널별 규칙에 맞는 게시 1~3건               │
 │     (Ferryx 안에서 에이전트 N개를 병렬로 돌려 초안 작성)        │
 │                                                                 │
 │  5. REPLY ── 게시 후 6시간 모든 댓글에 사람이 답변              │
 │                                                                 │
 └─ 6. RETRO ── log/day-N.md 기록, 다음 날 가설·채널 조정 ─────────┘
```

### 이 루프가 다른 점

1. **제품이 곧 루프의 실행 환경이다 (dogfooding loop).** 루프의 에이전트들(채널 리서치, 초안, 반론 검토, 지표 분석)을 Ferryx 안에서 패널별·워크트리별로 병렬 실행합니다. 루프를 돌리는 화면 녹화가 그대로 데모 영상과 게시물 소재가 됩니다. "에이전트로 홍보하는 에이전트 도구"를 그 도구 자체로 증명합니다.
2. **반대 이유를 연료로 쓴다 (objection-driven loop).** 출시 전에 회의적 사용자 관점의 "Ferryx를 쓰지 않을 이유" 11가지를 먼저 작성했습니다(세션 유실 이력, 비 OSI 라이선스, 벤더 기능 흡수 등). 매일 가장 큰 반대 이유 하나를 실제로 고치거나 정직하게 인정하고, 그 과정을 콘텐츠로 냅니다. 개발자 커뮤니티는 과장보다 정직한 한계 공개에 반응한다는 가설을 검증합니다.
3. **팔로워 0 전제.** 기존 영향력이 없으므로 알고리즘 채널(HN 첫 페이지, Reddit, GeekNews, GitHub Trending)과 남의 채널(뉴스레터, awesome 리스트, 크리에이터)만 씁니다. 각 채널의 게시 규칙(계정 나이, 자기 홍보 비율, Lobsters 초대제 등)을 스킬에 명시해 규칙 위반으로 계정을 잃지 않게 합니다.

## 레포 구조

| 경로 | 내용 |
|---|---|
| [strategy/GTM.md](strategy/GTM.md) | 전체 GTM 전략: 포지셔닝, 타겟, 경쟁, 가격·라이선스, 로드맵, 단계별 계획, 리스크 |
| [strategy/launch-7day.md](strategy/launch-7day.md) | 이번 7일 일정과 중간 판단 규칙 |
| [strategy/objections.md](strategy/objections.md) | "쓰지 않을 이유" 목록과 대응 상태 (루프가 매일 갱신) |
| [loop/LOOP.md](loop/LOOP.md) | 하루 루프 운영 절차 (에이전트가 읽고 실행하는 마스터 스킬) |
| [skills/](skills/) | 단계별 스킬: measure, listen, objection-fix, channel-post, reply, retro |
| [channels/rules.md](channels/rules.md) | 채널별 게시 규칙과 금지 사항 |
| [scripts/snapshot.ts](scripts/snapshot.ts) | GitHub 지표 스냅샷 (`bun scripts/snapshot.ts`) |
| [metrics/](metrics/) | 기준선과 일일 스냅샷 |
| [log/](log/) | 일일 운영 로그와 회고 |

## 평가 기준과의 대응

| 심사 기준 | 이 레포에서 확인할 곳 |
|---|---|
| 제품·고객에 맞는 전략인가 | strategy/GTM.md 1~3장, channels/rules.md |
| 실제 반복 운영했는가 | log/day-*.md, metrics/*.json (매일 커밋) |
| 중간 결과로 루프가 개선됐는가 | 각 log의 "루프 변경" 섹션, loop/CHANGELOG.md |
| 목표 대비 성과 | 위 목표 표 ↔ metrics/day-7.json |
