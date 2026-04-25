# ARCHITECTURE.md — System Structure & Domain Map

## Project Overview

> **Fill in:** One paragraph describing what this system does and who uses it.

---

## Tech Stack

| Layer | Technology | Notes |
|---|---|---|
| Frontend | (e.g., Next.js, React) | |
| Backend | (e.g., Node.js, FastAPI) | |
| Database | (e.g., Postgres via Neon) | |
| Auth | (e.g., Clerk, Auth.js) | |
| Hosting | (e.g., Vercel) | |
| CI/CD | (e.g., GitHub Actions) | |
| Testing | (e.g., Vitest, Playwright) | |

---

## Repository Layout

```
/
├── src/
│   ├── components/       # UI components (frontend-agent)
│   ├── pages/ or app/    # Routes / pages (frontend-agent)
│   ├── api/              # API routes (backend-agent)
│   ├── services/         # Business logic (backend-agent)
│   ├── db/               # DB client, queries (data-agent)
│   └── shared/           # Shared utilities — never duplicate these
├── migrations/           # DB migrations (data-agent)
├── tests/                # Unit & integration tests (qa-agent)
├── e2e/                  # End-to-end tests (qa-agent)
├── infra/                # IaC / deployment config (infra-agent)
├── docs/                 # All documentation (docs-agent)
│   ├── design-docs/
│   ├── exec-plans/
│   │   ├── active/
│   │   └── completed/
│   ├── product-specs/
│   └── references/
├── AGENTS.md
├── ARCHITECTURE.md
└── CLAUDE.md             # Claude Code project instructions (if used)
```

---

## Domain Map

| Domain | Owner Agent | Key Files | Status |
|---|---|---|---|
| UI / Frontend | frontend-agent | `src/components/`, `src/app/` | (active / planned) |
| API / Backend | backend-agent | `src/api/`, `src/services/` | (active / planned) |
| Data / DB | data-agent | `src/db/`, `migrations/` | (active / planned) |
| Infra / Deploy | infra-agent | `infra/`, `.github/` | (active / planned) |
| Tests / QA | qa-agent | `tests/`, `e2e/` | (active / planned) |

---

## Architectural Decisions Log

| Date | Decision | Rationale | Design Doc |
|---|---|---|---|
| YYYY-MM-DD | (e.g., chose Postgres over SQLite) | (e.g., need concurrent writes) | [link] |

---

## Integration Points

> List external services, APIs, or third-party dependencies and what owns them.

| Service | Purpose | Owner | Config location |
|---|---|---|---|
| (e.g., Stripe) | Payments | backend-agent | `src/services/stripe.ts` |
| (e.g., Resend) | Email | backend-agent | `src/services/email.ts` |
