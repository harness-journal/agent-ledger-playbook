# Validation Checklist

이 문서는 AI가 저장 시스템이 실제로 완성되었는지 검증할 때 사용하는 체크리스트입니다.

핵심 원칙:

`설계가 존재하는 것`과 `작동하는 저장 로직이 실제로 있는 것`은 다릅니다.

따라서 AI는 구현 후 반드시 PASS/FAIL 기반 검증을 수행해야 합니다.

## Validation Modes

### Mode A. Package Validation

이 패키지 자체가 완결되었는지 검증합니다.

대상:

- README
- AGENTS/CLAUDE
- pack
- templates
- examples

### Mode B. Project Implementation Validation

어떤 프로젝트에 이 패키지를 적용한 뒤, 실제 저장 시스템이 생겼는지 검증합니다.

대상:

- 실제 로그 파일
- 실제 JSON/SQLite 구조
- privacy 규칙
- review 루프
- bootstrap prompt 적용 결과

## AI Validation Rules

AI는 아래 원칙을 지켜야 합니다.

1. 추측하지 말 것
2. 실제 파일 또는 폴더를 확인할 것
3. 각 판단에 증거 파일 경로를 남길 것
4. PASS / FAIL / PARTIAL / N/A 중 하나로 표기할 것
5. FAIL인 경우 바로 다음 수정 액션을 제안할 것

## Package Validation Checklist

### Package Check 01. Core Docs Exist

아래가 있어야 합니다.

- `README.md`
- `README_START_HERE.md`
- `PLAYBOOK.pdf`

### Package Check 02. AI Control Files Exist

아래가 있어야 합니다.

- `AGENTS.md`
- `CLAUDE.md`

### Package Check 03. Simon Reference Exists

아래가 있어야 합니다.

- `SIMON_METHOD_REFERENCE.md`
- Simon 1차 출처 링크

### Package Check 04. Full Execution Pack Exists

아래가 모두 있어야 합니다.

- `pack/00_AI_INGESTION_NOTE.md`
- `pack/01_SIMON_METHOD.md`
- `pack/02_CAPTURE_RULES.md`
- `pack/03_STORAGE_SCHEMA.md`
- `pack/04_WORKFLOW_SETUP.md`
- `pack/05_REVIEW_AND_FEEDBACK.md`
- `pack/06_PRIVACY_REDACTION.md`
- `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`
- `pack/08_VALIDATION_CHECKLIST.md`

### Package Check 05. Templates Exist

아래가 있어야 합니다.

- `work-log.md`
- `ai-task.json`
- `weekly-review.md`
- `research-note.md`
- `team-policy.md`
- `validation-report.md`

### Package Check 06. Examples Exist

아래 중 최소 세 개가 있어야 합니다.

- solo creator example
- developer team example
- non-developer ops example

### Package Check 07. License Exists

아래가 있어야 합니다.

- `LICENSE`

## Package Overall Status Rule

- `PASS`: 공개 패키지의 핵심 문서, pack, templates, examples, license가 모두 존재
- `PARTIAL`: 일부 문서나 예시가 누락됐지만 핵심 문서는 존재
- `FAIL`: 핵심 공개 패키지 구조가 빠져 있음

## Project Validation Checklist

### Check 01. Control Files Exist

아래 중 최소 하나가 있어야 합니다.

- `AGENTS.md`
- `CLAUDE.md`

추가로 아래가 있으면 더 좋습니다.

- `README_START_HERE.md`
- `team-policy.md`

### Check 02. Real Storage Exists

아래 중 최소 하나가 실제로 존재해야 합니다.

- `work-log.md`
- `tasks/*.json`
- SQLite database file

중요:

템플릿만 있고 실제 저장 위치가 없으면 `FAIL`입니다.

### Check 03. Required Fields Are Present

실제 저장 구조 안에 아래 필드가 모두 있어야 합니다.

- prompt
- response
- tools
- actor
- model

실제 로그 샘플 또는 스키마에서 확인합니다.

### Check 04. Privacy Guardrails Exist

아래 중 최소 하나가 확인되어야 합니다.

- redaction 규칙 문서
- local-only 저장 원칙
- do-not-store 리스트

### Check 05. Review Loop Exists

아래 중 최소 하나가 있어야 합니다.

- `weekly-review.md`
- review cadence 문서
- review 규칙이 포함된 policy

### Check 06. Bootstrap Path Exists

AI가 다시 이 시스템을 세팅하거나 확장할 수 있는 시작 프롬프트가 있어야 합니다.

예:

- bootstrap prompts 문서
- setup prompt block
- install instruction

### Check 07. Evidence Of Actual Use Exists

아래 중 최소 하나가 보여야 합니다.

- sample log entry
- sample JSON task file
- sample review entry

완전히 빈 템플릿만 있으면 `PARTIAL` 또는 `FAIL`입니다.

### Check 08. Upgrade Path Exists

다음 단계가 문서화돼 있어야 합니다.

예:

- Markdown -> JSON
- JSON -> SQLite
- 개인 -> 팀 운영

## Canonical Output

검증 결과는 반드시 `templates/validation-report.md` 형식으로 정리합니다.

최소 출력 필드:

- checked_at
- target
- mode
- overall_status
- implementation_level
- per-check status
- evidence
- next_fixes

## Suggested Overall Status Rule

- `PASS`: 핵심 저장 로직과 review/privacy가 모두 존재
- `PARTIAL`: 저장은 되지만 review, privacy, bootstrap 중 일부 부족
- `FAIL`: 실제 로그 구조나 필수 필드가 없음

## AI Prompt For Validation

```txt
이 프로젝트에 적용된 AI 작업 로그 시스템을 검증해줘.

조건:
- pack/08_VALIDATION_CHECKLIST.md를 기준으로 판단할 것
- 추측하지 말고 실제 파일을 확인할 것
- 각 판단마다 evidence file path를 남길 것
- PASS / FAIL / PARTIAL / N/A 중 하나로 평가할 것
- 결과는 templates/validation-report.md 형식으로 출력할 것
```

## AI Prompt For Package Validation

```txt
이 패키지 자체가 공개 배포 가능한 상태인지 검증해줘.

조건:
- pack/08_VALIDATION_CHECKLIST.md의 Package Validation Checklist를 기준으로 판단할 것
- 실제 파일 존재 여부를 확인할 것
- PASS / FAIL / PARTIAL / N/A 중 하나로 평가할 것
- evidence file path를 남길 것
- 결과는 templates/validation-report.md 형식으로 출력할 것
```
