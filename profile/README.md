# ARKELYTHEX

> **Mission-grade intelligence systems for the organizations operating Latin America.**
>
> **Sistemas de inteligencia de misión crítica para las organizaciones que operan Latinoamérica.**

---

## Products

| Product | Description | Status |
|---|---|---|
| **Drenyra** | Financial & Fiscal Operating System — transactions, ledgers, tax compliance, treasury, evidence | **Active** |
| **Elvyra** | Legal & Evidence Operating System — contracts, cases, evidence, legal decisions | In Development |
| **Forge** | Industrial Operations & Infrastructure Command — construction, mining, energy | Planned |

## Architecture

Arkelythex is built on a 5-layer architecture designed for mission-grade operations:

| Layer | Purpose |
|---|---|
| **Fabric** | Identity, permissions, events, workflows, audit, offline sync |
| **Ontology** | Living model of organizations, assets, processes, and relationships |
| **Intelligence** | Agents, reasoning, document extraction, classification, planning |
| **Command** | Operations center, alerts, approvals, human supervision, automation |
| **Edge** | Mobile, cameras, sensors, drones, offline inference (future) |

## Principles

- **Mission-grade** — Idempotent operations, total traceability, graceful degradation
- **Evidence-native** — Every action produces verifiable evidence automatically
- **Offline-ready** — Works in hostile environments with limited connectivity
- **Human command** — AI assists; humans authorize; systems execute
- **Cost supremacy** — Efficient enough to scale across Latin America

## Repositories

| Category | Repos | Description |
|---|---|---|
| **Core** | [Arkelythex](https://github.com/arkelythex/Arkelythex), [Drenyra](https://github.com/arkelythex/Drenyra) | Landing page, design system, Financial & Fiscal OS |
| **Products** | Drenyra (active), Elvyra (in dev), Forge (planned) | Mission-grade operating systems |
| **Tools** | Gentleman Guardian Angel, opencode-desktop-bin, zeroclaw | Developer tooling |

## Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 16, React 19, TanStack Router, Tailwind CSS 4 |
| Backend | Bun + ElysiaJS, PostgreSQL 16, Drizzle ORM |
| Events | NATS JetStream |
| AI/Agents | OpenRouter, Gemini, specialized models |
| Design System | @arkelythex/ui, Tailwind CSS 4 |
| Runtime | Bun 1.x, Docker |

## Current Priorities — Q3 2026

1. **Drenyra Maturity** — Production hardening, SUNAT compliance automation, evidence engine
2. **Elvyra MVP** — Legal operations, contract management, evidence graph
3. **Documentation** — Strategic docs, developer guides, SDD ecosystem
4. **Platform** — CI/CD hardening, tenant isolation, observability

## Connect

- **Location:** Lima · Cusco · Montevideo
- **Doctrine:** [Arkelythex Doctrine](https://github.com/arkelythex/Arkelythex/blob/main/docs/DOCTRINE.md) — strategic vision

---

*Advanced intelligence, mission-critical engineering, industrial execution, efficient scale.*
