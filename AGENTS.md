# ARKELYTHEX GitHub Organization — Review Rules

> **Última actualización**: 2026-06-29
> Aplicado por Gentleman Guardian Angel (gga) en cada PR a `main`.
> Repositorio de perfil de organización — README, community health files, templates, workflows.

## ⛔ NON-NEGOTIABLES (MUST NOT)

These rules are absolute. Any violation causes the review to FAIL.

- **MUST NOT** include secrets, real credentials, tokens, or sensitive organization data in public files.
- **MUST NOT** expose internal URLs, private IPs, or unreleased product names without explicit approval.
- **MUST NOT** break the organization profile README display (HTML/XML structure in markdown).
- **MUST NOT** introduce broken links in community health files (CONTRIBUTING, SUPPORT, SECURITY).
- **MUST NOT** reference repositories, teams, or resources that do not exist or are not public.
- **MUST NOT** add `Co-Authored-By` or AI attribution to commits.
- **MUST NOT** use `any` type in any workflow or action TypeScript files.

## ✅ REQUIRED PRACTICES (MUST)

- **MUST** validate all YAML/JSON workflow syntax before committing (use `act --lint` or similar).
- **MUST** keep the profile README rendering correctly on GitHub (no broken relative links).
- **MUST** use conventional commits for all changes: `feat:`, `fix:`, `chore:`, `docs:`, `ci:`, `refactor:`.
- **MUST** prefer small, atomic commits — one logical change per commit.
- **MUST** update the profile README when adding or deprecating organization repositories.
- **MUST** use possessive form consistently for organization name in all public facing text.
- **MUST** include architecture badges or status badges that reflect current reality, not aspirational state.

## 🏗️ Organization Repo Rules

- Organization profile (`profile/README.md`) is the **public face** of ARKELYTHEX — treat it as communication design.
- Community health files (`CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md`, `CODE_OF_CONDUCT.md`) must be accurate and actionable.
- GitHub workflow files (`.github/workflows/*.yml`) must be tested or validated.
- Issue and PR templates (`.github/ISSUE_TEMPLATE/`, `.github/PULL_REQUEST_TEMPLATE/`) help external contributors — keep them clear.
- Funding and sponsorship configs (`FUNDING.yml`) must point to valid accounts.

## 🔒 Security Rules

- **MUST NOT** have hardcoded secrets or credentials in any file.
- **MUST NOT** merge workflows that execute arbitrary code from PRs without approval gates.
- **MUST NOT** add personal email addresses to public templates.
- **MUST NOT** use `pull_request_target` without understanding the security implications.
- **MUST NOT** reference internal infrastructure in public files.
- **MUST** use `${{ secrets.XXX }}` for all sensitive values in workflows.
- **MUST** pin third-party GitHub Actions to a full commit SHA, not a mutable tag.

## 🧪 Testing Rules

- **MUST** validate workflow YAML syntax before committing (`bun run validate-workflows` or `actionlint`).
- **MUST** test issue/PR templates by opening a draft PR first when modifying them.
- **MUST** verify all links in community health files point to real resources.

## 📐 Style & Conventions

- **MUST** use conventional commits: `feat:`, `fix:`, `chore:`, `docs:`, `test:`, `ci:`, `refactor:`.
- **MUST** keep commits atomic — one logical change per commit.
- **MUST NOT** add `Co-Authored-By` or AI attribution to commits.
- **MUST** format YAML consistently (2-space indentation, no tabs).
- **MUST** use descriptive workflow step names in `*.yml` files.
- **Prefer** small focused files over large monolithic ones.
- **MUST** use American English for all public-facing documentation.

## 🚫 REJECT (Fail Review)

The review MUST FAIL if any of these are detected:

1. Hardcoded secrets or credentials (API keys, tokens, passwords).
2. Broken links in README or community health files.
3. Workflow files with invalid YAML syntax.
4. `Co-Authored-By` or AI attribution in commit messages.
5. References to non-existent repositories, teams, or resources.
6. Personal email addresses in public templates.
7. Outdated or inaccurate repository lists in profile README.
8. Use of mutable tags for third-party GitHub Actions.

## Review Format

When reviewing, produce this output format:

```
## Review Summary

### ✅ Passed Rules
- {rule}: {brief evidence}

### ❌ Failed Rules
- {rule}: {violation description} — {file:line}

### ⚠️ Warnings
- {rule}: {concern} — {file:line}

### Verdict
PASS | FAIL | PASS WITH WARNINGS
```

Be objective. Quote the specific code that violates rules. For PASS WITH WARNINGS, the warnings must be non-blocking concerns.
