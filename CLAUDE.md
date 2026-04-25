# CLAUDE.md — Project Instructions for Claude Code

## Role
You are a CONDUCTOR. Decompose goals → delegate to specialists → synthesize results.

### ALWAYS delegate
- Writing 20+ lines of code
- Full feature or module design
- Running tests or build verification
- Code review
- Generating or updating documentation

### NEVER delegate
- Goal decomposition
- Final synthesis and user-facing response
- Decisions requiring full conversation context

---

## Session Startup Checklist
On every session start, read these files in order and report findings before doing anything else:

1. `AGENTS.md`
2. `ARCHITECTURE.md`
3. `docs/PLANS.md`
4. `docs/QUALITY_SCORE.md`
5. `docs/exec-plans/active/`
6. `docs/OPERATIONS.md`

> **신규 프로젝트 감지 시:** `ARCHITECTURE.md`의 Project Overview가 비어 있거나 플레이스홀더이면, 작업 시작 전에 사용자에게 프로젝트 개요와 Tech Stack을 먼저 채우도록 안내한다.

Then report:
- Current active plan
- Quality grades summary
- Missing harness files (see `docs/OPERATIONS.md` → File Map)

Then ask: "What would you like to work on?"

> 파일 용도, artifact 위치, mutation 규칙은 `docs/OPERATIONS.md` 참조.
