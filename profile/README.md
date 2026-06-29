# ARKELYTHEX

> **Inteligencia Fiscal-Operativa para LATAM**

ARKELYTHEX convierte la infraestructura de compliance fiscal (SUNAT, SIRE, IGV, retenciones, detracciones) en un sistema operativo unificado — accionable, auditado, y aumentado por inteligencia artificial con supervisión humana.

---

## Drenyra — Codex + Digits

**Drenyra** es el producto flagship de ARKELYTHEX. Su ADN se compone de dos layers:

- **Codex** — Motor de reglas fiscales deterministas. Traduce SUNAT, RUC, IGV, SIRE, CDR, detracciones, PLE en lógica testable, replayable y 100% cubierta por tests. TypeScript strict, Bun + Elysia, PostgreSQL.
- **Digits** — Experiencia de usuario. Web SPA (React 19) para el día a día + CLI (Go + Bubbletea) para operaciones avanzadas. Cash-flow, close, conciliación y compliance en una interfaz.

Codex + Digits forman Drenyra: un producto completo que va desde la regulación fiscal peruana hasta la experiencia del contador, con la ambición de escalar a todo LATAM.

---

## Products

| Product | Tagline | Status | Stack |
|---------|---------|--------|-------|
| **Andino** — AndinoDroneLab | Agentic AI platform for drone engineering evolution | Active (Phase 1 ~90%) | Python, NSGA-II, CadQuery, PX4 |
| **Estado** — CivicTech Peru | Civic tech open-source para Peru — transparencia y participación | Active (MVP) | Rust (Axum), Next.js, PostgreSQL |
| **Kuse** — Kuse Cowork | Open-source desktop cowork agent (alternative to Claude Cowork) | Active (v0.0.2) | Rust + Tauri, SolidJS, Docker |
| **Senzar** — EdgeTraz Agro | Trazabilidad agro-industrial con IA + Rust en el edge | Active (Pilot) | Rust (ESP32/RPi), TensorFlow Lite, Next.js |
| **Solevra** — Legal Drafting Orchestrator | LDD pipeline + adversarial validation + Mnevori reasoning | Active (v0.1.0) | Bun + ElysiaJS, PostgreSQL |

---

## Architecture

### Stack

| Layer | Technology |
|-------|------------|
| Frontend (web) | React 19 + Vite 7 + TanStack Router |
| Backend API | Bun 1.3 + Elysia 1.4 + OpenAPI |
| Data Engine | Python 3.11 + FastAPI + Polars |
| Database | PostgreSQL 16 + Drizzle ORM |
| Messaging | NATS JetStream 2.10 |
| AI/Agents | OpenRouter + Gemini + Mastra |
| CLI | Go + Cobra + Bubbletea |
| Design System | Tailwind CSS 4 + shadcn/ui + Glass & Steel (DTCG tokens) |

### Architecture Invariants

1. **AI is advisory, not fiscal authority** — AI prepares/reviews; humans approve material actions
2. **Fiscal truth is deterministic and replayable** — All fiscal paths are 100% test-covered
3. **Evidence-first** — Every claim anchors to source artifacts with content hashes
4. **Integer math for money** — Never floating point for financial values
5. **SDD for critical changes** — Full SDD cycle for compliance, schema, and monetary logic changes

---

## Repositories

| Category | Repos | Description |
|----------|-------|-------------|
| **Core** | Arkelythex (monorepo), Drenyra, Solevra | Flagship platform and products |
| **Web** | DreamFolio, Somnyx-web, dreamcoder-web | Public-facing applications |
| **Tools** | Somnyx-tui, codex-desktop-linux, Gentleman Guardian Angel, zeroclaw, opencode-desktop-bin | CLI, TUI, developer tooling |
| **Config** | Dreamcoder_dots, CleanSweep | Dotfiles and system configuration |

---

## Current Priorities — Q3 2026

1. **Platform Stabilization** — CI/CD hardening, test infra, deployment automation, observability
2. **Drenyra Agent System** — Instruction parsing, sandboxed execution, evidence graph, approval gates
3. **Product Launches** — Estado MVP, Senzar PoC, Kuse v0.3.0, Andino Phase 1 validation
4. **Documentation Overhaul** — SDD ecosystem docs propagated to all repos

---

## Connect

- **Location:** Lima · Cusco · Montevideo
- **Ecosystem SDD:** See our [SDD Maestro](https://github.com/arkelythex/Arkelythex/blob/main/sdd/ecosystem-readme-sdd/00-README.md) — the single source of truth for all documentation

---

*Documentation is maintained in the [SDD Maestro](https://github.com/arkelythex/Arkelythex/blob/main/sdd/ecosystem-readme-sdd/00-README.md) — edit there first, then propagate.*
