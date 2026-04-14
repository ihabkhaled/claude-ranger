# QA Baseline

## Purpose

This document defines the minimum QA operating model for independent validation.

## QA Expectations

- QA works from documented requirements, acceptance criteria, architecture notes, and test strategy.
- QA is independent from implementation validation.
- QA validates both specified behavior and risky real-world behavior.
- QA evidence must be traceable to the request ID.

## Minimum QA Coverage

- happy paths
- unhappy paths
- edge cases
- boundary cases
- regression scope
- permissions or role cases
- data validation
- workflow continuity across systems
- user-visible content and error states

## QA Inputs

- product requirements
- acceptance criteria
- delivery plan
- architecture review
- test strategy
- test data
- environment notes
- known risks and open limitations

## QA Outputs

- defects with reproducible steps
- severity and priority
- evidence
- environment
- pass or fail status by scenario
- final QA sign-off or rejection

## QA Exit Rule

QA sign-off requires all blockers resolved or explicitly accepted by authorized approvers with documented risk.

