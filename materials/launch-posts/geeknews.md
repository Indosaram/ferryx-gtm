# GeekNews Show GN

- Only if the account is at least 1 week old.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.

**Submit link:** https://news.hada.io/write

---

제목:

Ferryx - 코딩 에이전트 여러 개를 띄워 쓰기 위한 네이티브 터미널 멀티플렉서

URL: https://github.com/Indosaram/ferryx

본문:

Ferryx는 터미널 멀티플렉서입니다. tmux처럼 탭과 분할 창으로 터미널 여러 개를 한 화면에 띄우는데, 데스크톱 앱이고 Claude Code나 Codex 같은 코딩 에이전트를 여러 개 띄워 놓고 쓰는 상황에 맞춰 만들었습니다.

터미널은 창이 아니라 Rust로 만든 백그라운드 데몬이 들고 있습니다. 그래서 앱을 닫아도 셸과 그 안에서 돌던 에이전트는 계속 돌고, 다시 열면 그대로 이어서 붙습니다.

창마다 에이전트가 작업 중인지, 놀고 있는지, 내 답을 기다리는지 표시하고, 답이 필요하면 알림을 줍니다. 폰에서 로그인하면 밖에서도 세션을 보고 입력할 수 있습니다. 데스크톱이 릴레이로 먼저 연결하는 방식이라 포트를 열 필요가 없고, 릴레이는 직접 띄울 수도 있습니다.

Tauri에 libghostty 터미널 코어, wgpu 렌더링이라 Electron은 안 씁니다.

미리 말씀드릴 점도 있습니다. 오픈소스가 아니라 source-available이고, 개인과 50인 미만·매출 500만 달러 미만 회사는 무료입니다. Windows 빌드는 아직 코드 서명이 없어서 SmartScreen 경고가 뜹니다. Linux/Windows ARM64 빌드는 없습니다. 그리고 혼자 만들고 있습니다.

가입 없이 받을 수 있습니다: https://github.com/Indosaram/ferryx/releases/latest

tmux나 다른 터미널로 에이전트 여러 개를 돌리고 계신 분들은 어떤 점이 불편한지 궁금합니다.
