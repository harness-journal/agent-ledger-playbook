# Capture Rules

이 문서는 무엇을 저장해야 하는지에 대한 최소 규칙입니다.

## Required Fields

### prompt

- 내가 AI에게 무엇을 요청했는지

### response

- AI가 무엇을 답했는지

### tools

- 중간에 사용한 도구 목록

### actor

- 누가 실행했는지

### model

- 어떤 모델을 썼는지

## Recommended Fields

### timestamp

- 언제 실행했는지

### task

- 어떤 작업이었는지

### next_action

- 다음에 무엇을 해야 하는지

### artifact

- 결과 파일이나 링크

### approval

- 사람이 승인했는지 여부

## Capture Philosophy

최소 저장 규칙은 아래 질문에 답할 수 있어야 합니다.

1. 뭘 시켰나
2. 뭐가 나왔나
3. 중간에 뭘 했나
4. 누가 실행했나
5. 어떤 모델이었나

## What Not To Store By Default

- secret
- token
- 고객 원문 민감정보
- 사내 민감 문서 전체

민감정보가 섞일 수 있으면:

- redaction
- 요약 저장
- local-only
- 저장 opt-in

중 하나를 먼저 고려합니다.
