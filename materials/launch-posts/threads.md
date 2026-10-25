# Threads (Korean)

- 292 chars (limit 500).

**Submit link:** https://www.threads.net/intent/post?text=Claude%20Code%EB%9E%91%20Codex%EB%A5%BC%20%ED%95%9C%20%EB%A0%88%ED%8F%AC%EC%97%90%EC%84%9C%20%EA%B0%99%EC%9D%B4%20%EB%8F%8C%EB%A6%AC%EB%A9%B4%20%EC%84%9C%EB%A1%9C%20%ED%8C%8C%EC%9D%BC%EC%9D%84%20%EB%8D%AE%EC%96%B4%EC%93%B0%EA%B3%A0%2C%20%ED%84%B0%EB%AF%B8%EB%84%90%20%EC%95%B1%EC%9D%84%20%EB%8B%AB%EC%9C%BC%EB%A9%B4%20%EB%AA%87%20%EC%8B%9C%EA%B0%84%EC%A7%9C%EB%A6%AC%20%EC%9E%91%EC%97%85%EC%9D%B4%20%EB%82%A0%EC%95%84%EA%B0%80%EB%8D%94%EB%9D%BC%EA%B3%A0%EC%9A%94.%0A%0A%EA%B7%B8%EB%9E%98%EC%84%9C%20Ferryx%EB%A5%BC%20%EB%A7%8C%EB%93%A4%EC%97%88%EC%8A%B5%EB%8B%88%EB%8B%A4.%0A-%20%EC%97%90%EC%9D%B4%EC%A0%84%ED%8A%B8%EB%A7%88%EB%8B%A4%20%EB%B3%84%EB%8F%84%20git%20worktree%0A-%20%EC%B0%BD%EC%9D%84%20%EB%8B%AB%EC%95%84%EB%8F%84%20%EB%B0%B1%EA%B7%B8%EB%9D%BC%EC%9A%B4%EB%93%9C%20%EB%8D%B0%EB%AA%AC%EC%9D%B4%20%EC%97%90%EC%9D%B4%EC%A0%84%ED%8A%B8%EB%A5%BC%20%EA%B3%84%EC%86%8D%20%EB%8F%8C%EB%A6%BC%0A-%20%ED%8F%B0%EC%97%90%EC%84%9C%20%EB%A1%9C%EA%B7%B8%EC%9D%B8%ED%95%B4%EC%84%9C%20%EC%A7%84%ED%96%89%20%EC%83%81%ED%99%A9%20%ED%99%95%EC%9D%B8%2C%20%EC%9E%85%EB%A0%A5%EA%B9%8C%EC%A7%80%0A%0ARust%20%2B%20libghostty%2C%20Electron%20%EC%97%86%EC%9D%8C.%20%EA%B0%9C%EC%9D%B8%EC%9D%80%20%EB%AC%B4%EB%A3%8C(source-available)%EA%B3%A0%20%EA%B0%80%EC%9E%85%20%EC%97%86%EC%9D%B4%20%EB%B0%9B%EC%9D%84%20%EC%88%98%20%EC%9E%88%EC%96%B4%EC%9A%94.%0Ahttps%3A%2F%2Fgithub.com%2FIndosaram%2Fferryx

---

Claude Code랑 Codex를 한 레포에서 같이 돌리면 서로 파일을 덮어쓰고, 터미널 앱을 닫으면 몇 시간짜리 작업이 날아가더라고요.

그래서 Ferryx를 만들었습니다.
- 에이전트마다 별도 git worktree
- 창을 닫아도 백그라운드 데몬이 에이전트를 계속 돌림
- 폰에서 로그인해서 진행 상황 확인, 입력까지

Rust + libghostty, Electron 없음. 개인은 무료(source-available)고 가입 없이 받을 수 있어요.
https://github.com/Indosaram/ferryx
