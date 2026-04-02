# Project Bootstrap Prompts

이 문서는 Codex 또는 Claude Code에 바로 넣을 수 있는 시작 프롬프트 모음입니다.

## Prompt 01. Smallest Viable Setup

```txt
이 폴더의 AGENTS.md/CLAUDE.md와 pack 문서를 기준으로
내 프로젝트용 AI 작업 로그 시스템을 설계해줘.

조건:
- Simon Willison의 공개 워크플로를 핵심 기준으로 삼을 것
- 최소 저장 항목은 prompt, response, tools, actor, model
- 처음에는 Markdown work-log 방식으로 시작할 것
- 민감정보는 저장하지 않거나 마스킹할 것
- 사람이 이해할 수 있는 설명도 함께 쓸 것
```

## Prompt 02. Solo Creator Setup

```txt
이 패키지를 기준으로 1인 창작자용 AI 작업 기록 시스템을 세팅해줘.

원하는 것:
- work-log.md 기반
- 주간 회고 포함
- Threads, 리서치, 글쓰기 작업에 맞는 구조
- 다음 단계로 JSON 확장 경로도 제안
```

## Prompt 03. Developer Setup

```txt
이 패키지를 기준으로 개발자용 AI 로그 구조를 설계해줘.

원하는 것:
- Markdown + JSON 병행
- prompt/response/tool logging 포함
- actor와 model 필드 포함
- 나중에 SQLite로 확장 가능한 schema 제안
```

## Prompt 04. Team Setup

```txt
이 패키지를 기준으로 팀 공용 AI 작업 로그 정책을 설계해줘.

조건:
- 팀원별 actor 추적
- approval 지점 정의
- 민감정보 저장 금지 규칙 포함
- 주간 review workflow 포함
- team-policy.md 초안까지 만들어줘
```

## Prompt 05. Review Upgrade

```txt
지난 2주의 work-log와 ai-task.json을 기준으로
반복 실패 패턴과 다음 주 수정 규칙을 뽑아줘.

출력 형식:
- 반복 실수 3개
- 유지할 좋은 패턴 3개
- 새 규칙 3개
```

## Prompt 06. Privacy Upgrade

```txt
현재 로그 구조를 검토해서
민감정보가 저장될 위험이 있는 지점을 찾아줘.

그리고 아래를 제안해줘:
- redaction 규칙
- local-only 권장 위치
- export 전 human review 절차
```

## Prompt 07. Validation Audit

```txt
이 프로젝트에 적용된 AI 작업 로그 시스템을 검증해줘.

조건:
- pack/08_VALIDATION_CHECKLIST.md를 기준으로 판단할 것
- 실제 파일과 폴더를 확인할 것
- PASS / FAIL / PARTIAL / N/A 중 하나로 표기할 것
- 각 판단마다 evidence file path를 남길 것
- 결과는 templates/validation-report.md 형식으로 출력할 것
```

## Prompt 08. Package Validation Audit

```txt
이 패키지 자체가 공개 배포 가능한 상태인지 검증해줘.

조건:
- pack/08_VALIDATION_CHECKLIST.md의 Package Validation Checklist를 기준으로 판단할 것
- 실제 파일 존재 여부를 확인할 것
- PASS / FAIL / PARTIAL / N/A 중 하나로 표기할 것
- 각 판단마다 evidence file path를 남길 것
- 결과는 templates/validation-report.md 형식으로 출력할 것
```
