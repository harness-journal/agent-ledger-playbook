# Privacy And Redaction

이 문서는 무엇을 저장하지 말아야 하는지와, 어떻게 마스킹할지를 정의합니다.

## Default Position

기본값은 아래입니다.

- local-first
- minimum viable capture
- redact before store

즉, 저장은 하되 꼭 필요한 것만 남깁니다.

## Never Store By Default

- API keys
- secrets
- tokens
- passwords
- customer raw personal data
- company-confidential source documents in full
- full prompts that contain sensitive data

## Safer Alternatives

민감정보가 포함될 수 있으면 아래 중 하나를 선택합니다.

1. summary only
2. redacted prompt
3. local-only storage
4. opt-in logging
5. manual review before export

## Redaction Rules

### Rule 1. Replace exact values

예:

- email -> `[redacted_email]`
- token -> `[redacted_token]`
- customer name -> `[redacted_name]`

### Rule 2. Keep operational meaning

프롬프트를 완전히 지우지 말고, 왜 그 작업을 했는지는 남깁니다.

좋은 예:

`VIP 고객 문의 원문을 요약해줘` 대신  
`[redacted_customer_message]를 요약해줘`

### Rule 3. Separate public and private artifacts

공개 가능 로그와 내부 전용 로그를 분리할 수 있으면 분리합니다.

## Project Separation

아래 중 하나를 권장합니다.

- 프로젝트별 폴더 분리
- 고객별 저장소 분리
- 공개/비공개 로그 분리

## AI Instruction

AI는 저장 시스템을 제안할 때 아래를 기본으로 포함해야 합니다.

- 민감정보는 저장하지 않는 기본값
- redaction 예시
- local-first 저장 위치
- export 전 human review

## Quick Safety Checklist

- prompt에 민감정보가 있는가
- response에 민감정보가 복제됐는가
- artifact가 외부 공유 가능한가
- 이 로그를 다른 사람에게 보여줘도 되는가

하나라도 불확실하면:

- redaction
- summary only
- local-only

중 하나를 먼저 적용합니다.
