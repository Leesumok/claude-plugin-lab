# claude-plugin-lab

GitHub 워크플로우 자동화를 위한 Claude Code 커스텀 슬래시 커맨드 모음.

## 설치 (Marketplace를 통한 설치)

이 플러그인을 다른 프로젝트에서도 사용하려면 마켓플레이스를 추가한 뒤 플러그인을 설치합니다.

### 1단계: 마켓플레이스 추가

Claude Code 내에서 아래 명령어 중 하나를 실행합니다.

**GitHub 축약형 (권장)**

```shell
/plugin marketplace add leesumok/claude-plugin-lab
```

**HTTPS**

```shell
/plugin marketplace add https://github.com/leesumok/claude-plugin-lab.git
```

**SSH**

```shell
/plugin marketplace add git@github.com:leesumok/claude-plugin-lab.git
```

> 특정 브랜치나 태그를 지정하려면 `#`을 붙입니다:
> ```shell
> /plugin marketplace add leesumok/claude-plugin-lab#v1.0.0
> ```

### 2단계: 플러그인 설치

마켓플레이스를 추가한 뒤, 플러그인을 설치합니다.

```shell
/plugin install claude-plugin-lab@claude-plugin-lab
```

또는 `/plugin`을 실행하여 **Discover** 탭에서 검색 후 설치할 수도 있습니다.

설치 범위를 선택할 수 있습니다:
- **User scope**: 모든 프로젝트에서 사용 (기본값)
- **Project scope**: 이 저장소의 모든 협력자가 사용
- **Local scope**: 이 저장소에서 나만 사용

### 3단계: 플러그인 로드

```shell
/reload-plugins
```

설치 후 어떤 프로젝트에서든 아래와 같이 네임스페이스 커맨드를 사용할 수 있습니다:

```shell
/claude-plugin-lab:plan-issue 로그인 페이지 리디자인
/claude-plugin-lab:code-gen 42
/claude-plugin-lab:branch-commit feat/login-redesign
/claude-plugin-lab:pull-request
/claude-plugin-lab:merge 15
```

## 커맨드

### `/plan-issue <작업 주제>`
작업 주제에 대한 계획을 수립하고 GitHub 이슈를 생성합니다.

```
/plan-issue 로그인 페이지 리디자인
```

### `/code-gen <이슈 번호>`
이슈에 작성된 작업계획을 기반으로 코드를 작성합니다.

```
/code-gen 42
```

### `/branch-commit <브랜치명> [커밋메시지]`
브랜치를 생성하고 변경사항을 커밋/푸시합니다.

```
/branch-commit feat/login-redesign
/branch-commit feat/login-redesign "feat: redesign login page"
```

### `/pull-request [제목 | #이슈번호]`
현재 브랜치에서 main으로 PR을 생성합니다.

```
/pull-request
/pull-request 로그인 페이지 리디자인
/pull-request #42
```

### `/merge <PR 번호>`
PR을 squash merge하고 로컬을 정리합니다.

```
/merge 15
```

## 요구사항

- [Claude Code](https://claude.ai/code) CLI
- [GitHub CLI (`gh`)](https://cli.github.com/) 설치 및 인증
- Git
