# Simon Method

이 문서는 Simon Willison의 공개 워크플로를 이 패키지의 실행 규칙으로 번역한 문서입니다.

## The Main Idea

Simon의 공개 흐름을 쉬운 말로 바꾸면:

`AI를 쓰고 끝내지 말고, 나중에 다시 볼 수 있는 로그로 남겨라.`

## Simon-style Operational Priorities

### 1. Prompt is a first-class asset

프롬프트는 임시 대화가 아니라 나중에 다시 봐야 하는 작업 지시입니다.

### 2. Response is not enough

결과만 남기면 부족합니다.
가능하면 tools, usage, actor까지 함께 봐야 합니다.

### 3. Tool calls matter

에이전트는 중간 행동이 중요합니다.
검색, 파일 읽기, 테스트, 외부 호출이 무엇이었는지 남기면 원인 분석이 쉬워집니다.

### 4. Actor matters

누가 실행했는지 남겨야 팀 운영이 가능합니다.

### 5. Model choice is part of the system

작업별 허용 모델, 기본 모델, 사용 모델 기록은 나중에 품질과 비용을 비교할 때 중요합니다.

### 6. Storage should be queryable

메모만 쌓는 것이 아니라 나중에 다시 검색, 조회, 비교가 가능해야 합니다.

## How To Apply Simon's Method Without Complexity

### Step 1. Start with a work log file

작업마다 아래를 남깁니다.

- task
- prompt
- response
- tools
- actor
- model

### Step 2. Add JSON for structured logging

작업이 많아지면 JSON으로 바꿉니다.

### Step 3. Move to SQLite if you need retrieval

작업량이 늘거나 조회가 중요해지면 SQLite로 올립니다.

### Step 4. Add review

저장만 하지 말고 주간 review를 통해 반복 실수를 찾습니다.

## What An AI Should Do When Asked To Implement This

AI는 아래 순서로 제안해야 합니다.

1. 가장 쉬운 파일 기반 로그
2. 최소 JSON schema
3. SQLite 확장안
4. actor/model/tool을 포함한 운영 필드
5. review workflow
