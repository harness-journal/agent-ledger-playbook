# Agent Ledger Playbook

> A human-readable and AI-executable playbook for AI work logging systems.

[![License: MIT](https://img.shields.io/badge/license-MIT-black.svg)](./LICENSE)
[![Release](https://img.shields.io/badge/release-v1.0.0-e5622b.svg)](https://github.com/harness-journal/agent-ledger-playbook/releases/tag/v1.0.0)
[![Playbook PDF](https://img.shields.io/badge/read-PLAYBOOK.pdf-172330.svg)](./PLAYBOOK.pdf)

AI에게 일을 시킨 뒤, 나중에 다시 설명할 수 있게 만드는 저장 방법론 패키지입니다.

이 패키지는 두 층으로 구성됩니다.

- 사람에게는: 왜 AI 작업을 기록으로 남겨야 하는지 설명하는 플레이북
- AI에게는: Codex와 Claude Code가 바로 읽고 저장 시스템을 설계할 수 있는 실행 팩

핵심 문장:

`사람은 이 패키지를 읽고 이해하고, AI는 이 패키지를 읽고 저장 시스템을 설계한다.`

## Start Here

- 사람이라면: [`PLAYBOOK.pdf`](./PLAYBOOK.pdf)부터 읽으세요
- AI에게는: `AGENTS.md` 또는 `CLAUDE.md`와 `pack/`을 먼저 읽히세요
- 바로 써보고 싶다면: 아래 프롬프트를 그대로 붙여넣으세요

```txt
이 폴더의 PLAYBOOK.pdf와 AGENTS.md/CLAUDE.md, pack 문서를 기준으로
내 프로젝트용 AI 작업 로그 시스템을 설계해줘.
```

이 저장 방식이 유용했다면 repo에 star를 남겨주세요.  
같은 문제를 겪는 사람이 이 playbook을 더 빨리 찾는 데 도움이 됩니다.

## What This Package Solves

아래 문제를 줄이기 위해 만들었습니다.

- AI에게 무슨 일을 시켰는지 나중에 모르겠다
- 왜 그런 결과가 나왔는지 추적이 안 된다
- 팀이 AI를 제각각 사용한다
- 프롬프트, 응답, 사용 도구, 실행 주체, 모델이 남지 않는다

## What Is Included

- `PLAYBOOK.pdf`
  사람이 읽는 메인 플레이북
- `AGENTS.md`
  Codex용 상위 규칙
- `CLAUDE.md`
  Claude Code용 상위 규칙
- `SIMON_METHOD_REFERENCE.md`
  Simon Willison의 공개 저장/로그/조회 워크플로 기준 문서
- `pack/00~08`
  AI가 실제로 읽고 실행할 수 있는 운영 규칙 팩
- `templates/*`
  work log, JSON task, weekly review, research note, team policy, validation report 템플릿
- `examples/*`
  1인 작업자, 개발팀, 비개발 운영팀 예시

## Choose Your Starting Path

### 비개발자라면

아래 순서로 시작하는 것이 가장 쉽습니다.

1. `PLAYBOOK.pdf`
2. `templates/work-log.md`
3. `templates/weekly-review.md`
4. `examples/nondev-ops-example.md`
5. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`의 Solo Creator 또는 Team Setup 프롬프트

이 경로는 글쓰기, 리서치, 운영, 공지문, 메일 초안 같은 작업에 잘 맞습니다.

### 개발자라면

아래 순서로 시작하는 것이 가장 좋습니다.

1. `PLAYBOOK.pdf`
2. `AGENTS.md` 또는 `CLAUDE.md`
3. `pack/03_STORAGE_SCHEMA.md`
4. `templates/ai-task.json`
5. `examples/dev-team-example.md`
6. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`의 Developer Setup 프롬프트

이 경로는 코드 작성, 디버깅, 리서치 자동화, CLI 기반 작업에 잘 맞습니다.

## Why This Is Different

이 패키지는 일반적인 생산성 팁 모음이 아닙니다.

- Simon Willison의 공개 워크플로를 실전 백본으로 사용
- Mitchell Hashimoto의 하네스 관점으로 review와 반복 실수 방지를 연결
- PDF는 철학과 구조를 설명하고
- Markdown Pack은 AI가 바로 실행할 수 있는 규칙으로 정리합니다

## Verified Simon Sources

이 패키지에서 Simon 관련 설명은 아래 1차 출처를 기준으로 작성했습니다.

- `llm` repository: https://github.com/simonw/llm
- `Language models on the command-line` handout: https://github.com/simonw/language-models-on-the-command-line
- Simon Willison 2026년 4월 archive: https://simonwillison.net/2026/Apr/

## Start In 3 Minutes

### 사람이 먼저 읽을 순서

1. `PLAYBOOK.pdf`
2. `README_START_HERE.md`
3. `SIMON_METHOD_REFERENCE.md`
4. `pack/00_AI_INGESTION_NOTE.md`

### AI에게 먼저 읽힐 순서

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

## Recommended Prompt

```txt
이 폴더의 PLAYBOOK.pdf와 AGENTS.md/CLAUDE.md, pack 문서를 기준으로
내 프로젝트용 AI 작업 로그 시스템을 설계해줘.

조건:
- Simon Willison의 공개 워크플로를 핵심 기준으로 삼을 것
- 최소 저장 항목은 prompt, response, tools, actor, model
- 민감정보는 저장하지 않거나 마스킹할 것
- 처음에는 Markdown 또는 JSON 기반으로 시작할 것
- 필요하면 SQLite로 확장 경로를 제안할 것
```

## Minimum Logging Standard

최소한 아래 다섯 가지는 남겨야 합니다.

- prompt
- response
- tools
- actor
- model

## Safety Defaults

- local-first
- minimum viable capture
- redact before store

즉, 무조건 많이 저장하는 것이 아니라, 다시 볼 가치가 있는 것만 안전하게 남기는 것이 목적입니다.

## Suggested First Files

가장 쉬운 시작은 아래 세 파일이면 충분합니다.

- `templates/work-log.md`
- `templates/weekly-review.md`
- `AGENTS.md` 또는 `CLAUDE.md`

## Validation

이 패키지는 설계만 하게 두지 않습니다.
AI가 실제로 저장 로직이 완성됐는지 검증할 수 있도록 아래를 포함합니다.

- `pack/08_VALIDATION_CHECKLIST.md`
- `templates/validation-report.md`

즉, AI는 저장 시스템을 제안한 뒤에도

- 필수 파일이 실제로 생겼는지
- 필수 필드가 실제로 들어가는지
- privacy 규칙이 반영됐는지
- review 루프가 있는지

를 다시 체크할 수 있습니다.

## Version

- Current release: `v1.0.0`
- Release date: `2026-04-02`

## License

이 패키지는 `MIT License`로 무료 공개됩니다.

- license file: `LICENSE`
- 누구나 무료로 사용, 복사, 수정, 배포할 수 있습니다
- 재배포 시에는 라이선스 고지를 함께 포함해야 합니다

## Next Step

바로 시작하려면 `README_START_HERE.md`를 열고, AI에게는 `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`의 프롬프트를 그대로 사용하면 됩니다.
