> Fiscal convention: monetary values in the Drenyra ecosystem are BigInt cents; no float is ever used for money; version numbers are JSON integers, never floats.

# Security Policy for ARKELYTHEX

## Reporting a vulnerability

- **Report privately, per repository.** Use GitHub Private Vulnerability Reporting (Security tab → *Report a vulnerability*) on the affected repository. Do not open public issues or pull requests for vulnerabilities.
- **Never include customer data in a report:** no customer names, RUCs, periods, monetary amounts, or credentials. Describe the vulnerability abstractly and offer a sanitized reproduction on request.
- **Fiscal sensitivity:** flaws in fiscal paths — money math, RUC/period isolation, SUNAT flows, receipts, or ledger — are high sensitivity. State the affected component precisely and flag the report as fiscal when applicable.

## What to include

- Affected repository and component.
- Severity (per the repository's bug report template).
- Sanitized steps to reproduce.
- Expected vs. actual behavior.
- Environment versions (OS, runtime, package version — JSON integers, never floats).

## Handling SLA

- **Acknowledgment:** within 5 business days of the report.
- **Initial assessment:** within 10 business days of acknowledgment.
- **Coordinated disclosure:** we will not publish details before a fix is available; please allow time to fix and release.

## Scope

This policy applies to all public ARKELYTHEX repositories: Drenyra, drenyra-ai, drenyra-pi, drenyra-engram, and the organization's auxiliary repositories. Repository-level `SECURITY.md` files refine this baseline; they never weaken it.
