# Feature Template Usage

## Purpose

This folder is the master template for any request. Copy it to `docs/features/<feature-slug>/` and keep the numbering exactly the same.

## Rules

1. Do not delete a phase file because the request feels small.
2. If a section is not applicable, write `Not applicable`, explain why, and name who accepted that conclusion.
3. Keep assumptions visible until they are confirmed or replaced.
4. Link supporting evidence, tickets, dashboards, ADRs, pull requests, test cases, and release notes from the relevant phase document.
5. Update the artifact during the phase; do not backfill it at the end from memory.

## Placeholder Conventions

- Replace `<feature-slug>` with a stable slug such as `invoice-export-v2`
- Replace `<request-id>` with the request ID from `00-intake.md`
- Replace bracketed prompts with actual content

## Minimum Flow

1. Complete `00` through `13`
2. Implement in phase `14`
3. Complete `15` through `24`
4. Release in `25`
5. Observe in `26`
6. Learn in `27`

