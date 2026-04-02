# Dev Team Example

## Situation

세 명의 개발자가 Codex와 Claude Code를 함께 사용해 기능 개발과 디버깅을 수행한다.

## Minimum Policy

- 모든 작업은 `prompt`, `response`, `tools`, `actor`, `model`을 남긴다
- 코드 수정 작업은 `artifact`와 `approval`도 함께 남긴다
- 테스트 실행 여부는 반드시 `tools`에 남긴다

## Suggested Storage

- 개인 작업 중간 기록: `work-log.md`
- 중요 작업 구조화 기록: `tasks/*.json`
- 주간 리뷰: `weekly-review.md`

## Upgrade Trigger

아래 상황이면 SQLite로 확장한다.

- task JSON이 50개 이상 누적
- 모델별 비교가 필요
- 실패 패턴을 actor별로 보고 싶음
