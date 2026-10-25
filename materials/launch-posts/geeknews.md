# GeekNews Show GN

- Only if the account is at least 1 week old.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.

**Submit link:** https://news.hada.io/write

---

제목:

Ferryx - 여러 코딩 에이전트를 각자 git worktree에서 동시에 돌리는 네이티브 터미널

URL: https://github.com/Indosaram/ferryx

본문:

Claude Code랑 Codex를 한 레포에서 같이 돌리다 보니 계속 같은 문제가 생겼습니다. 같은 체크아웃에서 서로 파일을 고쳐놔서 손으로 정리해야 했고, 터미널 앱을 닫거나 앱이 죽으면 돌던 작업도 같이 죽었습니다.

그래서 Ferryx를 만들었습니다. 에이전트마다 git worktree와 브랜치를 따로 만들어 줍니다. 터미널은 창이 아니라 Rust로 만든 백그라운드 데몬이 들고 있어서, 앱을 닫아도 에이전트는 계속 돕니다. 다시 열면 그동안 놓친 출력이 다시 나옵니다.

어떤 에이전트가 작업 중인지, 놀고 있는지, 내 답을 기다리는지도 보여주고 답이 필요하면 알림을 줍니다. Claude Code, Codex, Cursor, OpenCode, Copilot CLI 등에서 동작합니다. 폰에서 로그인하면 밖에서도 세션을 보고 입력할 수 있습니다. 데스크톱이 릴레이로 먼저 연결하는 방식이라 포트를 열 필요가 없고, 릴레이는 직접 띄울 수도 있습니다.

Tauri에 libghostty 터미널 코어, wgpu 렌더링이라 Electron은 안 씁니다.

미리 말씀드릴 점도 있습니다. 오픈소스가 아니라 source-available이고, 개인과 50인 미만·매출 500만 달러 미만 회사는 무료입니다. Windows 빌드는 아직 코드 서명이 없어서 SmartScreen 경고가 뜹니다. Linux/Windows ARM64 빌드는 없습니다. 그리고 혼자 만들고 있습니다.

가입 없이 받을 수 있습니다: https://github.com/Indosaram/ferryx/releases/latest

worktree나 tmux로 이미 이렇게 쓰고 계신 분들은 이걸로 바꿀 만한지 아닌지 궁금합니다.
