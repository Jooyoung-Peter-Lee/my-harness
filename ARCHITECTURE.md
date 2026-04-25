# ARCHITECTURE.md — System Structure & Domain Map

> **이 파일은 프로젝트 시작 시 가장 먼저 채워야 합니다.**
> Project Overview와 Tech Stack을 먼저 작성한 후 개발을 시작하세요.
> Claude Code는 이 파일을 읽고 프로젝트 맥락을 파악합니다.

---

## Project Overview

> 작성 가이드: 이 시스템이 무엇을 하는지, 누가 사용하는지 한 문단으로 기술하세요.
> 예) "<your-product>는 <your-target-user>를 위한 <your-core-function> 서비스입니다."

<your-project-overview>

---

## Tech Stack

> 작성 가이드: 프레임워크와 버전, 선택 이유를 한 줄씩 기재하세요.
> Technology 칸에 실제 사용 기술을, Notes 칸에 버전 또는 선택 이유를 적습니다.

| Layer | Technology | Notes |
|---|---|---|
| Frontend | <your-frontend-framework> | |
| Backend | <your-backend-framework> | |
| Database | <your-database> | |
| Auth | <your-auth-solution> | |
| Hosting | <your-hosting-platform> | |
| CI/CD | <your-ci-cd-tool> | |
| Testing | <your-testing-tools> | |

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

> 작성 가이드: 프로젝트의 실제 디렉토리 구조에 맞게 Key Files 경로를 수정하세요.
> Status는 "active" 또는 "planned" 중 하나로 기입합니다.

| Domain | Owner Agent | Key Files | Status |
|---|---|---|---|
| UI / Frontend | frontend-agent | `<your-frontend-dir>/` | (active / planned) |
| API / Backend | backend-agent | `<your-api-dir>/`, `<your-services-dir>/` | (active / planned) |
| Data / DB | data-agent | `<your-db-dir>/`, `<your-migrations-dir>/` | (active / planned) |
| Infra / Deploy | infra-agent | `<your-infra-dir>/`, `.github/` | (active / planned) |
| Tests / QA | qa-agent | `<your-tests-dir>/`, `<your-e2e-dir>/` | (active / planned) |

---

## Architectural Decisions Log

> 작성 가이드: 중요한 기술적 결정이 생길 때마다 행을 추가하세요.
> Design Doc 칸에는 `docs/design-docs/<feature>.md` 링크를 기입합니다.

| Date | Decision | Rationale | Design Doc |
|---|---|---|---|
| YYYY-MM-DD | <your-decision> | <your-rationale> | [link] |

---

## Integration Points

> 작성 가이드: 외부 서비스, 써드파티 API, SaaS 의존성을 모두 기재하세요.
> Config location에는 해당 서비스를 초기화하는 파일 경로를 적습니다.

| Service | Purpose | Owner | Config location |
|---|---|---|---|
| <your-service> | <your-purpose> | <owner-agent> | `<your-config-path>` |
