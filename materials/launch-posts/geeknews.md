# GeekNews Show GN

- Only if the account is at least 1 week old.
- Add one concrete story of your own (e.g. a specific time agents clobbered each other or a run died) in your words. It is the strongest human signal.

**Submit link:** https://news.hada.io/write

---

제목:

Ferryx - Windows·Linux에서도 쓸 수 있는 코딩 에이전트용 네이티브 터미널

URL: https://github.com/Indosaram/ferryx

본문:

Claude Code, Codex 같은 에이전트 여러 개를 터미널 탭에 띄워 놓고 쓰는 용도로 만든 데스크톱 터미널입니다. macOS, Windows, Linux에서 다 돕니다.

특히 신경 쓴 건 이 두 개예요.

1. 앱을 닫아도 에이전트가 안 죽습니다. 터미널은 창이 아니라 Rust로 만든 백그라운드 데몬이 들고 있어서, 앱을 껐다 켜면 돌던 세션에 그대로 다시 붙고 그동안 놓친 출력도 다시 보여줍니다.
2. 원격 Linux 서버를 SSH 없이 붙입니다. 서버에 ferryx-cli를 깔면 서버 쪽에서 릴레이로 먼저 연결하는 방식이라 포트를 열거나 공인 IP가 없어도 됩니다. 릴레이는 직접 띄울 수도 있습니다.

그 밖에 탭·분할 창, 어떤 에이전트가 내 답을 기다리는지 표시·알림, 폰 브라우저에서 세션 보기, 탭마다 git worktree 따로 쓰기 정도가 있습니다. Tauri에 libghostty, wgpu 렌더링이라 Electron은 안 씁니다.

그리고 오해 없게: 오픈소스가 아니라 source-available이고 개인과 소규모 회사는 무료입니다. 혼자 만들고 있고, Orca처럼 에디터나 diff 리뷰가 들어 있는 IDE는 아닙니다.

받기: https://github.com/Indosaram/ferryx/releases/latest

지금 쓰시는 터미널로 에이전트 돌리면서 제일 불편했던 거 알려주시면 우선순위에 넣겠습니다.
