# AI Ingestion Note

이 문서는 AI가 이 패키지를 읽을 때 가장 먼저 참고해야 하는 짧은 메모입니다.

## Purpose

당신의 목표는 "AI 작업을 설명 가능한 기록으로 남기는 시스템"을 설계하는 것입니다.

이 패키지는 단순 생산성 팁 모음이 아닙니다.
저장 규칙, 로그 구조, 리뷰 흐름을 한 세트로 만드는 것이 목적입니다.

## Priority

이 패키지에서 우선순위는 아래와 같습니다.

1. 저장 가능한 구조
2. 다시 조회 가능한 구조
3. 민감정보를 피하는 구조
4. 가장 쉬운 버전부터 시작하는 구조

## Minimum Required Capture

반드시 우선 고려할 항목:

- prompt
- response
- tools
- actor
- model

## Reference Hierarchy

이 패키지에서 판단 순서는 아래와 같습니다.

1. `SIMON_METHOD_REFERENCE.md`
2. `pack/01_SIMON_METHOD.md`
3. `pack/02_CAPTURE_RULES.md`
4. `pack/03_STORAGE_SCHEMA.md`
5. `pack/04_WORKFLOW_SETUP.md`
6. `pack/05_REVIEW_AND_FEEDBACK.md`
7. `pack/06_PRIVACY_REDACTION.md`
8. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`
9. `pack/08_VALIDATION_CHECKLIST.md`
10. 템플릿 파일들

## Instruction To The AI

시스템을 설계할 때는:

- 처음부터 복잡한 시스템을 강요하지 말 것
- 파일 기반 최소 로그에서 시작할 것
- 나중에 JSON/SQLite로 확장 가능하게 만들 것
- Simon식 저장/조회 구조를 적극적으로 반영할 것
- 사람도 이해할 수 있는 설명을 함께 제공할 것
- privacy와 redaction 규칙을 기본 제안에 포함할 것
- 구현 후에는 validation checklist로 실제 완성 여부를 다시 검증할 것
