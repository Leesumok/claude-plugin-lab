---
name: merge
description: PR 병합
args_description: "<PR 번호>"
---

PR 번호: $ARGUMENTS

위 PR 번호에 대해 다음을 수행해줘:

1. PR 상태를 확인해줘:
   - `gh pr view $ARGUMENTS`
   - 머지 가능 상태인지 (체크, 리뷰, 충돌 여부)

2. 머지 가능하면 병합해줘:
   - `gh pr merge $ARGUMENTS --squash --delete-branch`
   - squash merge로 커밋 히스토리를 깔끔하게 유지

3. 머지 불가능하면 이유를 알려주고 해결 방법을 제안해줘.

4. 병합 완료 후:
   - 로컬 브랜치를 main으로 전환: `git checkout main`
   - 최신 상태로 업데이트: `git pull`
   - 결과를 요약해줘.
