# Engineering Standards

## Purpose

This document defines the minimum engineering quality bar for any change that moves through the SDLC.

## Core Standards

### 1. Architecture Fit

- Respect approved architecture and domain boundaries.
- Reuse existing patterns unless a better approach is formally justified.
- New architecture decisions require ADRs.
- Avoid hidden coupling across modules, services, teams, or data stores.

### 2. Change Design

- Prefer small, reviewable changes.
- Separate refactors from behavior changes when practical.
- Keep interfaces explicit.
- Keep rollback practical.
- Make dependency changes deliberate and documented.

### 3. Code Quality

- Strong typing is mandatory.
- Public behavior must be easy to trace from input to output to side effect.
- Avoid dead code, placeholder logic, decorative UI, and hidden feature flags with no owner.
- Use consistent naming and module organization.
- Keep functions and modules focused.

### 4. Error Handling

- Handle happy path, failure path, timeout path, dependency failure path, and partial failure path.
- Expose machine-readable errors where systems integrate.
- Show meaningful user-facing errors where users interact.
- Never swallow errors without logging, metrics, and explicit intent.

### 5. Logging, Metrics, and Traces

- Emit structured logs for materially important actions and failures.
- Instrument key workflows with metrics.
- Preserve traceability across service or process boundaries.
- Redact secrets, credentials, tokens, and sensitive personal data.

### 6. Security and Privacy

- Follow least privilege.
- Validate inputs and encode outputs.
- Protect secrets in transit, at rest, and in logs.
- Define data classification, retention, masking, and deletion expectations.
- Review abuse cases, misuse cases, and tenant-isolation risks.

### 7. Data and Schema Change Rules

- Every schema change requires migration planning and rollback planning.
- Every backfill requires monitoring, retry behavior, failure handling, and completion validation.
- Every data contract change requires compatibility analysis.
- Do not mutate production data blindly.

### 8. API and Contract Rules

- Document contract changes before release.
- Preserve backward compatibility unless a breaking change is explicitly approved.
- Version or stage breaking changes when needed.
- Define status codes, validation errors, and rate-limit behavior clearly.

### 9. Frontend Standards

- Accessibility is required, not optional.
- Internationalization or localization must be respected for user-facing text when the product supports it.
- Loading, empty, success, and error states must all be designed.
- Buttons, links, actions, and controls must perform meaningful work or be visibly disabled with reason.

### 10. Performance and Reliability

- Consider latency, throughput, scaling, retries, idempotency, caching, and concurrency where relevant.
- Define SLO or operational expectations for business-critical changes.
- Test failure recovery and degraded behavior.

### 11. Testability

- Code must be written in a way that is observable and testable.
- Critical logic must be scenario-rich, not percentage-rich only.
- Every change must have traceable test coverage.

### 12. Documentation

- Docs are part of the definition of done.
- Update user, support, architecture, API, and operations docs as needed.
- Keep examples, screenshots, diagrams, and workflows current.

## Review Questions

- Does the change fit the current architecture?
- Is the design understandable and maintainable?
- Are failures handled deliberately?
- Is the blast radius clear?
- Is the change observable?
- Is the rollback realistic?
- Are docs updated?
- Are tests good enough for the real risk?

## Non-Compliance

If a change cannot meet a standard, the gap must be documented with risk, compensating controls, approver, and follow-up owner. Silent non-compliance is not allowed.

