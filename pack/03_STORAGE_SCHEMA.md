# Storage Schema

이 문서는 가장 쉬운 버전부터 확장 버전까지의 저장 구조를 정의합니다.

## Level 1. Markdown

가장 쉬운 시작점.

```md
## 2026-04-02 15:00
- task: Simon 4월 글 정리
- actor: inabe
- model: gpt-5
- prompt: Simon 4월 글 핵심 정리
- response: 운영, 추적, 권한 중심
- tools: web_search
- next_action: Threads 초안 작성
```

## Level 2. JSON

구조화된 저장.

```json
{
  "timestamp": "2026-04-02T15:00:00",
  "task": "summarize_simon_april_posts",
  "actor": "inabe",
  "model": "gpt-5",
  "prompt": "Simon 4월 글 핵심 정리",
  "response": "운영, 추적, 권한 중심",
  "tools": ["web_search"],
  "next_action": "write_threads_draft"
}
```

## Level 3. SQLite

조회와 분석이 중요해질 때.

권장 테이블 개념:

- tasks
- prompts
- responses
- tool_calls
- usage
- artifacts

### Minimal SQLite-Oriented Field Set

- task_id
- timestamp
- actor
- model
- prompt
- response
- tool_calls_json
- next_action

## Schema Rule

처음부터 SQLite를 강요하지 않습니다.

확장 순서는:

1. Markdown
2. JSON
3. SQLite

단, 어느 단계든 필수 정보는 같습니다.

- prompt
- response
- tools
- actor
- model
