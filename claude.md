# Enterprise SDLC Operating Brain

> Every request must pass through full business, product, architecture, impact, standards, testing, implementation, QA, security, UAT, risk, documentation, release, hypercare, and retrospective phases with written artifacts and hard gates; no step may be skipped, and no change may ship unless it is reviewed, tested, secure, observable, documented, and operationally reversible.

## Purpose

This file is the permanent operating brain for AI-assisted delivery. It is not a feature document. It defines the standing company policy that every engineer, reviewer, delivery lead, QA analyst, AppSec reviewer, product owner, and AI coding assistant must follow for every request.

If a local workflow, ticket comment, chat thread, or urgent request conflicts with this file, this file wins unless an authorized leader approves an explicit exception in writing.

## Scope

This policy applies to all features, bug fixes, enhancements, refactors, migrations, integrations, experiments that may ship, security improvements, UX changes, API changes, database changes, infrastructure changes, analytics changes, AI workflow changes, and operational changes.

## Standing Instruction to Claude or Any AI Coding Agent

You are operating inside a strict enterprise SDLC. This workflow is mandatory and must never be skipped, compressed away, ignored, or bypassed, even for small changes. Depth may scale by request size, but every phase and gate must still exist.

Your job whenever you receive a new feature, bug fix, enhancement, refactor, migration, integration, security improvement, UX change, API change, database change, workflow modification, or any product or technical request is to execute this workflow step by step, document everything, and keep all artifacts updated.

## General Operating Rules

1. Never skip any phase.
2. Never jump directly to implementation.
3. Always start with request intake, analysis, requirements, architecture, impact, standards, and testing.
4. Always document every phase in the correct file.
5. Always update `claude.md` and, when your environment uses it, the mirrored `CLAUDE.md` compatibility file if any new permanent rule, workflow, pattern, standard, architecture constraint, testing rule, release rule, or quality rule is discovered.
6. Always use a production-grade mindset: reliable, secure, reviewed, testable, observable, maintainable, reversible, and well documented.
7. If information is missing, do not stop. Make best-effort assumptions, label them clearly, and continue while highlighting the related risk.
8. Prefer small, reviewable changes instead of giant changes.
9. Keep tests in the same change as the logic whenever possible.
10. Keep documentation in the same change as the behavior whenever possible.
11. Treat touched-module coverage as the enforcement target; repository-wide averages cannot hide weak testing in changed code.
12. No work is done when the code compiles. Work is done when business intent, product behavior, architecture fit, risk, testing, docs, support, rollout, rollback, and operational readiness are all covered.

## Required Output Order for Every Request

Whenever an AI agent responds to a request, it must organize its work in this order:

1. Request classification
2. Assumptions
3. Phase tracker
4. Summary of the current request
5. Business analysis
6. Product requirements
7. Architecture and impact analysis
8. Engineering standards review
9. Test strategy and coverage plan
10. Delivery plan and technical roadmap
11. Documentation plan
12. Risks and blockers
13. Implementation plan or code work only after phases `00` through `13` are documented

## Mandatory Repository Structure

```text
/claude.md
/docs/sdlc/
/docs/features/<feature-slug>/
/test-cases/
/runbooks/
/architecture/adrs/
/release-notes/
/support/
```

The canonical phase documents for each request are:

- `00-intake.md`
- `01-business-analysis.md`
- `02-business-development.md`
- `03-product-requirements.md`
- `04-cross-functional-refinement.md`
- `05-delivery-plan.md`
- `06-technical-refinement.md`
- `07-technical-roadmap.md`
- `08-architecture-review.md`
- `09-impact-analysis.md`
- `10-engineering-standards-check.md`
- `11-test-strategy.md`
- `12-coverage-plan.md`
- `13-implementation-readiness.md`
- `15-dev-validation-report.md`
- `16-dev-bug-log.md`
- `17-qa-report.md`
- `18-defect-cycle-log.md`
- `19-threat-model.md`
- `19-security-review.md`
- `19-pentest-report.md`
- `20-uat-report.md`
- `21-client-approval.md`
- `22-go-no-go.md`
- `23-documentation-changelog.md`
- `24-risk-compliance-ops.md`
- `25-release-report.md`
- `26-hypercare-report.md`
- `27-retrospective.md`
- `27-postmortem.md` when a significant defect or incident occurred

Phase `14` is implementation and does not require a standalone markdown file because the artifacts are the code, tests, migrations, dashboards, release notes, and docs created during the change.

## Phase Policy

### Phase 0 - Request Intake and Classification

- Assign a unique request ID.
- Classify the request type and affected domains.
- Assess severity, urgency, critical path impact, and whether the request requires the standard or hotfix track.
- Flag whether it touches money flow, auth, permissions, privacy, tenant isolation, health or safety concerns, reporting, or external integrations.
- Required artifact: `00-intake.md`

### Phase 1 - Business Analysis

- Define the real business problem, not only the requested solution.
- Identify stakeholders, user pain, desired outcome, business value, and measurable success metrics.
- Define current state, desired state, assumptions, dependencies, and risks of not delivering.
- Required artifact: `01-business-analysis.md`

### Phase 2 - Business Development / Commercial Impact

- Evaluate commercial value, customer segment impact, contract or SLA implications, rollout audience, and adoption risk.
- Required artifact: `02-business-development.md`

### Phase 3 - Product Requirements

- Define epics, user stories, acceptance criteria, scope boundaries, non-goals, UX expectations, error states, permissions, analytics, and definition of done.
- Required artifact: `03-product-requirements.md`

### Phase 4 - Cross-Functional Refinement

- Review the request with engineering, QA, security, DevOps, support, analytics, and other impacted functions.
- Surface hidden complexity, missing requirements, and cross-system implications.
- Required artifact: `04-cross-functional-refinement.md`

### Phase 5 - Delivery Planning

- Break the work into milestones, workstreams, dependencies, blockers, approvals, rollout strategy, and sequencing.
- Required artifact: `05-delivery-plan.md`

### Phase 6 - Technical Refinement

- Evaluate implementation approaches, alternatives, trade-offs, maintainability, security, performance, backward compatibility, and cost.
- Record the chosen path and rejected alternatives with reasons.
- Required artifact: `06-technical-refinement.md`

### Phase 7 - Technical Roadmap

- Plan the engineering execution slices, merge strategy, schema evolution, rollout sequence, and rollback sequence.
- Required artifact: `07-technical-roadmap.md`

### Phase 8 - Architecture Review

- Re-check architecture, patterns, service boundaries, ownership, contracts, workflows, and data flow.
- Create or update ADRs when an architectural decision changes.
- Required artifact: `08-architecture-review.md`

### Phase 9 - Full Impact Analysis

- Assess blast radius across backend, frontend, mobile, database, analytics, reporting, DevOps, security, QA, documentation, support, operations, monitoring, release engineering, and customer workflows.
- Required artifact: `09-impact-analysis.md`

### Phase 10 - Engineering Standards Review

- Re-check code quality rules, naming, module boundaries, linting, logging, observability, accessibility, internationalization, error handling, and secure coding requirements.
- Update this file if a new lasting standard is established.
- Required artifact: `10-engineering-standards-check.md`

### Phase 11 - Test Strategy

- Design unit, integration, repository, database, service, module, API, UI, UX, E2E, regression, RBAC, analytics, migration, rollback, negative, edge, race-condition, and external-failure tests.
- Store detailed test cases under `test-cases/`.
- Required artifact: `11-test-strategy.md`

### Phase 12 - Coverage Strategy

- Enforce at least `95%` lines, branches, functions, and statements for touched modules unless an explicit written waiver is approved.
- Required artifact: `12-coverage-plan.md`

### Phase 13 - Implementation Readiness

- Prepare branches, flags, migrations, rollback, observability, test scaffolding, dashboards, alerts, seed or backfill plans, and release controls.
- Required artifact: `13-implementation-readiness.md`

### Phase 14 - Implementation

- Implementation may start only after phases `00` through `13` are documented.
- Implement in small, reviewable slices.
- Keep tests, docs, migrations, telemetry, resilience, and release artifacts in the same delivery stream.

### Phase 15 - Developer Validation

- Run linting, type checks, static analysis, unit tests, integration tests, E2E tests where applicable, and manual exploratory validation.
- Validate logs, metrics, DB side effects, events, jobs, retries, status codes, and acceptance criteria.
- Required artifact: `15-dev-validation-report.md`

### Phase 16 - Internal Bug Loop

- Track defects found by the implementation team, fix them, re-test, re-run regression, and repeat until stable.
- Required artifact: `16-dev-bug-log.md`

### Phase 17 - Independent QA Validation

- QA validates APIs, UI, workflows, edge cases, regression scope, and business behavior independently.
- Required artifact: `17-qa-report.md`

### Phase 18 - QA Defect Loop

- Every QA defect returns through fix, re-test, regression, doc update when needed, and QA re-validation.
- Required artifact: `18-defect-cycle-log.md`

### Phase 19 - Security Testing and AppSec Review

- Threat model the change.
- Review auth, authorization, rate limits, secrets handling, tenant isolation, file handling, privacy, dependency risk, logging leakage, CI/CD controls, and deployment safety.
- Required artifacts: `19-threat-model.md`, `19-security-review.md`, `19-pentest-report.md`

### Phase 20 - UAT / Business Testing

- Validate real-world business workflows, wording, UX clarity, reporting, operational usefulness, and whether the original business pain is actually solved.
- Required artifact: `20-uat-report.md`

### Phase 21 - Client Testing and Approval

- Provide release notes, known constraints, test scope, demo steps, and approval checklist to the client or external stakeholder when applicable.
- Required artifact: `21-client-approval.md`

### Phase 22 - Go / No-Go Governance

- Review readiness across delivery scope, defects, risk, rollback, support, observability, migration, feature flags, compliance, and communications.
- Required artifact: `22-go-no-go.md`

### Phase 23 - Documentation and Knowledge Updates

- Update `claude.md`, any mirrored uppercase compatibility file if used, architecture docs, API docs, workflows, runbooks, support docs, security docs, onboarding docs, migration docs, release notes, and user docs as needed.
- Required artifact: `23-documentation-changelog.md`

### Phase 24 - Risk / Compliance / Operational Readiness

- Review business, technical, legal, compliance, operational, and reputational risk.
- Confirm monitoring, alerting, escalation, runbooks, and support readiness.
- Required artifact: `24-risk-compliance-ops.md`

### Phase 25 - Release and Delivery

- Release using the approved strategy.
- Validate production smoke tests, data changes, external integrations, logs, metrics, traces, and rollback readiness.
- Required artifact: `25-release-report.md`

### Phase 26 - Hypercare

- Monitor incidents, error rates, support load, adoption, SLO impact, and abnormal behavior during the defined hypercare window.
- Required artifact: `26-hypercare-report.md`

### Phase 27 - Retrospective and Postmortem

- Run a retrospective for every delivery.
- Run a blameless postmortem for serious incidents, major defects, or failed launches.
- Record process, architecture, testing, operational, and documentation improvements.
- Required artifact: `27-retrospective.md`
- Additional artifact when applicable: `27-postmortem.md`

## Non-Negotiable Gates

- No implementation before phases `00` through `13` are complete.
- No pull request without tests.
- No pull request without documentation updates when behavior changes.
- No merge when touched-module coverage is below threshold unless a documented waiver is approved.
- No merge if lint, type checks, static analysis, tests, or security checks fail.
- No merge if architecture impact is undocumented.
- No release without QA sign-off.
- No release without security validation.
- No release without a rollback plan.
- No release without observability, alerting, and smoke tests.
- No release without documentation updates.
- No release without go/no-go approval.
- No release without required client or business approval where applicable.

## Approval Workflow

- Intake owner confirms classification and request ID.
- Product owner approves business framing and product requirements.
- Engineering lead approves technical direction and architecture fit.
- QA lead approves the test strategy and QA sign-off.
- Security lead approves security review when applicable.
- Operations or SRE lead approves readiness for rollout, observability, and rollback.
- Business owner approves UAT.
- Client or external stakeholder approves when contractually required.
- Release manager or delegated approver records the go/no-go decision.

If a company uses different titles, map local roles to these responsibilities and document the mapping in `docs/sdlc/company-sdlc-policy.md`.

## Defect Workflow

1. Log the defect with request ID, severity, environment, reproducer, and owner.
2. Determine whether the defect is a blocker, release risk, or accepted limitation.
3. Fix the defect in a small, reviewable change.
4. Add or update tests for the exact failure mode and nearby regression scope.
5. Re-run relevant validation and regression.
6. Return the build to QA or the reporting party.
7. Update release notes, support notes, and postmortem action items if the issue escaped late.

## Engineering Rules

### Architecture and Ownership

- Respect domain and module boundaries.
- One service or module owns each data domain.
- Shared contracts must be versioned or changed carefully with compatibility analysis.
- Architectural changes require ADRs.
- Refactors must preserve behavior unless the change is explicitly approved as a behavior change.

### Code Quality

- Strong typing is mandatory.
- Keep changes small, reviewable, and logically scoped.
- Prefer existing patterns and approved abstractions over inventing new ones.
- Avoid hidden side effects.
- Keep public interfaces explicit and stable.
- Every change must be understandable by a reviewer without tribal knowledge.

### Data and Migrations

- Schema changes require forward and rollback planning.
- Data migrations, backfills, and cleanup jobs need explicit monitoring and retry behavior.
- Sensitive data needs classification, minimization, retention rules, and masking in logs and lower environments.

### Security

- Least privilege is the default.
- Protect secrets and credentials in transit, at rest, and in logs.
- Validate input, encode output, and review abuse paths.
- Keep tenant boundaries explicit and testable.
- Review dependencies and supply-chain controls before release.

### Observability

- Every materially changed workflow must emit useful logs, metrics, traces, and alerts.
- Correlation IDs or equivalent traceability are mandatory across distributed flows.
- Dashboards and alert routing must exist before release for production-critical changes.

### Documentation

- Documentation is part of the change, not a follow-up task.
- Update system, API, support, security, operational, and onboarding docs when affected.
- Release notes must be written for user-visible or operator-visible changes.

## Testing Thresholds

- Minimum touched-module coverage: `95%` lines, branches, functions, statements
- Critical logic areas should be near-complete and scenario-rich: auth, permissions, money flow, calculations, privacy, migrations, transformations, tenant isolation, and external integrations
- Coverage numbers do not replace scenario quality
- Waivers require explicit written approval, justification, and compensating controls

## Release, Rollout, and Rollback Rules

- Prefer staged rollout, canary, tenant-scoped release, dark launch, shadow mode, or feature flags when risk justifies them.
- Define rollback triggers before release.
- Keep rollback technically feasible until stability is confirmed.
- Production smoke tests must be written, rehearsed, and executed.
- Release communications must be prepared before go/no-go.

## Incident, Hypercare, and Postmortem Rules

- Significant defects or incidents require rapid triage, transparent communication, and explicit ownership.
- Hypercare is a planned operating window, not informal watchfulness.
- Retrospectives are mandatory for every shipped request.
- Serious incidents require blameless postmortems with timeline, impact, root cause, contributing factors, action items, owners, and due dates.

## When This File Must Be Updated

Update `claude.md` and any mirrored uppercase compatibility file whenever a new permanent rule or expectation appears in any of these areas:

- SDLC phases or gates
- architecture rules
- design patterns
- module boundaries
- coding standards
- testing standards
- security rules
- QA workflow
- release process
- rollback policy
- observability policy
- incident handling
- documentation requirements
- support readiness
- approval mapping

## Final Instruction

Treat this file as company policy, not advice. Do not skip detail because a request looks small. Do the work in order, write the artifacts, respect the gates, and optimize for software that is correct, secure, testable, observable, supportable, and reversible.
