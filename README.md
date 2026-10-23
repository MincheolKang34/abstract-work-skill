# abstract-work

폴더 또는 파일을 분석해 **어떤 작업이 진행되었는지 요약·정리**해 주는 Claude Code 스킬입니다.

## 설치

Claude Code 안에서 아래 두 줄을 차례로 입력합니다.

```
/plugin marketplace add MincheolKang34/abstract-work-skill
/plugin install abstract-work@abstract-marketplace
```

설치 후 Claude Code를 새로 시작하면 `/abstract-work` 명령을 쓸 수 있습니다.

### 직접 복사해서 설치 (플러그인 없이)

`plugins/abstract-work/skills/abstract-work/` 폴더를 아래 위치에 복사해도 됩니다.

- 모든 프로젝트에서 사용: `~/.claude/skills/abstract-work/`
- 현재 프로젝트에서만 사용: `<프로젝트>/.claude/skills/abstract-work/`

## 사용 방법

```
/abstract-work <폴더 또는 파일 경로>
```

경로 없이 `/abstract-work`만 입력하면 경로를 입력해 달라고 안내하고, 다음 메시지로 보낸 경로를 분석합니다.

### 경로가 파일일 때

- **용도**: 이 파일이 무엇을 위한 것인지
- **내용**: 코드는 동작/역할, 문서는 내용
- **생성 일자**: 파일 시스템의 생성 시각

### 경로가 폴더일 때

- 폴더 안 파일을 하나씩 간략히 소개합니다. 코드는 동작/역할, 문서는 내용을 설명합니다.
- 마지막에 폴더 전체에 대한 요약을 붙입니다.
- `.git`, `node_modules` 같은 폴더는 제외하고, 파일이 많으면 대표 파일 위주로 읽습니다.

### 프로젝트일 때

분석한 내용을 바탕으로 **더 수행하면 좋을 작업을 추천**합니다.

- 추천만 하며, 추천한 작업을 스스로 실행하지 않습니다.
- 배포, 삭제·덮어쓰기, 운영 서버 변경처럼 관리자 권한이 필요하거나 위험한 작업에는 ⚠️ 경고를 함께 안내합니다.

## 알아둘 점

- 읽기 전용 스킬입니다. 파일을 수정·삭제·생성하지 않습니다.
- `/abstract-work`를 직접 입력했을 때만 작동합니다(자동 실행 안 됨).
- 생성 일자 조회는 Windows PowerShell 기준으로 작성되어 있어, macOS/Linux에서는 값을 못 구하면 "확인 필요"로 표시될 수 있습니다.
- 플러그인으로 설치했을 때 명령 이름이 `/abstract-work:abstract-work` 형태로 보일 수 있습니다. `/` 입력 후 목록에서 확인하세요.
