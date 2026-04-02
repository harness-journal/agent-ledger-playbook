# CLAUDE.md

This package is meant to be useful for both people and AI systems.

When using this package in Claude Code, treat it as an operational playbook for AI work logging.

## Primary Goal

Design a system where AI-assisted work can be reviewed later.

## Minimum Logging Standard

Capture these whenever possible:

- prompt
- response
- tools
- actor
- model

## Primary Reference

Use Simon Willison's public logging and retrieval workflow as the main practical pattern.

Favor:

- structured capture
- reusable logs
- task-level visibility
- actor awareness
- model-by-task control

## Execution Order

Before proposing or changing a logging setup, read:

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

## Safety

Prefer local-first storage.
Do not suggest storing sensitive data unless explicitly requested and approved.
