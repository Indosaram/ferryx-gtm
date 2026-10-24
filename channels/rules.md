# 채널별 규칙과 금지 사항

2026-10-24에 각 공식 페이지를 확인했다(Reddit은 2026-07~08 아카이브 사본). 게시 직전에 다시 확인한다.

| 채널 | 핵심 규칙 (출처) | 우리 운영 |
|---|---|---|
| Hacker News (Show HN) | 직접 실행해 볼 수 있는 것만, 랜딩·가입 페이지는 안 됨. 친구에게 투표·댓글 요청 금지. **LLM으로 쓴 글·댓글 금지**. 회사 계정명 금지. 같은 글 삭제 후 재게시 금지 ([showhn](https://news.ycombinator.com/showhn.html), [guidelines](https://news.ycombinator.com/newsguidelines.html), [dang의 팁](https://news.ycombinator.com/item?id=22336638)) | 사람이 직접 씀. 제목에 라이선스 용어를 넣지 않고 본문 첫 문단에 source-available 명시("open source"라고 쓰면 모더레이터가 고침: [사례](https://news.ycombinator.com/item?id=42824568)). 프로필에 이메일 기재. 10/26 22:00 KST = 13:00 UTC, 연구상 좋은 시간대 12~17 UTC 안 ([arXiv 2511.04453](https://arxiv.org/abs/2511.04453)) |
| HN 재도전 | 1년 내 큰 관심을 못 받은 글은 소수의 재게시 허용 ([FAQ](https://news.ycombinator.com/newsfaq.html)). second-chance pool 추천은 hn@ycombinator.com ([설명](https://news.ycombinator.com/item?id=26998308)) | 같은 글 재게시 대신 다른 각도의 글. 필요하면 second-chance 요청 메일 1회 |
| r/ClaudeAI | 직접 만든 Claude 관련 도구 홍보 허용, Claude가 어떻게 도왔는지 설명, 무료로 써볼 수 있음을 명시, **피드 게시에 카르마 50 초과 필요** ([규칙 사본](http://web.archive.org/web/20260823233716/https://old.reddit.com/r/ClaudeAI/about/rules/)) | 카르마 조건 확인 후에만 |
| r/LocalLLaMA | 자기 홍보는 활동의 10% 이하, 소속 공개, LLM 생성 글 금지 ([사본](http://web.archive.org/web/20260807221923/https://old.reddit.com/r/LocalLLaMA/about/rules/)) | 로컬 모델(Ollama 등) 연동 이야기가 있을 때만 |
| r/ChatGPTCoding | 홍보 글은 자기 홍보 스레드로 ([사본](http://web.archive.org/web/20260727134012/https://old.reddit.com/r/ChatGPTCoding/about/rules)) | 자기 홍보 스레드에만 |
| r/rust | Rust 주제여야 함, 저품질·AI 생성 글 삭제 ([사본](http://web.archive.org/web/20260811152833/https://old.reddit.com/r/rust/about/rules)) | libghostty·wgpu·데몬 구조 기술 글로만 |
| r/programming | **"I made this" 프로젝트 홍보 금지**, 기술 글만 ([사본](http://web.archive.org/web/20260811153143/https://old.reddit.com/r/programming/about/rules)) | 기술 글(벤치마크 방법론 등)만, 10/27 이후 |
| r/commandline | 생성형 AI 관련 프로젝트 금지(유명 예외만), 30일 미만 프로젝트 금지 ([사본](http://web.archive.org/web/20260811152913/https://old.reddit.com/r/commandline/about/rules)) | **사용 안 함** |
| r/opensource | 링크한 코드는 **OSI 라이선스 필수** ([사본](http://web.archive.org/web/20260726134356/https://old.reddit.com/r/opensource/about/rules/)) | **사용 안 함** (Ferryx License는 OSI 아님) |
| Lobsters | **가입 후 70일간 자기 홍보 게시 불가**, 새 계정은 처음 보는 도메인·show 태그 게시 불가, 초대제 ([about](https://lobste.rs/about), [코드](https://github.com/lobsters/lobsters/blob/407536444934ac7d78f4ce1c18f228e3891a8663/app/models/user.rb#L178)) | 이번 주는 댓글 참여만. 기존 회원이 자기 판단으로 올리는 경우만 |
| GeekNews | **가입 1주일 뒤부터 링크 등록 가능**. 자기 제품은 반드시 Show GN으로, 제목 "프로젝트명 - 핵심 기능", 지인 추천 요청·다중 계정 금지, 같은 프로젝트 일정 기간 재등록 불가 ([guidelines](https://news.hada.io/guidelines), [Show GN](https://news.hada.io/blog/show)) | 계정 나이 1주일 이상인지 먼저 확인. 아니면 지인 대리 게시가 아니라 일정을 미룸 |
| Product Hunt | 직접 올려도 불리하지 않음, 투표 요청 금지(방문·댓글 요청은 가능), 메인 노출은 편집 선정 ([launch 가이드](https://www.producthunt.com/launch/before-launch)) | 7일 이후로 연기 (팔로워 없음) |

## 리스트·뉴스레터

| 대상 | 조건 (출처) | 판단 |
|---|---|---|
| [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | 14일 이상 꾸준한 커밋 또는 스타 100+, 이슈 폼으로만, 사람이 작성 ([CONTRIBUTING](https://github.com/hesreallyhim/awesome-claude-code/blob/15a8bf8626eaa14ad52ff118e53ace29a4cca244/CONTRIBUTING.md)) | 커밋 이력 충족 → 10/24 제출 |
| [Terminal Trove](https://terminaltrove.com/post/) | 미리보기 이미지·GIF 필요, 비공개 라이선스도 가능 (사이트가 자동 접근을 403으로 막아 [2026-07 아카이브 사본](http://web.archive.org/web/20260713020823/https://terminaltrove.com/post/)으로 확인) | 10/24 제출 |
| [Console.dev](https://console.dev/selection-criteria) | 개발자용, 셀프 가입, 문서 양호. 이메일 제출 | 10/24 제출 |
| [Changelog News](https://changelog.com/news/submit) | 자기 작업 제출 환영, 상용 제품은 제외 | 해당 없음 (유료 가격이 공개된 상용 제품). 벤치마크 방법론 같은 기술 글이 생기면 그 글만 제출 검토 |
| awesome-cli-apps | 자유/오픈소스 라이선스 필수 ([contributing](https://github.com/agarrharr/awesome-cli-apps/blob/1f85964177eefd08469005b0c47d09c7c729cfd6/contributing.md)) | 해당 없음 |
| awesome-tuis | 레포 6개월 이상 | 해당 없음 (TUI도 아님) |

## 공통 금지

- "open source" 표기 → "source-available"
- 에이전트가 쓴 게시글·댓글을 그대로 올리기
- 출시 전 기능을 현재 기능처럼 표기, 측정하지 않은 경쟁사 성능 수치
- 투표 요청, 다중 계정, 자동 게시 봇
