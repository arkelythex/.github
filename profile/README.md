# ARKELYTHEX

> **Mission-grade intelligence systems for the organizations operating Latin America.**
>
> **Sistemas de inteligencia de misión crítica para las organizaciones que operan Latinoamérica.**

ARKELYTHEX builds the **Drenyra Accounting Ecosystem**: a verifiable financial operating system where fiscal correctness, tenant isolation, and auditability are product safety requirements. Web, CLI, agents, and memory share one discipline — receipts prove execution, contracts freeze behavior, and a human accountant remains the final authority.

---

## DRENYRA ACCOUNTING ECOSYSTEM

The core is four repositories with strict, explicit boundaries:

| Repo | Role | Type | Status |
| --- | --- | --- | --- |
| [Drenyra](https://github.com/arkelythex/Drenyra) | Accounting Command Center — product UI, tenants, documents, close, reconciliation, approvals, SUNAT | Product / Command Center | Active |
| [drenyra-ai](https://github.com/arkelythex/drenyra-ai) | Verifiable Accounting Agent Ecosystem — protocol, runtime, receipts, ledger, missions, candidates, review | Runtime and protocol | Pre-alpha |
| [drenyra-pi](https://github.com/arkelythex/drenyra-pi) | Pi-native Accounting Operations Harness — operator experience, pinned verified runtime | Pi-native harness | Pre-alpha |
| [drenyra-engram](https://github.com/arkelythex/drenyra-engram) | Institutional Accounting Memory — scope-first memory, lifecycle, provenance | Institutional memory | Pre-alpha |

```text
                    ┌───────────────────┐
                    │ Drenyra-Engram    │  Institutional Accounting Memory
                    └─────────▲─────────┘  (independent; memory never authorizes)
                              │
                ┌─────────────┴─────────────┐
                │                           │
       ┌────────┴────────┐        ┌─────────┴─────────┐
       │ Drenyra-AI      │        │ Drenyra-Pi       │  Pi-native harness
       │ Agent Ecosystem │◄───────│ (installs + pins │
       └────────▲────────┘        │  drenyra-ai)     │
                │                 └───────────────────┘
       ┌────────┴────────┐
       │ Drenyra         │  Accounting Command Center
       └─────────────────┘
```

### Dependency direction

- `Drenyra` consumes released, versioned `drenyra-ai`; uses `drenyra-engram` for context.
- `drenyra-pi` consumes a **pinned, package-local, checksum-verified** `drenyra-ai` (never `PATH`); uses `drenyra-engram`.
- `drenyra-ai` never depends on Drenyra or Drenyra Pi, and never knows Drenyra Pi exists.
- `drenyra-engram` is independent — it informs, it never authorizes.

### Authority model

```text
Drenyra database          → transactional truth
Drenyra Engram            → institutional memory (guides, never authorizes)
Drenyra AI receipts+ledger → execution proof (Ed25519-signed, append-only)
Drenyra Pi                → operator experience
Human accountant          → final authority
```

### Principles

- **Mission-grade** — idempotent operations, total traceability, graceful degradation.
- **Evidence-native** — every action produces verifiable evidence automatically (RDA receipts, audit ledger).
- **Human command** — AI assists and prepares; humans authorize (R2 single, R3 dual approval); systems execute.
- **Deterministic fiscal truth** — fiscal paths are test-covered; money is integer math (BigInt cents), never floats.
- **Scope-first** — company/RUC/period isolation is structural in queries, memory, and search.
- **Contracts as public surface** — versioned, transport-agnostic, with canonical vectors and migration paths.

---

## OTHER ARKELYTHEX SYSTEMS

| Repo | Role | Status |
| --- | --- | --- |
| [.github](https://github.com/arkelythex/.github) | Organization profile and community health | Active |
| Elvyra | Legal Command Center — private | In development |
| [admin](https://github.com/arkelythex/admin) | Internal tools and administrative infrastructure | Maintenance / review |
| [elect-validate](https://github.com/arkelythex/elect-validate) | Electoral act validation suite for Peru's ONPE (Go, CLI, web) | Maintenance / review |

Future verticals (industrial operations, public sector, edge) are planned but have no public repositories yet — they will land as clearly-identified repos, never mixed into `Drenyra`.

---

## Current priorities — Q3 2026

1. **Drenyra AI industrialization** — finish gates + recovery, freeze first contracts (`0.1.0`), release with provenance (SHA-256 manifest, SBOM, signed tag).
2. **Drenyra Pi harness** — packed verification, private Drenyra AI installer, `/drenyra:status` + `/drenyra:doctor` end-to-end.
3. **Drenyra Engram engine** — freeze strategy (neutral contracts, in-memory reference, PostgreSQL authority), build + packaging.
4. **Drenyra scope discipline** — no new non-accounting verticals enter the product repo; progressive retirement of foreign folders.

---

*The four Drenyra repositories are the current public core. Everything else on this page is auxiliary or in transition.*
