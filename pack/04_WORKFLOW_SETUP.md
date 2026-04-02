# Workflow Setup

이 문서는 이 패키지를 실제 프로젝트에 붙이는 순서를 정의합니다.

목표는 간단합니다.

- 오늘 시작할 수 있게 만들기
- Simon식 저장/조회 구조로 자연스럽게 확장되게 만들기
- 사람이 이해할 수 있고 AI가 바로 실행할 수 있게 만들기

## Core Principle

처음부터 완성형 시스템을 만들지 않습니다.

권장 순서는 아래와 같습니다.

1. Markdown work log
2. JSON task log
3. SQLite storage
4. review layer
5. query/view layer

## Setup Tracks

### Track A. Solo Creator

가장 쉬운 시작.

필수 파일:

- `templates/work-log.md`
- `templates/weekly-review.md`

운영 순서:

1. 프로젝트 루트 또는 전용 폴더에 `work-log.md` 생성
2. AI 작업이 끝날 때마다 한 블록 append
3. 주 1회 `weekly-review.md` 기준으로 회고

이 트랙은 아래 상황에 적합합니다.

- 개인 창작
- 리서치
- Threads 또는 블로그 작성
- AI 작업 습관 만들기

### Track B. Builder / Developer

자동화가 조금 필요한 경우.

필수 파일:

- `templates/work-log.md`
- `templates/ai-task.json`

운영 순서:

1. Markdown 로그로 시작
2. 반복 작업만 JSON 구조로 병행 저장
3. 모델 비교 또는 도구 추적이 중요해지면 SQLite로 확장

이 트랙은 아래 상황에 적합합니다.

- 코드 작성
- 디버깅
- 리서치 자동화
- CLI 기반 AI 사용

### Track C. Team / Shared Workflow

여러 사람이 같은 기준으로 써야 하는 경우.

필수 파일:

- `templates/team-policy.md`
- `templates/weekly-review.md`
- `templates/ai-task.json`

운영 순서:

1. team policy 정의
2. 필수 저장 필드 통일
3. actor와 approval 기준 추가
4. 주간 review에서 실패 패턴과 규칙 변경 반영

이 트랙은 아래 상황에 적합합니다.

- 콘텐츠 팀
- 운영 팀
- 제품 팀
- AI 실험을 여러 명이 함께 하는 조직

## Minimum Folder Layout

```txt
project/
├── AGENTS.md or CLAUDE.md
├── ai-ops/
│   ├── work-log.md
│   ├── weekly-review.md
│   ├── tasks/
│   │   └── 2026-04-02-task-001.json
│   └── policy/
│       └── team-policy.md
```

## What The AI Should Propose First

AI는 처음부터 복잡한 DB나 대시보드를 제안하지 않습니다.

먼저 아래를 제안해야 합니다.

1. 가장 쉬운 파일 저장 구조
2. 누가 써도 되는 필수 필드
3. 민감정보 제외 규칙
4. 다음 확장 단계

## Upgrade Triggers

아래 상황이면 다음 단계로 올립니다.

- Markdown 검색이 불편해진다
- 작업 수가 늘어서 비교가 필요하다
- actor/model/tool 기준으로 필터링하고 싶다
- 팀이 같은 규칙으로 써야 한다
- 주간 review를 자동화하고 싶다

## Setup Checklist

- `AGENTS.md` 또는 `CLAUDE.md`가 있다
- 최소 필수 필드가 정해져 있다
- 저장 위치가 프로젝트별로 분리되어 있다
- 민감정보 저장 금지 기준이 있다
- 주간 review 루프가 있다
