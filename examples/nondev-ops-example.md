# Non-Developer Ops Example

## Situation

운영 담당자와 콘텐츠 담당자가 AI로 메일 초안, 공지문, 요약 작업을 반복한다.

## Minimum Policy

- work-log.md 하나로 시작
- actor는 사람 이름 또는 역할명으로 통일
- 고객 원문은 저장하지 않고 summary only로 남긴다

## Suggested Storage

- 일일 작업 기록: `work-log.md`
- 팀 규칙: `team-policy.md`
- 주간 개선: `weekly-review.md`

## Upgrade Trigger

아래 상황이면 노션 테이블 또는 JSON 구조를 병행한다.

- 같은 작업이 주 10회 이상 반복
- 여러 사람이 같은 AI 규칙을 써야 함
- approval 흐름이 필요함
