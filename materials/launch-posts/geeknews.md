# GeekNews Show GN

- Only if the account is at least 1 week old. Submit as Show GN.

**Submit link:** https://news.hada.io/write

---

제목:

Ferryx - 여러 코딩 에이전트를 각자 git worktree에서 동시에 돌리는 네이티브 터미널

URL: https://github.com/Indosaram/ferryx

본문:

혼자 만들고 있는 Ferryx를 소개합니다. Claude Code, Codex 같은 CLI 코딩 에이전트 여러 개를 한 레포에서 동시에 돌리기 위한 데스크톱 터미널 워크스페이스입니다.

만든 이유
- 한 체크아웃에서 에이전트 두 개를 돌리면 서로 파일과 커밋을 덮어씁니다.
- 터미널 앱을 닫으면 몇 시간짜리 에이전트 작업이 같이 죽었습니다.

주요 기능
- 에이전트마다 별도의 git worktree와 브랜치
- 터미널을 창이 아니라 백그라운드 Rust 데몬이 소유합니다. 창을 닫거나 UI가 죽어도 에이전트는 계속 돌고, 다시 붙으면 놓친 출력이 재생됩니다.
- Claude Code, Codex, Cursor, OpenCode, Copilot CLI 등의 상태 감지(작업 중/입력 대기/유휴)와 알림
- 폰이나 브라우저에서 계정으로 로그인해 세션 확인과 입력. 호스트가 릴레이로 바깥으로 연결하므로 인바운드 포트나 공인 IP가 필요 없고, 릴레이를 직접 띄울 수도 있습니다.
- Rust, Tauri v2, libghostty, wgpu 기반이고 Electron을 쓰지 않습니다.

한계
- 오픈소스가 아니라 source-available(Ferryx License)입니다. 개인과 50인 미만·매출 500만 달러 미만 회사는 무료입니다.
- Windows 설치 파일은 아직 코드 서명이 없어 SmartScreen 경고가 뜹니다.
- Linux/Windows ARM64 빌드는 없습니다.
- 1인 프로젝트입니다.

가입 없이 macOS, Windows, Linux용으로 바로 받을 수 있습니다: https://github.com/Indosaram/ferryx/releases/latest

worktree를 직접 관리하거나 tmux로 에이전트를 돌리시는 분들 의견이 특히 궁금합니다.
