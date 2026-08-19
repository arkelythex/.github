# ARKELYTHEX

> **Mission-grade intelligence systems for the organizations operating in Latin America.**
>
> **Sistemas de inteligencia de misión crítica para las organizaciones que operan en Latinoamérica.**

ARKELYTHEX builds the **Drenyra Accounting Ecosystem**: a verifiable financial operating system where fiscal correctness, tenant isolation, and auditability are product safety requirements. Web, CLI, agents, and memory share one discipline — receipts prove execution, contracts freeze behavior, and a human accountant remains the final authority.

---

## DRENYRA ACCOUNTING ECOSYSTEM

The core is **six repositories** with strict, explicit boundaries:

| Repo | Role | Type | Status |
| --- | --- | --- | --- |
| [drenyra-command-center](https://github.com/arkelythex/drenyra-command-center) | Accounting Command Center — product UI, tenants, documents, close, reconciliation, approvals, SUNAT | Product / Command Center | In development |
| [drenyra-ai](https://github.com/arkelythex/drenyra-ai) | Verifiable Accounting Agent Ecosystem — protocol, runtime, receipts, ledger, missions, candidates, review | Runtime and protocol | Alpha (v0.5.0) |
| [drenyra-pi](https://github.com/arkelythex/drenyra-pi) | Pi-native Accounting Operations Harness — operator experience, pinned verified runtime | Pi-native harness | Pre-alpha |
| [drenyra-engram](https://github.com/arkelythex/drenyra-engram) | Institutional Accounting Memory — scope-first memory, lifecycle, provenance | Institutional memory | Alpha (v0.2.1) |
| [drenyra-skills](https://github.com/arkelythex/drenyra-skills) | Versioned accounting, tax, and operational knowledge — content layer (content ≠ runtime) | Knowledge | In development |
| [drenyra-guardian-angel](https://github.com/arkelythex/drenyra-guardian-angel) | Independent adversarial verification — refutation, dual review, evidence checks | Verification | In development |

```text
                            ┌───────────────────────┐
                            │ Drenyra-Engram        │  Institutional memory — Alpha
                            └───────────▲───────────┘  (informs, never authorizes)
                                        │
                       ┌────────────────┴────────────────┐
                       │                                 │
              ┌────────┴────────┐              ┌──────────┴─────────┐
              │ Drenyra-AI      │              │ Drenyra-Pi         │  Pi-native — Pre-alpha
              │ Verifiable core │◄─────────────│ (pins drenyra-ai)  │  harness
              │ Alpha           │              │                    │
              └───────▲─────────┘              └────────────────────┘
                      │
              ┌───────┴─────────┐
              │ Drenyra Command │  Command Center — web + API + TUI — In development
              │ Center          │  (consumes drenyra-ai contracts)
              └─────────────────┘

      Drenyra-Skills          → versioned accounting/tax knowledge (content layer) — In development
      Drenyra-Guardian-Angel  → independent adversarial verification (consumes contracts) — In development
```

### Dependency direction

- `drenyra-command-center` consumes released, versioned `drenyra-ai`; uses `drenyra-engram` for context.
- `drenyra-pi` consumes a **pinned, package-local, checksum-verified** `drenyra-ai` (never `PATH`); uses `drenyra-engram`.
- `drenyra-ai` never depends on the Command Center or Pi, and never knows Drenyra Pi exists.
- `drenyra-engram` is independent — it informs, it never authorizes.
- `drenyra-skills` is content (versioned knowledge), not code — the `drenyra-ai` runtime validates and agents consume it.
- `drenyra-guardian-angel` verifies against the frozen `drenyra-ai` contracts — never the author of what it reviews.

### Authority model

```text
Drenyra accounting database → transactional truth (PostgreSQL, tenant-isolated)
Drenyra Engram             → institutional memory (guides, never authorizes)
Drenyra AI receipts+ledger  → execution proof (Ed25519-signed, append-only)
Drenyra Guardian Angel     → independent adversarial verification (never the author)
Drenyra Pi                 → operator experience
Human accountant           → final authority
```

### Principles

- **Mission-grade** — idempotent operations, total traceability, graceful degradation.
- **Evidence-native** — every action produces verifiable evidence automatically (RDA receipts, audit ledger).
- **Human command** — AI assists and prepares; humans authorize (approval tiers: single and dual); systems execute.
- **Deterministic fiscal truth** — fiscal paths are test-covered; money is integer math (BigInt cents), never floats.
- **Scope-first** — company/RUC/period isolation is structural in queries, memory, and search.
- **Contracts as public surface** — versioned, transport-agnostic, with canonical vectors and migration paths.

---

## OTHER ARKELYTHEX SYSTEMS

| Repo | Role | Status |
| --- | --- | --- |
| [.github](https://github.com/arkelythex/.github) | Organization profile and community health | Active |
| [admin](https://github.com/arkelythex/admin) | Internal tools and administrative infrastructure | Maintenance / review |
| [elect-validate](https://github.com/arkelythex/elect-validate) | Electoral act validation suite for Peru's ONPE (Go, CLI, web) | Maintenance / review |

Future verticals (industrial operations, public sector, edge) are planned but have no public repositories yet — they will land as clearly-identified repos, never mixed into `drenyra-command-center`.

---

## Current priorities — Q3 2026

1. **Drenyra AI ecosystem maturity** — Phases 2c (hybrid orchestration) + 3 are current; expose `agents/` as a package subpath, keep releasing with provenance (SHA-256 manifest, SBOM, signed tag) and drive toward **v1.0**.
2. **Drenyra Engram engine** — deliver Evidence Objects (v0.7.0), Evidence Lifecycle (v0.8.0), and Review Workspace (v0.9.0); freeze strategy on neutral contracts + PostgreSQL authority.
3. **Drenyra Pi harness** — land runtime pin 0.3.0 (fiscal harness extraction complete), `/drenyra:status` + `/drenyra:doctor` end-to-end.
4. **Drenyra scope discipline** — no new non-accounting verticals enter the product repo; progressive retirement of foreign folders.

---

*The six Drenyra repositories are public and define the current production architecture. Other production repositories may remain private while public contracts, specifications, threat models, and reference slices are released progressively. Everything else on this page is auxiliary or in transition.*
