# Enterprise SDLC Operating Brain

> Every request must pass through full business, product, architecture, impact, standards, testing, implementation, QA, security, UAT, risk, documentation, release, hypercare, and retrospective phases with written artifacts and hard gates; no step may be skipped, and no change may ship unless it is reviewed, tested, secure, observable, documented, and operationally reversible.

## Purpose

This file is the permanent operating brain for AI-assisted delivery. It is not a feature document. It is the standing company policy that defines how software work must be classified, analyzed, planned, implemented, validated, documented, released, monitored, and improved.

The point of this file is to remove ambiguity. Nothing important should depend on unstated tribal knowledge, hidden habits, assumed seniority, or optimism.

## Authority And Precedence

If a ticket, sprint note, chat message, verbal request, or local team habit conflicts with this file, this file wins unless an authorized approver records an explicit exception in writing.

This file is policy, not advice.

## Scope

This policy applies to:

- features
- enhancements
- bug fixes
- refactors
- migrations
- integrations
- security fixes
- performance work
- UX changes
- API changes
- database changes
- analytics changes
- workflow changes
- infrastructure changes
- AI behavior changes
- platform changes
- internal tools
- customer-facing systems

## How To Apply This File In Any Codebase

This file is intentionally generic. It must work across languages, frameworks, and architectures.

Map local structures to these generic responsibilities:

- transport layer: controllers, routes, handlers, resolvers, RPC endpoints, actions
- application layer: services, use cases, orchestration flows, commands, workflows
- domain layer: policies, business rules, calculations, invariants, decisions
- data layer: repositories, DAOs, persistence adapters, gateways
- integration layer: third-party clients, SDK wrappers, event publishers, queue consumers
- presentation layer: pages, screens, components, templates, clients
- operational layer: CI/CD, deployment, runtime config, observability, support, runbooks

If the codebase uses different naming, the responsibility still exists even if the class or file names differ.

On case-sensitive filesystems, teams may mirror this file to `CLAUDE.md` if their tooling expects that name. On case-insensitive filesystems, `claude.md` is the canonical file.

## Standing Instruction To Claude Or Any AI Coding Agent

You are operating inside a strict enterprise SDLC. This workflow is mandatory and must never be skipped, compressed away, ignored, or bypassed, even for small changes. Depth may scale by request size, but every phase and gate must still exist.

Whenever you receive a request, you must:

1. classify the request
2. document the phases in order
3. surface assumptions instead of hiding them
4. surface risk instead of hand-waving it
5. implement only after phases `00` through `13` are documented
6. validate through the correct test layers
7. update documentation with the change
8. refuse to label incomplete work as done

If information is missing, do not stop by default. Make the best reasonable assumptions, label them clearly, record the risk, and continue until a real blocker exists.

## General Operating Rules

1. Never skip any phase.
2. Never jump directly to implementation.
3. Always start with request intake, business analysis, product framing, architecture review, impact review, standards review, and test planning.
4. Always document every phase in the correct artifact.
5. Always update `claude.md` and any uppercase compatibility mirror if a new permanent rule, workflow, standard, architecture constraint, testing expectation, release rule, or quality gate is discovered.
6. Always prefer small, reviewable changes over large, opaque changes.
7. Always keep tests in the same delivery stream as the behavior they validate.
8. Always keep docs in the same delivery stream as the behavior they explain.
9. Always measure coverage on touched modules, not only repository-wide averages.
10. Always review blast radius before changing code.
11. Always make changes observable, supportable, and reversible.
12. Always expose assumptions, risks, open questions, and dependencies explicitly.
13. Never treat compile success as proof of correctness.
14. Never treat a passing happy path as adequate validation.
15. Never treat undocumented behavior as complete implementation.
16. Never treat a bug as fixed when only the visible symptom disappeared.
17. Never hide missing work behind vague wording such as "mostly done" or "follow-up later."
18. Never skip documentation because the request looks small.
19. Never skip rollback thinking because the request looks safe.
20. Never leave support, operations, QA, or security surprised by a release.

## Mandatory Read-Before-Acting Sequence

Before doing analysis or implementation work, the assigned engineer or AI agent must:

1. read this root `claude.md`
2. read the request artifacts if the request already exists
3. read relevant architecture docs, ADRs, standards, and runbooks
4. read the code that will be modified before changing it
5. read existing tests for the affected area before adding or changing behavior
6. read recent incidents, bug reports, and support signals if the request is related to a known issue
7. read deployment, config, security, or routing docs if the change touches runtime or exposure concerns

No one should modify code they have not read.

## Required Output Order For Every Request

Whenever an AI agent responds to a request, it must organize the work in this order:

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

If implementation work is completed in the same response, also include:

14. changed files summary
15. validation evidence summary
16. documentation updates summary
17. known gaps, waivers, blockers, or follow-up items

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

The canonical request artifacts are:

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
- `27-postmortem.md` when applicable

Phase `14` is implementation and does not require a standalone markdown artifact because the artifacts are the code, tests, migrations, observability assets, and documentation created during the change.

## Artifact Rules

1. If a section is not applicable, write `Not applicable`, explain why, and name who accepted that conclusion.
2. Do not leave silent blanks for meaningful sections.
3. Keep assumptions visible until resolved or explicitly accepted.
4. Link related tickets, dashboards, pull requests, ADRs, incident IDs, and evidence where useful.
5. Update artifacts during the phase, not from memory after the fact.
6. Treat artifacts as living records, not ceremony.

## Minimum Document Contents By Artifact

Each request artifact must contain at least the following:

- `00-intake.md`: request ID, title, type, source, owners, severity, urgency, affected domains, delivery track, critical-risk flags, initial scope statement
- `01-business-analysis.md`: problem statement, stakeholders, personas, current state, desired state, business goals, success metrics, assumptions, dependencies, risks of not doing the work
- `02-business-development.md`: commercial value, target segment or accounts, contract or SLA impact, rollout audience, adoption risks, enablement notes
- `03-product-requirements.md`: epics, user stories, acceptance criteria, in-scope items, out-of-scope items, non-goals, UX expectations, error states, permissions expectations, analytics expectations, localization expectations, product definition of done
- `04-cross-functional-refinement.md`: participant list, findings by function, hidden work, integration points, missing requirements, open questions, decisions, owners
- `05-delivery-plan.md`: workstreams, milestones, sequence, dependencies, blockers, approvals, rollout strategy, risk list
- `06-technical-refinement.md`: technical context, alternatives considered, trade-offs, chosen approach, rejected approaches, open technical questions, debt impact
- `07-technical-roadmap.md`: engineering milestones, branch and merge strategy, schema evolution plan, rollout sequence, rollback sequence, flag and compatibility notes
- `08-architecture-review.md`: current architecture context, impact by area, boundary changes, contract changes, data-flow changes, ADR decision, architecture risks
- `09-impact-analysis.md`: affected systems, affected teams, backward compatibility, migration needs, monitoring impact, support impact, training impact, compliance impact
- `10-engineering-standards-check.md`: standards review matrix, request-specific rules, permanent-rule update check, implementation constraints
- `11-test-strategy.md`: requirement-to-test mapping, test layers, negative and edge cases, migration and rollback tests, environment needs, evidence plan, linked test-case locations
- `12-coverage-plan.md`: touched modules, required thresholds, critical scenario areas, evidence plan, waiver status
- `13-implementation-readiness.md`: branch strategy, slices, flags, config changes, migration plan, rollback plan, observability plan, review readiness, release readiness, open readiness gaps
- `15-dev-validation-report.md`: validation summary, commands or activities run, functional coverage, operational checks, acceptance-criteria validation, defects found
- `16-dev-bug-log.md`: bug table, severity, owner, fix status, retest status, regression rerun notes, stability decision
- `17-qa-report.md`: QA inputs, scenario matrix, API validation, UI validation, end-to-end validation, findings, QA decision
- `18-defect-cycle-log.md`: defect list, fix cycle status, retest status, regression status, behavior changes during fixes, return-to-QA notes
- `19-threat-model.md`: scope, assets, trust boundaries, threat scenarios, abuse cases, mitigations, residual risk
- `19-security-review.md`: security checklist coverage, findings, waivers, decision, reviewer, date
- `19-pentest-report.md`: scope, techniques used, executed cases, findings, residual risk, remediation ownership
- `20-uat-report.md`: UAT participants, scenarios, business fit assessment, findings, UAT decision
- `21-client-approval.md`: review package shared, client feedback, approval status, conditions, notes
- `22-go-no-go.md`: readiness review by area, remaining risks, final decision, decision owner, conditions
- `23-documentation-changelog.md`: all updated documents, why each changed, remaining documentation gaps, owners
- `24-risk-compliance-ops.md`: reviewer list, review areas, status, findings, final readiness decision
- `25-release-report.md`: release summary, deployment steps executed, smoke-test results, production checks, issues during release, final status
- `26-hypercare-report.md`: hypercare window, observed signals, actions taken, conclusion, follow-ups
- `27-retrospective.md`: what went well, what did not, process improvements, engineering improvements, documentation improvements, follow-up actions, `claude.md` update needs
- `27-postmortem.md`: incident summary, impact, timeline, root cause, contributing factors, detection review, corrective actions, policy and process changes

## Phase Policy

### Phase 0 - Request Intake And Classification

Purpose: classify the request before solutioning begins.

What must happen:

- assign a unique request ID
- classify request type
- identify affected domains
- assess severity and urgency
- decide whether this is standard track or hotfix track
- identify whether money flow, auth, permissions, privacy, tenant isolation, compliance, external integrations, reporting, or critical workflows are touched
- assign owners

Required artifact: `00-intake.md`

Exit criteria:

- the request is classified
- the request has owners
- the request has an initial scope statement
- the request criticality is visible

### Phase 1 - Business Analysis

Purpose: define the actual business problem before implementation details take over.

What must happen:

- define the real business pain
- identify stakeholders and affected user groups
- describe current state and desired state
- define measurable success metrics
- document assumptions, dependencies, and consequences of not delivering

Required artifact: `01-business-analysis.md`

Exit criteria:

- business intent is explicit
- business value is stated
- success is measurable

### Phase 2 - Business Development / Commercial Impact

Purpose: confirm the request makes sense commercially, strategically, and contractually.

What must happen:

- evaluate commercial value
- define target audience or rollout audience
- review contract or SLA implications
- identify adoption and enablement risk

Required artifact: `02-business-development.md`

Exit criteria:

- commercial or strategic justification exists
- rollout audience is defined
- contract risk is visible

### Phase 3 - Product Requirements

Purpose: translate business intent into product behavior.

What must happen:

- define epics and user stories
- define acceptance criteria
- define scope boundaries and non-goals
- define UX, permission, notification, analytics, localization, and error-state expectations
- define product-level definition of done

Required artifact: `03-product-requirements.md`

Exit criteria:

- requirements are testable
- scope boundaries are visible
- product behavior is explicit

### Phase 4 - Cross-Functional Refinement

Purpose: surface hidden work before implementation planning hardens.

What must happen:

- review with engineering, QA, security, DevOps or SRE, support, analytics, and any other impacted function
- surface missing requirements
- identify integration points and support impact
- identify observability, migration, and permission implications

Required artifact: `04-cross-functional-refinement.md`

Exit criteria:

- hidden work is exposed
- missing requirements are captured
- cross-functional concerns are visible

### Phase 5 - Delivery Planning

Purpose: convert the request into an executable plan.

What must happen:

- break work into milestones and workstreams
- assign owners
- sequence dependencies
- identify blockers
- identify required approvals
- define rollout approach

Required artifact: `05-delivery-plan.md`

Exit criteria:

- there is a realistic path to delivery
- dependencies and blockers are visible
- workstreams are owned

### Phase 6 - Technical Refinement

Purpose: choose the technical direction deliberately.

What must happen:

- evaluate implementation alternatives
- compare simplicity, maintainability, scalability, performance, security, cost, reliability, and compatibility
- choose an approach and explain why
- record rejected alternatives
- record open technical questions

Required artifact: `06-technical-refinement.md`

Exit criteria:

- technical direction is selected
- trade-offs are documented
- rejected options are documented

### Phase 7 - Technical Roadmap

Purpose: define engineering execution slices.

What must happen:

- define incremental milestones
- define branch and merge strategy
- define schema evolution order
- define rollout order
- define rollback order
- prefer small reviewable slices instead of large entangled changes

Required artifact: `07-technical-roadmap.md`

Exit criteria:

- implementation order is explicit
- merge and release sequencing are explicit
- rollback sequencing is explicit

### Phase 8 - Architecture Review

Purpose: ensure the solution fits the current architecture or intentionally evolves it with traceability.

What must happen:

- review architecture docs, domain boundaries, ownership, workflows, and contracts
- identify data-flow and topology impact
- identify required ADRs
- identify intentional deviations and why they are acceptable

Required artifact: `08-architecture-review.md`

Exit criteria:

- architecture fit is documented
- required ADR decisions are made
- ownership impact is visible

### Phase 9 - Full Impact Analysis

Purpose: expose the full blast radius so no team is surprised later.

What must happen:

- review impact across engineering, QA, security, analytics, reporting, DevOps or SRE, documentation, support, operations, monitoring, release engineering, and customer success
- review backward compatibility
- review migration needs
- review support and training implications
- review privacy and compliance implications

Required artifact: `09-impact-analysis.md`

Exit criteria:

- affected systems are identified
- affected teams are identified
- compatibility and migration impacts are documented

### Phase 10 - Engineering Standards Review

Purpose: freeze the implementation rules before coding.

What must happen:

- review architecture boundaries
- review code quality expectations
- review logging and observability rules
- review accessibility and localization expectations
- review secure coding expectations
- identify request-specific rules
- update `claude.md` if a new lasting standard is discovered

Required artifact: `10-engineering-standards-check.md`

Exit criteria:

- implementation constraints are explicit
- standards are visible to everyone doing the work
- any permanent-rule update decision is recorded

### Phase 11 - Test Strategy

Purpose: design quality before implementation starts.

What must happen:

- map requirements and risks to test layers
- define unit, integration, contract, UI, UX, E2E, regression, migration, rollback, permission, analytics, and security tests
- define environments and test data
- define evidence expectations

Required artifact: `11-test-strategy.md`

Exit criteria:

- testing is comprehensive enough for the risk
- test layers are mapped to requirements and risks
- environments and evidence expectations are defined

### Phase 12 - Coverage Strategy

Purpose: define the measurable coverage gate.

What must happen:

- define touched-module coverage thresholds
- define critical scenario areas
- define how coverage will be measured and reviewed
- record waivers if needed

Required artifact: `12-coverage-plan.md`

Exit criteria:

- coverage expectations are enforceable
- touched modules are identified
- waiver status is documented

### Phase 13 - Implementation Readiness

Purpose: prepare safely before coding.

What must happen:

- confirm phases `00` through `12` are sufficient to begin
- prepare branch strategy
- prepare flags and config changes
- prepare migrations and rollback
- prepare observability
- prepare review and test scaffolding
- identify release controls and approvers

Required artifact: `13-implementation-readiness.md`

Exit criteria:

- the team can start implementation safely
- major readiness gaps are either closed or explicitly accepted

### Phase 14 - Implementation

Purpose: implement according to the approved plan.

What must happen:

- implement in small, reviewable slices
- keep tests with the code whenever possible
- keep docs with the code whenever behavior changes
- respect architecture and module boundaries
- add observability, resilience, validation, and error handling as part of implementation
- keep rollback and supportability in view

Required artifacts:

- code
- tests
- migrations or data change scripts when needed
- observability updates when needed
- documentation updates when needed
- release notes draft when behavior is user-visible or operator-visible

Exit criteria:

- implementation is complete and internally coherent
- implementation artifacts exist alongside the change

### Phase 15 - Developer Validation

Purpose: the implementation team proves its own work before handoff.

What must happen:

- run linting
- run type checks or language-appropriate static analysis
- run unit tests
- run integration tests
- run E2E tests where applicable
- run manual exploratory validation
- validate logs, metrics, state transitions, jobs, queues, retries, and acceptance criteria

Required artifact: `15-dev-validation-report.md`

Exit criteria:

- the team can credibly say the feature works before QA sees it
- evidence exists for the validations performed

### Phase 16 - Internal Bug Loop

Purpose: the implementation team must find and fix its own defects aggressively.

What must happen:

- track defects
- classify severity
- fix defects
- re-test fixes
- re-run regression
- repeat until internally stable

Required artifact: `16-dev-bug-log.md`

Exit criteria:

- internal blocking defects are zero or explicitly accepted with approval
- stability status is recorded

### Phase 17 - Independent QA Validation

Purpose: independent validation of product intent and implementation behavior.

What must happen:

- validate APIs, UI, flows, permissions, data behavior, edge cases, and regression scope
- validate end-to-end workflows
- verify the system matches requirements and real usage expectations

Required artifact: `17-qa-report.md`

Exit criteria:

- QA signs off or returns defects

### Phase 18 - QA Defect Loop

Purpose: send QA-found defects back through the full engineering quality cycle.

What must happen:

- fix defects
- add or update tests
- re-run relevant automation
- update docs when behavior changes
- return to QA
- repeat until QA signs off

Required artifact: `18-defect-cycle-log.md`

Exit criteria:

- a QA-approved build exists

### Phase 19 - Security Testing And AppSec Review

Purpose: validate security, privacy, abuse resistance, and operational security.

What must happen:

- threat model the change
- review authentication and authorization
- review secrets handling
- review input validation and output safety
- review abuse controls and rate limits
- review data handling, logging leakage, and privacy boundaries
- review dependency and CI/CD risk
- perform dynamic validation when the risk warrants it

Required artifacts:

- `19-threat-model.md`
- `19-security-review.md`
- `19-pentest-report.md`

Exit criteria:

- no unresolved critical or high-risk issue remains unless explicitly waived by authorized leadership

### Phase 20 - UAT / Business Testing

Purpose: validate the solution against real business use.

What must happen:

- validate practical workflows
- validate wording and operator usability
- validate business rules and reporting expectations
- validate whether the original pain is actually solved

Required artifact: `20-uat-report.md`

Exit criteria:

- business owner signs off or rejects

### Phase 21 - Client Testing And Approval

Purpose: obtain external stakeholder approval when needed.

What must happen:

- provide release notes, demo path, known constraints, and approval checklist
- capture feedback and change requests
- route defects back through implementation, QA, security, and UAT as needed

Required artifact: `21-client-approval.md`

Exit criteria:

- client approves or formally defers approval

### Phase 22 - Go / No-Go Governance

Purpose: perform the formal release gate decision.

What must happen:

- review scope delivered
- review open defects
- review risk
- review rollback readiness
- review support and observability readiness
- review migration readiness
- review compliance and approval status
- record a clear GO or NO-GO decision

Required artifact: `22-go-no-go.md`

Exit criteria:

- signed release decision exists

### Phase 23 - Documentation And Knowledge Updates

Purpose: update institutional memory before release, not later.

What must happen:

- update `claude.md`
- update architecture docs
- update API and contract docs
- update runbooks
- update support docs
- update QA and security docs
- update onboarding and migration docs
- update release notes
- update user docs when behavior changed

Required artifact: `23-documentation-changelog.md`

Exit criteria:

- documentation is current enough for engineering, QA, security, support, and operations

### Phase 24 - Risk / Compliance / Operational Readiness

Purpose: confirm enterprise readiness before release.

What must happen:

- review business, technical, security, privacy, legal, operational, and reputational risk
- confirm monitoring and alerting
- confirm escalation paths
- confirm support readiness
- confirm compliance and policy implications

Required artifact: `24-risk-compliance-ops.md`

Exit criteria:

- risks are accepted, mitigated, or blocked explicitly

### Phase 25 - Release And Delivery

Purpose: deploy in a controlled way.

What must happen:

- release using the approved strategy
- execute smoke tests
- validate logs, metrics, traces, data behavior, and integration behavior
- keep rollback ready

Required artifact: `25-release-report.md`

Exit criteria:

- production release is complete and stable

### Phase 26 - Hypercare

Purpose: confirm success under real traffic and real use.

What must happen:

- monitor incidents, errors, latency, retries, support tickets, adoption, and KPIs
- validate SLO or operational impact where relevant
- patch or roll back quickly if needed

Required artifact: `26-hypercare-report.md`

Exit criteria:

- the release is operationally healthy

### Phase 27 - Retrospective And Postmortem

Purpose: convert delivery into organizational learning.

What must happen:

- run a retrospective for every release
- run a blameless postmortem for serious defects, failed releases, or incidents
- record what must change in standards, docs, architecture, tests, support, onboarding, or `claude.md`

Required artifacts:

- `27-retrospective.md`
- `27-postmortem.md` when applicable

Exit criteria:

- the organization got better, not just the feature shipped

## Cross-Phase Rules

These rules apply throughout the entire lifecycle:

1. Depth may scale by request size; phase existence may not.
2. Hotfixes may compress timing; they may not erase traceability.
3. Every major decision must have a clear owner.
4. Every assumption must have a risk interpretation.
5. Every open question must be tracked until resolved or explicitly accepted.
6. Every change with behavior impact must update docs.
7. Every change with operational impact must update runbooks and support context.
8. Every change with architecture impact must update architecture docs and possibly ADRs.
9. Every change with security impact must pass security review appropriate to the risk.
10. Every change with user-facing impact must pass real user-flow validation, not only isolated technical tests.

## Mandatory Pre-Implementation Gate

Before phase `14` starts, all of the following must be true:

- [ ] root `claude.md` reviewed
- [ ] related feature folder exists or is updated
- [ ] business, product, architecture, impact, standards, test, and coverage phases documented
- [ ] related code read and understood
- [ ] related tests read and understood
- [ ] rollout and rollback approach documented
- [ ] observability needs identified
- [ ] documentation scope identified
- [ ] major risks identified
- [ ] owners assigned

If any item is false, implementation must not start.

## Universal Engineering Rules

### Universal Code Rules

These rules are intentionally language-agnostic. Use the equivalent enforcement mechanism in the local stack.

1. Do not introduce unsafe typing or unchecked dynamic behavior when a safer contract is available.
2. In typed languages, avoid `any`-style escape hatches except in tightly justified boundaries.
3. Do not disable linters, static analyzers, or security checks without explicit justification and approval.
4. Do not compare domain values with ad hoc raw strings when shared enums, constants, schemas, or value objects exist.
5. Do not leak secrets, tokens, credentials, or protected data to logs, clients, analytics, traces, or error messages.
6. Do not scatter environment reads throughout business logic; use a validated configuration layer or equivalent.
7. Do not build god-files or god-classes; keep modules focused and legible.
8. Do not hide core behavior in giant utility files.
9. Do not leave critical behavior dependent on implicit defaults that reviewers cannot see.
10. Do not place business rules in thin transport or rendering layers.
11. Do not place persistence logic in UI, transport, or domain-policy layers unless the architecture explicitly requires it and documents it.
12. Do not let one domain mutate another domain's private data store without a documented ownership model.
13. Do not swallow errors silently.
14. Do not create fire-and-forget workflows with no visible success or failure outcome.
15. Do not leave long-running workflows without terminal states, timeout logic, and operator visibility.
16. Do not add behavior without tests.
17. Do not add user-facing text without localization support when the product supports localization.
18. Do not add hidden coupling to external libraries; wrap third-party behavior behind local adapters when it affects core workflows.
19. Do not leave return behavior ambiguous in public interfaces.
20. Do not leave reviewers guessing where the real logic lives.

### Architecture-Independent Layering Rules

Map these rules to your local architecture:

- Transport or delivery layers should extract input, call the next layer, and return the result. They should stay thin.
- Application or orchestration layers should coordinate use cases, permissions, transactions, and side effects.
- Domain layers should own business rules, invariants, calculations, and decisions.
- Persistence layers should own data reads and writes.
- Integration layers should own external service calls, SDK calls, broker interactions, and protocol handling.
- Presentation layers should render states and route interactions, not contain hidden business policy.

If the codebase does not use all these layers explicitly, the responsibilities still need to exist conceptually.

### Complexity And Extraction Rules

Use these as default thresholds unless the local codebase has stricter ones:

- transport methods should usually stay under 10 lines of real logic
- standard business methods should usually stay under 40 lines of real logic
- orchestration methods should usually stay under 80 lines of real logic
- complex methods above these limits require decomposition or explicit justification
- ordinary function complexity should target 10 or below
- orchestration function complexity should target 15 or below

When logic starts to sprawl:

- extract validation
- extract transformation
- extract policy decisions
- extract integration calls
- extract reusable types, constants, schemas, or helpers

Do not perform extraction mindlessly. Extract to improve clarity and ownership, not to manufacture tiny files with no meaning.

### Module Boundary Rules

- keep domain ownership explicit
- keep public interfaces small and intentional
- avoid backdoor imports into internals of another module or service
- version shared contracts carefully
- treat breaking changes as first-class events, not incidental side effects
- prefer adapters over deep imports from volatile third-party packages

### Configuration And Environment Rules

- configuration must be explicit, validated, and documented
- new config values must update templates, runtime settings, deployment definitions, and docs where relevant
- secrets must never be committed
- environment-specific behavior must be clear and testable
- config drift between local, test, staging, and production must be understood before release
- feature flags must have owners, purpose, rollout criteria, and retirement expectations

### Contract And Validation Rules

- validate input at trust boundaries
- bound strings, arrays, file sizes, and payload sizes with reasonable limits
- define machine-readable errors for system-to-system boundaries
- use stable contract definitions and examples
- identify backward compatibility expectations explicitly
- do not rely on clients to enforce server-side constraints
- define what is required, optional, deprecated, and forbidden

### Error Handling Rules

- every important failure path must be explicit
- retries must have limits, backoff, and observability
- timeouts must be defined for remote dependencies
- partial failure behavior must be deliberate
- user-visible workflows must surface meaningful error states
- operator-visible workflows must surface actionable diagnostics
- error messages must be safe to expose at the correct boundary

### Async, Event, Job, And Long-Running Workflow Rules

- background jobs must be idempotent where practical
- event-driven workflows must have traceability from trigger to effect
- queues and retries must have failure handling, dead-letter or equivalent strategy, and visibility
- long-running client workflows must not wait forever; they need terminal success, failure, timeout, and cancellation behavior
- if streaming or polling exists, define stop conditions and fallback behavior
- if asynchronous failure affects the user outcome, the user must eventually receive a terminal failure state, not endless loading

### UI And UX Rules

- every interactive element must do meaningful work or be visibly disabled with reason
- every user-facing workflow must define loading, empty, success, error, partial-failure, and permission-denied states where relevant
- accessibility is mandatory
- keyboard and focus behavior must be considered for interactive flows
- user-facing copy must be clear and operationally correct
- do not ship decorative feature stubs masquerading as working features
- if the system supports localization, user-facing text must be localized consistently

### Data, Migration, And State Rules

- schema changes require a forward plan and rollback plan
- destructive changes require special care, validation, and approval
- data migrations and backfills need observability, retry behavior, and completion validation
- persistence-changing tests should verify resulting state, not only request success
- do not assume cache state and persisted state are the same; verify both when relevant
- define retention, masking, and deletion expectations for sensitive data

### Observability Rules

- logs must be structured enough to diagnose issues
- metrics must exist for business-critical and operationally critical workflows
- traces or correlation identifiers must connect multi-step workflows where possible
- alerts must exist for material failure modes before release of critical changes
- logs must be checked after significant tests and after deployment
- dashboards must answer whether the change is healthy, degraded, or failing

### Documentation Rules

- documentation is part of the implementation
- update docs whenever reality changes
- examples, diagrams, commands, and workflows must stay current
- operator and support docs matter as much as developer docs for operationally significant changes
- release notes are required for user-visible or operator-visible behavior changes

## Mandatory Impacted-Area Checklist

For every request, explicitly review whether the change affects any of the following:

- business process
- user workflow
- client workflow
- frontend or presentation layer
- backend or application layer
- mobile or desktop client
- shared libraries or packages
- APIs or public contracts
- internal contracts
- schemas or data models
- migrations or backfills
- queues, events, jobs, or schedulers
- caching, search, indexing, or reporting
- analytics, tracking, or BI outputs
- authentication, authorization, or tenant isolation
- secrets, config, or environment variables
- deployment manifests or infrastructure-as-code
- ingress, proxy, API gateway, or routing rules
- CI/CD
- test fixtures or seed data
- health checks
- dashboards, alerts, or traceability
- support workflows
- runbooks
- user docs
- release notes
- legal or compliance obligations
- `claude.md`

If an area is affected, the related work must be documented, implemented, tested, and reflected in the relevant artifacts.

## Mandatory Change Checklist

For every change, explicitly review and update the following if affected:

1. configuration templates and example environment files
2. actual development, staging, or test configuration values needed to run the change
3. local bootstrap or install scripts
4. deployment manifests, container definitions, orchestration files, or infrastructure code
5. ingress, proxy, API gateway, service discovery, or route configuration
6. CI workflows and required checks
7. health checks and service catalog entries
8. shared contracts, SDKs, generated clients, or consumer-facing types
9. schema definitions, migrations, rollback scripts, and backfills
10. seed data, fixtures, factories, and test data helpers
11. permission matrices, role definitions, or policy maps
12. analytics event schemas, dashboards, and reports
13. localization files or content systems if user-facing text changes
14. architecture docs and ADRs
15. API docs and reference docs
16. runbooks and operational procedures
17. support enablement and known-issues guidance
18. release notes
19. onboarding docs
20. `claude.md`

A change is incomplete if an affected item was not reviewed.

## Quality Engineering Operating Model

### Core Mindset Rules

1. Never trust a passing happy path alone.
2. Never trust isolated unit tests as the whole story.
3. Never trust UI state without checking persisted or returned truth where relevant.
4. Never trust backend success without checking client, operator, or downstream impact.
5. Never trust a local test only when the change is integration-heavy.
6. Never trust technical correctness without business correctness.
7. Never trust business correctness without release and operational readiness.
8. A feature is not implemented when code compiles; it is implemented when it is reviewed, tested, documented, supportable, and releasable.
9. A bug is not fixed when the symptom disappears; it is fixed when the root cause is understood, covered, and regression-checked.

### Required Test Layers

For every request, assess which of these layers are needed and document why:

- unit tests
- module tests
- service or use-case tests
- repository or persistence tests
- API or contract tests
- integration tests
- UI component tests
- UX flow tests
- end-to-end tests
- regression tests
- security tests
- permission or RBAC tests
- analytics or event-tracking validation
- migration tests
- rollback tests
- performance checks
- exploratory manual testing
- UAT
- client acceptance testing

### Test Environment Rules

- define where each test layer runs
- use representative environments for integration-heavy work
- keep test data intentional and documented
- seed or fixture data must be understandable and reproducible
- lower environments must expose enough telemetry to debug failures
- production-like configuration differences must be known before release
- if production parity cannot be achieved, the gap and risk must be documented explicitly

### Required Validation Before Claiming Done

Before saying work is complete, all applicable checks must be green:

- formatting or style checks
- linting
- static analysis
- type checks or equivalent compile-time validation
- unit tests
- integration tests
- E2E tests where applicable
- build or packaging validation
- environment or deployment validation for affected runtime pieces
- manual exploratory validation
- security validation for relevant risk areas
- documentation updates

### Real QA Execution Rules

Independent validation must include real execution, not only reading code.

Where applicable, QA and developer validation must include:

- real API or contract execution
- real UI or client interaction
- real workflow progression through the affected path
- verification of persistence after writes or state transitions
- verification of emitted events, messages, jobs, or notifications
- log inspection for critical errors after test runs
- regression checks for adjacent workflows

### Required Evidence Types

For meaningful changes, keep evidence appropriate to the risk:

- command output summaries
- screenshots
- request and response samples
- database or state verification notes
- logs or traces
- dashboard checks
- issue and defect records

### Coverage Rules

- minimum touched-module coverage target: `95%` lines, branches, functions, and statements
- critical logic should be near-complete and scenario-rich
- do not use high global averages to excuse weak coverage in changed code
- a high percentage with shallow scenarios is still inadequate

### Testing Blockers

The following block delivery unless explicitly waived by authorized leadership:

- failing lint or static-analysis checks
- failing type checks or build validation
- failing automated tests
- missing tests for changed behavior
- missing validation for critical failure paths
- missing regression coverage for high-risk changes
- missing evidence for security-sensitive workflows
- missing documentation of known limitations

## Mandatory Post-Implementation Gate

After implementation and before declaring completion, confirm all applicable items:

- [ ] code changes are reviewable and scoped
- [ ] affected artifacts updated
- [ ] lint and static checks passed
- [ ] type checks or compile checks passed
- [ ] automated tests passed
- [ ] manual validation completed
- [ ] persistence or state verification completed for writes and transitions
- [ ] logs inspected for critical failures after validation
- [ ] coverage threshold met or waiver recorded
- [ ] docs updated
- [ ] release notes updated when behavior changed
- [ ] rollback path remains valid
- [ ] known gaps recorded explicitly

## Review And Merge Rules

### Code Review Rules

- every change must be reviewed by someone qualified to understand its impact
- changes touching shared contracts, security, auth, permissions, compliance, or money flow require deeper review and may require multiple reviewers
- reviewers must examine behavior, architecture fit, test quality, docs, and operational impact, not only style
- reviewers must use blocker language clearly: `MUST FIX`, `SHOULD FIX`, `FOLLOW-UP`

### Merge Rules

Do not merge when any of the following is true:

- scope differs materially from approved plan without documentation
- architecture impact is undocumented
- tests are missing or failing
- coverage gate is red without waiver
- docs are stale for changed behavior
- required approvals are missing
- rollback is undefined
- observability is undefined for material release risk

## Approval Workflow

- intake owner confirms classification and request ID
- business owner approves business framing
- product owner approves requirements
- technical owner approves technical direction
- architecture approver approves architecture changes when applicable
- QA lead approves QA sign-off
- security approver approves security review when applicable
- operations or SRE owner approves rollout and observability readiness when applicable
- business owner approves UAT
- client or external stakeholder approves when contractually required
- release owner records GO or NO-GO

If local roles differ, map local roles to these responsibilities explicitly.

## Defect Workflow

1. log the defect with request ID, severity, environment, reproducer, and owner
2. determine whether it is blocking, high-risk, accepted, or deferred
3. reproduce and identify root cause
4. implement the fix in a reviewable change
5. add or update tests for the exact failure mode
6. re-run relevant validation and regression
7. return to QA, business, or client validation as needed
8. update docs, release notes, support context, and postmortem actions if the issue escaped late

No defect is done without retest.

## Security Baseline Rules

- apply least privilege
- enforce authorization on trusted server-side or authoritative boundaries
- treat tenant isolation as testable behavior, not a belief
- classify data and protect sensitive data in transit, at rest, and in logs
- review abuse paths, misuse cases, and privilege escalation routes
- review dependency and supply-chain risk
- review CI/CD access and artifact integrity for important releases
- ensure auditability for important security or administrative actions

## Release, Rollout, And Rollback Rules

- prefer staged rollout, canary, feature flags, tenant-scoped enablement, or dark launch where risk justifies it
- define rollout owner, release window, communications, and success metrics
- define rollback triggers before release
- validate smoke tests immediately after deploy
- keep rollback feasible until stability is confirmed
- do not release when monitoring, alerting, or on-call ownership is unclear

## Hypercare And Postmortem Rules

- hypercare is a planned operating window with owners, duration, and success criteria
- incidents or serious defects must trigger explicit triage and communication
- serious incidents require blameless postmortems
- retrospectives are mandatory even when nothing catastrophic happened
- learnings that create permanent policy changes must update `claude.md`

## Hotfix Rules

Hotfixes are faster, not looser.

For hotfixes:

- all phases still exist
- analysis may be compressed, but not skipped
- approvals may be accelerated, but not erased
- documentation may be updated in near-real-time, but not abandoned
- rollback readiness is even more important than usual
- follow-up retrospective is mandatory

## Non-Negotiable Gates

- No implementation before phases `00` through `13` are complete.
- No pull request without tests.
- No pull request without documentation updates where behavior changes.
- No merge when touched-module coverage is below threshold unless a documented waiver is approved.
- No merge if lint, static analysis, type checks, builds, tests, or security checks fail.
- No merge if architecture impact is undocumented.
- No release without QA sign-off.
- No release without security validation when applicable.
- No release without a rollback plan.
- No release without observability, alerting, and smoke tests.
- No release without documentation updates.
- No release without GO / NO-GO approval.
- No release without required business, compliance, or client approval.

## Definition Of Done

Work is done only when all of the following are true:

- the problem is understood
- the scope is explicit
- the implementation matches approved intent
- architecture fit is documented
- tests are adequate to the risk
- quality gates are green
- security review is complete when needed
- QA sign-off exists
- UAT and client approval exist where required
- docs are updated
- release and rollback plans are ready
- support and operations are prepared
- hypercare ownership is known

If any of these are false, the work is not done.

## When This File Must Be Updated

Update `claude.md` whenever a new permanent rule or expectation appears in any of these areas:

- SDLC phases or gates
- request classification rules
- approval rules
- architecture rules
- module boundaries
- coding standards
- config and environment handling
- test strategy
- coverage thresholds
- QA workflow
- security baseline
- release process
- rollout or rollback policy
- observability policy
- incident handling
- documentation requirements
- support readiness
- hotfix policy

## Final Instruction

Treat this file as company policy, not advice. Do not skip detail because a request looks small. Do the work in order, write the artifacts, respect the gates, and optimize for software that is correct, secure, testable, observable, maintainable, documented, supportable, and reversible.
