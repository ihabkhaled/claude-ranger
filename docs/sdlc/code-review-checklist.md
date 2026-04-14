# Code Review Checklist

## Purpose

Use this checklist for every pull request or change review. A reviewer should be able to answer each item clearly.

## Review Preparation

- Read the request summary and linked phase artifacts.
- Confirm the PR scope matches the documented plan.
- Confirm the PR is reviewable in size and logically cohesive.

## Checklist

### Scope and Intent

- [ ] The change solves the documented problem.
- [ ] Scope is consistent with product requirements.
- [ ] Hidden extra behavior has not been introduced.

### Architecture and Design

- [ ] The change respects module and service boundaries.
- [ ] Architectural impacts are documented.
- [ ] A new ADR exists when architecture changed.
- [ ] Refactors are separated or clearly explained.

### Code Quality

- [ ] Naming is clear and consistent.
- [ ] Complexity is proportionate to the problem.
- [ ] Duplication is avoided or justified.
- [ ] Error handling is explicit.
- [ ] Logging and observability are present where needed.

### Security and Privacy

- [ ] Auth and permission behavior is correct.
- [ ] Sensitive data is protected and redacted.
- [ ] Input validation and output safety are covered.
- [ ] Abuse paths and misuse cases were considered.

### Data and Compatibility

- [ ] Schema or contract changes are documented.
- [ ] Migrations and rollback are present when needed.
- [ ] Backward compatibility impact is known.

### Tests

- [ ] Tests exist for the changed behavior.
- [ ] Tests cover happy path, failure path, and edge cases appropriate to the risk.
- [ ] Touched-module coverage meets the threshold or has an approved waiver.
- [ ] Regression scope is identified.

### Documentation

- [ ] Required docs were updated.
- [ ] Release notes were updated when behavior changed.
- [ ] Support or runbook docs were updated when operations changed.

### Release Readiness

- [ ] Feature flags, rollout, and rollback needs are covered.
- [ ] Monitoring and alerts are addressed when required.
- [ ] No unresolved blocker remains hidden in comments.

## Review Outcomes

- Use `MUST FIX` for blockers.
- Use `SHOULD FIX` for important improvements before merge when reasonable.
- Use `FOLLOW-UP` only for non-blocking items with explicit owner and due date.

## Approval Rule

Do not approve when a blocker remains unresolved, when artifacts are missing, or when the reviewer cannot explain the change with confidence.

