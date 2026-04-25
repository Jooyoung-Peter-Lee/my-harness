# AGENTS.md — Agent Roster & Delegation Rules

## Conductor (Claude Code — default)
The Conductor is responsible for goal decomposition, delegation, and synthesis.
It does NOT write large blocks of code, run tests, or generate documentation directly.

**Delegate when:**
- Writing 20+ lines of code
- Designing a full feature or module
- Running tests or build verification
- Generating or updating documentation
- Deep debugging sessions

**Never delegate:**
- Goal decomposition
- Final synthesis and user-facing response
- Decisions requiring full conversation context

---

## Agent Roster

### frontend-agent
**Role:** UI implementation, component design, styling, client-side logic.
**Stack:** See `ARCHITECTURE.md` → Tech Stack
**Owns:** `src/components/`, `src/pages/`, `src/styles/`
**Delegate when:** building or modifying UI components, pages, or client routing.

---

### backend-agent
**Role:** API design, business logic, server-side processing.
**Stack:** See `ARCHITECTURE.md` → Tech Stack
**Owns:** `src/api/`, `src/services/`, `src/middleware/`
**Delegate when:** building endpoints, service logic, or integrations.

---

### data-agent
**Role:** Database schema, migrations, queries, data modeling.
**Stack:** See `ARCHITECTURE.md` → Tech Stack
**Owns:** `src/db/`, `migrations/`, `prisma/` or `drizzle/`
**Delegate when:** schema changes, query optimization, or seed data.

---

### infra-agent
**Role:** CI/CD pipelines, deployment config, environment management, IaC.
**Stack:** See `ARCHITECTURE.md` → Tech Stack
**Owns:** `.github/`, `infra/`, `vercel.json` or `vercel.ts`, `Dockerfile`
**Delegate when:** deploy config, environment variables, or pipeline changes.

---

### qa-agent
**Role:** Test strategy, writing tests, coverage analysis, regression checks.
**Stack:** See `ARCHITECTURE.md` → Tech Stack
**Owns:** `tests/`, `e2e/`, `__tests__/`
**Delegate when:** writing unit, integration, or end-to-end tests.

---

### docs-agent
**Role:** Technical documentation, design docs, ADRs, changelogs.
**Stack:** N/A
**Owns:** `docs/`
**Delegate when:** writing or updating any documentation artifact.

---

## Golden Principles (non-negotiable)

1. **Shared utilities first** — never hand-roll what belongs in `shared/`
2. **No YOLO probing** — validate data boundaries; never guess shapes
3. **Repository is the brain** — if it's not committed, it doesn't exist
4. **One responsibility per file** — split when a file exceeds its purpose
5. **Fail loud** — prefer explicit errors over silent fallbacks
6. **Leave a trail** — every significant decision gets a design-doc entry

---

## Mutation Rules

| What changed | Also update |
|---|---|
| AGENTS.md (roles) | ARCHITECTURE.md |
| ARCHITECTURE.md | Affected design-docs |
| Plan completed | Move `exec-plans/active/` → `completed/` |
| Quality drift found | `docs/QUALITY_SCORE.md` |
| Arch decision made | Row in ARCHITECTURE.md + linked design-doc |
