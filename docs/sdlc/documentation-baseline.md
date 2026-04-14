# Documentation Baseline

## Purpose

Documentation must change with the software. This baseline defines what must be updated and when.

## Documentation Principles

- Docs are part of the deliverable.
- Behavior changes require documentation changes.
- Operator-facing changes require runbook and support updates.
- Architecture changes require architecture updates and possibly ADRs.
- User-facing changes require release notes and user guidance when applicable.

## Documentation Types to Review

- `claude.md`
- architecture docs
- API docs
- data or schema docs
- runbooks
- QA docs
- security docs
- support docs
- onboarding docs
- migration docs
- release notes
- user documentation

## Definition of Updated

A document is updated only when it:

- reflects the new behavior accurately
- removes now-wrong old behavior
- includes new operational or support expectations
- identifies any new risks, flags, or constraints

## Documentation Exit Rule

No change is done if a future engineer, operator, support agent, or auditor would still need tribal knowledge to understand what changed and how to work with it.

