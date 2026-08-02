> Fiscal convention: monetary values in the Drenyra ecosystem are BigInt cents; no float is ever used for money; version numbers are JSON integers, never floats.

# Dependency Policy — ARKELYTHEX

## Dependabot cadence

- **npm dev dependencies:** weekly Dependabot update PRs.
- **Runtime dependencies:** reviewed individually; no blanket cadence.
- **Other ecosystems:** monthly, unless a security advisory forces earlier action.

## Review-before-merge

- Every Dependabot PR is reviewed before merge — never auto-merged.
- Dependabot PRs follow the same review path as any PR (automated + human review).
- Version bumps that change behavior or break the build are handled as normal PRs with tests.

## Lockfile discipline

- Lockfiles are committed and kept in sync with their manifest.
- Lockfile and manifest changes land together in the same commit.
- Never hand-edit a lockfile; regenerate through the package manager.
- Never add a dependency to a lockfile without a manifest entry.

## New runtime dependencies

- No new runtime dependency without justification: state the need, the alternatives considered, and the size/security tradeoff in the PR description.
- Prefer dev-only over runtime dependencies whenever possible.
- Runtime dependencies use locked/pinned versions, never floating ranges.

## License compatibility

- Every new dependency must carry a license compatible with the repository's license and the Drenyra ecosystem distribution model.
- Check the dependency's license and its transitive licenses; note copyleft in the PR.
- When in doubt, ask the maintainers before merging.
