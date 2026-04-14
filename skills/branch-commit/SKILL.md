---
name: branch-commit
description: 브랜치 생성, 커밋, 푸시
args_description: "<브랜치명> [커밋메시지]"
---

인자: $ARGUMENTS

위 인자를 파싱해줘. 형식은 다음 중 하나:
- `<브랜치명>` — 브랜치명만 제공 (커밋 메시지는 자동 생성)
- `<브랜치명> <커밋메시지>` — 둘 다 제공

다음을 순서대로 수행해줘:

1. `git status`로 현재 상태를 확인해줘.

2. 브랜치를 생성하고 전환해줘:
   - `git checkout -b <브랜치명>`
   - 이미 존재하는 브랜치면 `git checkout <브랜치명>`

3. 변경사항을 커밋해줘:
   - `git add`로 관련 파일 스테이징 (민감한 파일 제외)
   - 커밋 메시지가 없으면 변경사항을 분석해서 conventional commit 형식으로 자동 생성
   - `git commit`

4. 리모트에 푸시해줘:
   - `git push -u origin <브랜치명>`

5. 결과를 요약해줘 (브랜치명, 커밋 해시, 푸시 상태).

6. 사용자에게 PR을 생성할지 물어봐줘. 사용자가 동의하면 `/pull-request` 스킬을 실행해줘.
