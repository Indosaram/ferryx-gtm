# skill: measure

목적: 매일 같은 방법으로 지표를 찍어 루프 효과를 비교 가능하게 만든다.

1. `bun scripts/snapshot.ts > metrics/day-N.json` (gh CLI 로그인 필요, traffic API는 레포 관리자 권한 필요).
2. 수동 지표를 같은 파일의 `manual` 필드에 기록:
   - Discord: `curl -s 'https://discord.com/api/v9/invites/Z2hBkQEHUG?with_counts=true' | jq .approximate_member_count`
   - 대기 명단 (고유 사용자, 메인테이너 제외):
     `(gh api repos/Indosaram/ferryx-gtm/issues/1/comments --jq '.[].user.login'; gh api repos/Indosaram/ferryx-gtm/issues/1/reactions --jq '.[].user.login') | grep -vx Indosaram | sort -u | wc -l`
   - 외부 게시물·언급 수와 URL
3. 전날 대비 증감과 7일 목표 대비 진척률을 표로 `log/day-N.md` 맨 위에 붙인다.
4. referrer 상위 5개를 보고 어느 채널이 유입을 만들었는지 적는다.

출력: metrics/day-N.json, log/day-N.md의 "지표" 섹션.
