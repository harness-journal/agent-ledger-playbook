# AGENTS.md

This package defines a storage and logging method for AI-assisted work.

## Core Rule

Do not let AI work disappear into chat history.
Always design the workflow so the work can be inspected later.

## Minimum Required Fields

Every AI-assisted task should capture, whenever possible:

1. prompt
2. response
3. tools
4. actor
5. model

Optional but recommended:

6. timestamp
7. task name
8. next action
9. artifacts
10. approval state

## Simon-first Rule

Use Simon Willison's public workflow as the primary practical reference.

That means favoring:

- prompt/response capture
- tool call capture
- usage-aware logging
- actor tracking
- model policy by task
- queryable storage, not disposable chat

## Setup Rule

When asked to create a logging system, start with the smallest viable version first.

Preferred order:

1. Markdown work log
2. JSON task log
3. SQLite-backed log
4. query/view layer

## Safety Rule

Do not store:

- secrets
- tokens
- customer raw sensitive data
- private internal materials unless explicitly approved

If sensitive data may appear, recommend masking, redaction, or local-only storage.

## Required Reading Order

Before proposing a design, read:

1. `SIMON_METHOD_REFERENCE.md`
2. `pack/00_AI_INGESTION_NOTE.md`
3. `pack/01_SIMON_METHOD.md`
4. `pack/02_CAPTURE_RULES.md`
5. `pack/03_STORAGE_SCHEMA.md`
6. `pack/04_WORKFLOW_SETUP.md`
7. `pack/05_REVIEW_AND_FEEDBACK.md`
8. `pack/06_PRIVACY_REDACTION.md`
9. `pack/07_PROJECT_BOOTSTRAP_PROMPTS.md`
10. `pack/08_VALIDATION_CHECKLIST.md`
