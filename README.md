# Enterprise SDLC Documentation Template

This repository is a generic, reusable operating system for strict software delivery. It is meant to work across new products, legacy products, startups, enterprise teams, agencies, regulated environments, monoliths, modular monoliths, microservices, mobile apps, AI products, internal tools, and customer-facing platforms.

The goal is simple: every request must move through a complete, documented lifecycle so an engineer, product team, QA team, security team, or AI coding agent cannot silently skip the work that makes software production-ready.

## What This Repo Gives You

- A permanent `claude.md` operating brain for AI-assisted delivery
- A strict SDLC policy with non-skippable gates
- Reusable baseline documents for engineering, QA, security, release, documentation, UAT, and risk
- A full feature template covering phases `00` through `27`
- Reusable test-case templates for unit, integration, E2E, security, and business validation
- Generic runbook, ADR, release-note, and support templates

## Core Policy

Every request must pass through full business, product, architecture, impact, standards, testing, implementation, QA, security, UAT, risk, documentation, release, hypercare, and retrospective phases with written artifacts and hard gates; no step may be skipped, and no change may ship unless it is reviewed, tested, secure, observable, documented, and operationally reversible.

## Recommended Usage

1. Keep `claude.md` at the repo root. On case-sensitive filesystems, mirror it to `CLAUDE.md` if your tooling expects the uppercase filename.
2. Treat `docs/sdlc/` as the permanent company baseline.
3. Copy `docs/features/_template/` to `docs/features/<feature-slug>/` for each request.
4. Create or update test-case files under `test-cases/` as the request advances.
5. Refuse implementation until phases `00` through `13` are documented.
6. Refuse merge or release until all hard gates are green.

## Repository Layout

```text
/claude.md

/docs/sdlc/
  company-sdlc-policy.md
  engineering-standards.md
  code-review-checklist.md
  release-checklist.md
  security-baseline.md
  qa-baseline.md
  uat-baseline.md
  risk-baseline.md
  documentation-baseline.md
  public-reference-points.md

/docs/features/_template/
  00-intake.md
  01-business-analysis.md
  02-business-development.md
  03-product-requirements.md
  04-cross-functional-refinement.md
  05-delivery-plan.md
  06-technical-refinement.md
  07-technical-roadmap.md
  08-architecture-review.md
  09-impact-analysis.md
  10-engineering-standards-check.md
  11-test-strategy.md
  12-coverage-plan.md
  13-implementation-readiness.md
  15-dev-validation-report.md
  16-dev-bug-log.md
  17-qa-report.md
  18-defect-cycle-log.md
  19-threat-model.md
  19-security-review.md
  19-pentest-report.md
  20-uat-report.md
  21-client-approval.md
  22-go-no-go.md
  23-documentation-changelog.md
  24-risk-compliance-ops.md
  25-release-report.md
  26-hypercare-report.md
  27-retrospective.md
  27-postmortem.md

/test-cases/
  unit/
  integration/
  e2e/
  security/
  business/

/runbooks/
/architecture/adrs/
/release-notes/
/support/
```

## Design Notes

- The process is strict by design.
- Depth can scale with request size; phase existence cannot.
- Coverage is measured on touched modules, not just global repository averages.
- Hotfixes move faster, but they still produce artifacts and still pass gates.
- This repo is intentionally generic so it can be adapted to any company or architecture.
- On Windows and other case-insensitive filesystems, `claude.md` is the canonical file. On case-sensitive filesystems, teams may optionally mirror it to `CLAUDE.md` for tool compatibility.

## Start Here

- Read `claude.md`
- Read `docs/sdlc/company-sdlc-policy.md`
- Read `docs/sdlc/public-reference-points.md`
- Copy `docs/features/_template/` for the first request you want to run through the system
