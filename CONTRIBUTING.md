> Fiscal convention: monetary values in the Drenyra ecosystem are BigInt cents; no float is ever used for money; version numbers are JSON integers, never floats.

# Contributing to ARKELYTHEX

Welcome. ARKELYTHEX builds the Drenyra Accounting Ecosystem: a verifiable accounting platform where fiscal correctness, tenant isolation, and auditability are product safety requirements. This document is the organization-wide baseline for contributing to any ARKELYTHEX repository.

## Before you start

- Read the repository's own contributing guide if it has one; repository-level rules refine, never contradict, this baseline.
- Read `SECURITY.md` and `CODE_OF_CONDUCT.md` in the repository (the organization copies apply when the repository does not override them).
- Fiscal changes move money or tax positions. The human accountant is the final authority; AI prepares and reviews, it never decides alone. See `docs/ai-contribution-policy.md`.

## Commit discipline

- Use [Conventional Commits](https://www.conventionalcommits.org/) for every commit: `feat:`, `fix:`, `chore:`, `docs:`, `ci:`, `refactor:`, `test:`, `perf:`.
- One logical change per commit; keep commits small and atomic.
- Never add `Co-Authored-By`, AI attribution, or tool attribution lines to commits, PR bodies, or release notes. The human who pushes the change owns it.
- Include the change scope in the commit subject when it helps: `fix(close): …`, `feat(receipts): …`.

## Pull requests

- **Small, reviewable PRs.** Prefer many small PRs over one large one. A PR should be reviewable in one focused sitting.
- **Chained PRs for large work.** When the total change exceeds roughly 400 changed lines, split it into a chain of stacked, reviewable PRs instead of one monolithic PR. Each PR in the chain must be independently reviewable and mergeable in order; each one states its position in the chain.
- Every PR must use the organization's PR template (review empathy: scope, review path, workload forecast) so the reviewer knows what to expect before opening the diff.
- Automated review (GGA) and human review run on every PR to `main`. A passing automated review is not approval; the human review remains authoritative.
- Resolve review comments explicitly; do not silently dismiss them.

## Docs-as-code

- Documentation lives in the repository, reviewed and versioned like code.
- Update docs in the same PR as the behavior they describe; do not defer documentation to a follow-up PR.
- Release notes, migration notes, and contract compatibility reports are release artifacts — see `docs/release-checklist.md`.

## Tests

- Business logic requires tests. This is non-negotiable for accounting, fiscal, receipts, and ledger code.
- Money is integer math (BigInt cents). Tests must assert exact integer amounts — never float equality.
- Tests must pass before the PR is opened, and the PR must state the commands used.

## Fiscal and scope discipline

- **Scope-first:** company/RUC/period isolation is structural in queries, memory, and search. Fiscal changes must state the RUC and period (when applicable) they affect and prove isolation in tests.
- Fiscal/SUNAT changes require compliance tests with canonical vectors.
- Receipts/ledger changes require conformance vectors against the frozen contract.
- Do not introduce new non-accounting verticals into product repositories; new verticals land as clearly identified repositories.

## Review empathy

Before you open a PR, walk through it as your reviewer will:

- **Scope:** what the PR touches — and explicitly what it deliberately does NOT touch.
- **Review path:** the shortest path to review the change; what to read first and why.
- **Workload forecast:** estimated review effort (files, lines, risk areas), so the reviewer can plan.

## Getting help

See `SUPPORT.md` for where to ask questions. Issues first, always; never private chat for bug reports. Security issues are handled privately — see `SECURITY.md`.
