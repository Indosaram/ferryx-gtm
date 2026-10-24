# skill: listen

목적: 사용자 반응을 반론·요청·칭찬·버그로 분류해 다음 행동의 입력으로 만든다.

1. 수집: 전날 게시물 댓글(HN/Reddit/GeekNews 등), GitHub 이슈·디스커션, Discord, "Ferryx" 검색 결과.
2. 각 항목을 한 줄로 요약하고 분류: OBJECTION / REQUEST / PRAISE / BUG.
3. OBJECTION은 `strategy/objections.md`의 기존 항목에 매핑하고 등장 횟수를 올린다. 새 반론이면 추가.
4. BUG는 재현 정보와 함께 Ferryx 이슈로 등록(사람 확인 후).
5. 사실과 해석을 구분한다. 댓글 하나를 "사용자들은"으로 일반화하지 않는다.

출력: log/day-N.md의 "들은 것" 섹션, objections.md 횟수 갱신.
