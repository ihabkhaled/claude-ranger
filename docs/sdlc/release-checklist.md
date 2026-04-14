# Release Checklist

## Purpose

This checklist is the minimum release gate for any deployment to production or any environment that matters to customers, operators, or regulated workflows.

## Pre-Release

- [ ] Scope delivered matches approved scope
- [ ] Outstanding defects are documented and accepted
- [ ] QA sign-off recorded
- [ ] Security review completed
- [ ] UAT or business sign-off completed when applicable
- [ ] Client approval captured when required
- [ ] Rollout plan documented
- [ ] Rollback plan documented and technically feasible
- [ ] Smoke tests prepared
- [ ] Monitoring, dashboards, alerts, and on-call ownership confirmed
- [ ] Runbooks updated
- [ ] Support briefed
- [ ] Release notes prepared
- [ ] Compliance and risk review completed when applicable
- [ ] Go / no-go decision recorded

## Deployment Execution

- [ ] Release window confirmed
- [ ] Change owner present
- [ ] Approvers reachable
- [ ] Feature flags or staged rollout controls ready
- [ ] Backup or snapshot steps completed if needed
- [ ] Migrations executed in approved order
- [ ] Smoke tests passed
- [ ] Critical metrics healthy
- [ ] External integrations healthy

## Immediate Post-Release

- [ ] Error rate normal
- [ ] Latency normal
- [ ] Queues, jobs, or workers healthy
- [ ] Database behavior validated
- [ ] User-facing flows validated
- [ ] No critical alerts triggered without response

## Hypercare Handoff

- [ ] Hypercare window has owner and duration
- [ ] Incident escalation path shared
- [ ] Support and customer-facing teams have known-issues guidance
- [ ] Rollback criteria remain visible until stabilization

