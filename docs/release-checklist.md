> Fiscal convention: monetary values in the Drenyra ecosystem are BigInt cents; no float is ever used for money; version numbers are JSON integers, never floats.

# Release Checklist — ARKELYTHEX

Applies to all ARKELYTHEX repositories that release artifacts (currently Drenyra, drenyra-ai, drenyra-pi, drenyra-engram).

## Version policy

- Pre-release phases are `0.0.x` / pre-alpha with suffixed versions (`0.1.0-alpha.1`, …).
- **Freeze at 0.1.0:** the first public contract freeze. After `0.1.0`, contracts are versioned and compatibility becomes a release gate.
- Version numbers are JSON integers where they appear in machine-readable artifacts — never floats. `0.1.0` is not `0.1`.
- Breaking changes follow semver and require a migration note and a contract compatibility report.

## Gates before release

- [ ] Typecheck passes.
- [ ] Test suite passes (focused + full).
- [ ] Conformance: business logic tests; fiscal/SUNAT compliance vectors; receipts/ledger conformance vectors.
- [ ] Changelog updated.
- [ ] Migration note written (when applicable).
- [ ] Contract compatibility report written (when applicable).

## Package build and pack verification

- [ ] Package builds cleanly.
- [ ] `npm pack` (or the ecosystem equivalent) produces the expected archive.
- [ ] **Packed-install test:** install the packed artifact in a clean consumer and smoke-test the public surface.
- [ ] Packed artifact contains no stray files (tests, secrets, local configuration).

## Provenance

- [ ] Signed git tag (`git tag -s`).
- [ ] npm provenance enabled (or equivalent supply-chain attestation).
- [ ] SHA-256 manifest of the release artifacts.
- [ ] SBOM generated and attached.
- [ ] Changelog entry.
- [ ] Migration note.
- [ ] Contract compatibility report.

## Release notes

- [ ] Written and reviewed by a human; no `Co-Authored-By` or AI attribution.
- [ ] State version, what changed, and migration impact.

## Post-release

- [ ] Tag pushed and verified.
- [ ] Manifests and SBOM published with the release.
- [ ] Dependent repositories updated: Drenyra consumes released, versioned drenyra-ai; drenyra-pi pins a package-local, checksum-verified drenyra-ai (never `PATH`).
