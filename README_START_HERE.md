# Agent Ledger Playbook

이 패키지는 사람이 읽는 가이드이면서, AI가 그대로 실행 규칙으로 읽을 수 있는 저장 방법론 팩입니다.

핵심 문장:

`사람은 이 패키지를 읽고 이해하고, AI는 이 패키지를 읽고 저장 시스템을 설계한다.`

## What This Package Is

이 패키지는 아래 문제를 해결하기 위해 만들어졌습니다.

- AI에게 무슨 일을 시켰는지 나중에 다시 모르겠다
- 왜 그런 결과가 나왔는지 추적이 안 된다
- 팀이 AI를 각자 제멋대로 쓰고 있다
- Codex와 Claude Code가 같은 기준으로 기록하지 않는다

## Start Here

### 사람이 먼저 볼 것

1. `SIMON_METHOD_REFERENCE.md`
2. `pack/00_AI_INGESTION_NOTE.md`
3. `pack/01_SIMON_METHOD.md`
4. `pack/02_CAPTURE_RULES.md`
5. `pack/04_WORKFLOW_SETUP.md`
6. `pack/05_REVIEW_AND_FEEDBACK.md`
7. `pack/06_PRIVACY_REDACTION.md`

### 비개발자용 빠른 시작

1. `PLAYBOOK.pdf`
2. `templates/work-log.md`
3. `templates/weekly-review.md`
4. `examples/nondev-ops-example.md`
5. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`의 Solo Creator Setup 또는 Team Setup 사용

### 개발자용 빠른 시작

1. `PLAYBOOK.pdf`
2. `AGENTS.md` 또는 `CLAUDE.md`
3. `templates/ai-task.json`
4. `examples/dev-team-example.md`
5. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`의 Developer Setup 사용

### AI에게 먼저 읽힐 것

1. `AGENTS.md` 또는 `CLAUDE.md`
2. `pack/00_AI_INGESTION_NOTE.md`
3. `pack/01_SIMON_METHOD.md`
4. `pack/02_CAPTURE_RULES.md`
5. `pack/03_STORAGE_SCHEMA.md`
6. `pack/04_WORKFLOW_SETUP.md`
7. `pack/05_REVIEW_AND_FEEDBACK.md`
8. `pack/06_PRIVACY_REDACTION.md`
9. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`
10. `pack/08_VALIDATION_CHECKLIST.md`

## Recommended Prompt For Codex or Claude Code

```txt
이 폴더의 AGENTS.md/CLAUDE.md와 pack 문서를 기준으로 내 프로젝트용 AI 작업 로그 시스템을 설계해줘.

조건:
- Simon Willison의 공개 워크플로를 핵심 기준으로 삼을 것
- 최소 저장 항목은 prompt, response, tools, actor, model
- 민감정보는 저장하지 않거나 마스킹할 것
- 처음엔 파일 기반으로 시작하고, 필요하면 JSON/SQLite까지 확장할 것
```

## What Makes This Different

이 패키지는 일반적인 "AI 생산성 팁" 모음이 아닙니다.

- Simon Willison의 공개 저장/로그/조회 워크플로를 핵심 백본으로 사용
- Hashimoto식 하네스 관점으로 반복 실수 방지와 운영 구조를 연결
- 사람에게는 쉬운 문장으로 설명
- AI에게는 바로 실행 가능한 규칙으로 정리

## Minimum Promise

이 패키지를 적용하면 최소한 아래는 남길 수 있어야 합니다.

- 내가 뭐라고 시켰는지
- AI가 뭐라고 답했는지
- 중간에 어떤 도구를 썼는지
- 누가 실행했는지
- 어떤 모델을 썼는지

## Current Package State

- `PLAYBOOK.pdf` 포함
- Markdown Pack `00~08` 포함
- 템플릿과 예시 파일 포함
- `LICENSE` 포함
- 지금도 바로 프로젝트에 복사해서 쓸 수 있습니다
