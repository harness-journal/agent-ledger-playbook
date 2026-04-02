# Simon Willison Method Reference

이 패키지는 Simon Willison의 공개 워크플로를 핵심 실전 기준으로 삼습니다.

## Why Simon Is The Backbone

Simon의 강점은 "AI를 더 세게 만든다"보다 "AI를 더 기록 가능하고 운영 가능하게 만든다"에 있습니다.

공개적으로 확인 가능한 포인트:

- `llm` 도구는 prompt/response를 SQLite에 저장하는 방향을 택함
- 저장된 로그를 Datasette로 다시 조회하는 흐름을 제시함
- 2026년 4월 공개 릴리스에서 tool call loops, prompts/responses/tool calls logging, actor, allowed/default model 같은 운영 포인트를 반복적으로 다룸

## Primary Sources

아래 링크는 이 문서가 직접 참고한 공개 1차 출처입니다.

- `llm` repository: https://github.com/simonw/llm
- `Language models on the command-line` handout: https://github.com/simonw/language-models-on-the-command-line
- Simon Willison April 2026 archive: https://simonwillison.net/2026/Apr/

팩트는 위 링크를 기준으로 정리했고, 그 외의 적용 설명은 이 패키지의 해석과 번역입니다.

## Confirmed Pattern

공개 자료 기준으로 해석 가능한 핵심 흐름:

1. LLM 실행
2. prompt/response 저장
3. tool calls와 usage 기록 강화
4. actor 추가
5. model policy 추가
6. 나중에 다시 조회

한 줄로 정리하면:

`기억에 의존하지 말고, AI 실행을 다시 볼 수 있는 기록으로 남겨라.`

## What We Borrow

이 패키지는 Simon의 워크플로에서 아래를 적극적으로 차용합니다.

- chat history가 아니라 log 중심 사고
- prompt/response를 별도 자산으로 보는 시각
- tool call을 운영 로그로 보는 태도
- actor를 운영 정보로 취급하는 방식
- 작업별 model policy를 두는 감각
- 저장 후 다시 조회 가능한 구조를 우선하는 방식

## What We Do Not Assume

우리는 Simon의 개인 내부 운영 전체를 아는 것이 아닙니다.

따라서:

- 공개 자료에서 확인 가능한 것만 사실로 쓴다
- 그 이상은 응용 또는 해석으로 명시한다

## Design Consequence

이 패키지를 따르는 AI는 다음을 우선 제안해야 합니다.

1. 최소 저장 필드 정의
2. 파일 기반 최소 로그 설계
3. JSON 또는 SQLite 확장 경로 제시
4. actor와 model 기록 포함
5. 나중에 조회/리뷰 가능한 구조 제시
