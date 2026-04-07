# claude-plugin-lab

GitHub 워크플로우 자동화를 위한 Claude Code 커스텀 슬래시 커맨드 모음.

## 커맨드 목록

| 커맨드 | 설명 |
|--------|------|
| `/plan-issue` | 작업 주제로 이슈 생성 + 작업계획 |
| `/code-gen` | 이슈 번호 기반 코드 작성 |
| `/branch-commit` | 브랜치 생성, 커밋, 푸시 |
| `/pull-request` | PR 생성 |
| `/merge` | PR 병합 |

## 규칙

- 모든 커맨드는 `gh` CLI와 `git`을 사용한다.
- 커맨드 실행 전 현재 레포 상태를 확인한다.
- 위험한 작업(force push, 브랜치 삭제 등)은 사용자 확인 후 진행한다.
- 커밋 메시지는 conventional commits 형식을 따른다.
