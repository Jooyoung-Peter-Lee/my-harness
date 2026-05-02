> **이 파일은 스프린트 시작 시 가장 먼저 업데이트해야 합니다.**
> Active Plans → Backlog → Roadmap 순으로 채우세요.

# PLANS.md — Active Goals & Roadmap

## Current Focus

> 작성 가이드: 지금 팀이 집중하는 목표를 한 문장으로 기술하세요. 예) "MVP 인증 플로우 구현"

---

## Active Plans

> 작성 가이드: Status는 "In Progress / Blocked / Review / Done" 중 하나. Owner는 AGENTS.md의 에이전트 이름을 사용하세요. Priority는 P0/P1/P2. Blocker는 Blocked 상태일 때만 기입.
> Backlog 항목을 Active로 올리는 기준: 현재 스프린트에서 착수 가능한 상태(의존성 해소, 담당자 확정)일 때.

| Priority | Plan | File | Status | Owner | Blocker |
|---|---|---|---|---|---|
| (P0/P1/P2) | `<plan-name>` | [plan-name.md](exec-plans/active/plan-name.md) | In Progress | (agent) | |

---

## Backlog

> 작성 가이드: P0=blocking, P1=중요하지만 비blocking, P2=nice-to-have. Owner는 AGENTS.md의 에이전트 이름 (미정이면 TBD).

| Priority | Task | Owner | Notes |
|---|---|---|---|
| P0 | `<your-task>` | TBD | |
| P1 | `<your-task>` | TBD | |
| P2 | `<your-task>` | TBD | |

---

## Completed

> 작성 가이드: 플랜 완료 시 exec-plan 파일을 `docs/exec-plans/active/` → `docs/exec-plans/completed/`로 이동한 뒤 이 테이블에 행을 추가하세요. Notes 칸에는 관련 PR 링크 또는 exec-plan 파일 경로를 기입하세요.

| Plan | Completed | Notes |
|---|---|---|
| `<plan-name>` | YYYY-MM-DD | |

---

## Roadmap (High Level)

> 작성 가이드: Phase 수는 프로젝트 규모에 맞게 추가/삭제하세요. Target은 절대 날짜(YYYY-MM-DD)로 기입하세요.

| Phase | Goal | Target |
|---|---|---|
| Phase N | (e.g., MVP — core flows working) | YYYY-MM-DD |
| Phase N+1 | (e.g., Polish + launch) | YYYY-MM-DD |
| Phase N+2 | (e.g., Growth features) | YYYY-MM-DD |
