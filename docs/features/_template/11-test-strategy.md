# 11 - Test Strategy

## Purpose

Design quality before implementation starts.

## Step-by-Step Workflow

1. Map requirements to test layers.
2. Define happy paths, unhappy paths, edge cases, race conditions, and rollback validation.
3. Identify which test cases must exist in `test-cases/`.
4. Define environments, data, evidence, and ownership.

## Requirement-to-Test Matrix

| Requirement or risk | Unit | Integration | E2E | Security | Business / UAT |
| --- | --- | --- | --- | --- | --- |
| | | | | | |

## Test Layers

### Unit

[Describe the logic units, validation rules, calculations, guards, or helpers that need direct tests.]

### Integration / API

[Describe service-to-service, database, queue, contract, or API flow tests.]

### UI / UX

[Describe component, state, accessibility, and workflow tests.]

### End-to-End

[Describe real user flows from entry point to outcome.]

### Security

[Describe auth, authz, tenant isolation, abuse, validation, and sensitive-data test needs.]

### Regression

[Describe adjacent flows that must be re-tested.]

### Migration / Rollback

[Describe migration verification, backfill validation, rollback triggers, and rollback checks.]

## Environment and Data Needs

- Test environments needed:
- Seed data needed:
- External dependency stubs or sandboxes needed:
- Monitoring evidence needed:

## Linked Test Case Files

- `test-cases/unit/`
- `test-cases/integration/`
- `test-cases/e2e/`
- `test-cases/security/`
- `test-cases/business/`

## Exit Checklist

- [ ] Requirements mapped to tests
- [ ] Negative and edge cases included
- [ ] Security and permissions covered
- [ ] Migration and rollback covered when applicable
- [ ] Test-case locations identified

## Sign-Off

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| QA lead | | approve / revise | |
| Technical owner | | approve / revise | |

