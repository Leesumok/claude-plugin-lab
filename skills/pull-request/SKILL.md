---
name: pull-request
description: PR 생성
args_description: "[PR 제목 | #이슈번호]"
---

인자: $ARGUMENTS

위 인자를 파싱해줘. 형식은 다음 중 하나:
- 빈 값 — 자동으로 PR 제목/설명 생성
- `<PR 제목>` — 제목만 제공
- `#<이슈번호>` — 이슈 번호 기반으로 PR 생성

다음을 수행해줘:

1. 현재 브랜치와 base 브랜치(main) 간의 차이를 확인해줘:
   - `git log main..HEAD --oneline`
   - `git diff main...HEAD --stat`

2. PR을 생성해줘:
   - `gh pr create` 사용
   - 제목: 제공된 제목 또는 커밋 내역 기반으로 자동 생성
   - 본문: 변경사항 요약, 관련 이슈 링크 (있으면 `Closes #이슈번호`)
   - base 브랜치: main

3. 생성된 PR 번호와 URL을 알려줘.
