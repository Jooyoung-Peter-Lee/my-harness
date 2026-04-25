# OPERATIONS.md — File Map, Artifact Placement & Mutation Rules

## File Map

### Core harness files (always read at startup)

| File | 용도 |
|---|---|
| `CLAUDE.md` | 하네스 운영 규칙, Conductor 역할 정의 |
| `AGENTS.md` | 에이전트 목록, 위임 규칙, 소유 디렉토리 |
| `ARCHITECTURE.md` | 기술 스택, 도메인 맵, ADR 로그 |
| `docs/PLANS.md` | 활성 스프린트, 백로그, 로드맵 |
| `docs/QUALITY_SCORE.md` | 도메인별 품질 등급 |
| `docs/exec-plans/active/` | 진행 중인 실행 플랜 |

### Supplementary docs (task에 따라 읽는 파일)

| File | 용도 | 언제 읽는가 |
|---|---|---|
| `docs/DESIGN.md` | 디자인 시스템, 색상, 타이포그래피, 접근성 기준 | UI 작업, 컴포넌트 설계, 스타일 결정 시 |
| `docs/FRONTEND.md` | 프레임워크 컨벤션, 컴포넌트 규칙, 성능 목표 | 프론트엔드 코드 작성 또는 리뷰 시 |
| `docs/PRODUCT_SENSE.md` | 제품 원칙, 유저 페르소나, 의사결정 프레임워크 | 기능 범위 결정, 우선순위 논의 시 |
| `docs/RELIABILITY.md` | SLO, 에러 처리 표준, 인시던트 대응 절차 | 백엔드 변경, 인프라 작업, 장애 대응 시 |
| `docs/SECURITY.md` | 인증/인가, 입력 검증, OWASP 완화 기준 | 인증 변경, 새 엔드포인트 추가, 데이터 처리 시 |

### Generated & tracked files

| File | 용도 | 언제 읽는가 |
|---|---|---|
| `docs/generated/db-schema.md` | 현재 DB 스키마 레퍼런스 | 쿼리 작성, 마이그레이션, 데이터 모델 설계 시 |
| `docs/exec-plans/tech-debt-tracker.md` | 미해결 기술 부채 목록 | 품질 리뷰, 스프린트 계획 시 |

### Working document directories

| Directory | 용도 |
|---|---|
| `docs/design-docs/` | 기능별 설계 문서 및 핵심 신념 (`index.md`로 탐색) |
| `docs/exec-plans/completed/` | 완료된 플랜 및 인시던트 포스트모템 |
| `docs/product-specs/` | 제품 요구사항 명세 (`index.md`로 탐색) |
| `docs/references/` | LLM 친화적 라이브러리 레퍼런스 (`<lib>-llms.txt`) |

---

## What Goes Where

| Artifact | Location |
|---|---|
| Big feature design | `docs/design-docs/<feature>.md` + update `index.md` |
| Core engineering / product beliefs | `docs/design-docs/core-beliefs.md` |
| Sprint or task list | `docs/exec-plans/active/<plan>.md` + update `docs/PLANS.md` |
| Product requirement | `docs/product-specs/<feature>.md` + update `index.md` |
| Architectural decision | row in `ARCHITECTURE.md` + linked design-doc |
| Library reference | `docs/references/<lib>-llms.txt` |
| Generated DB schema | `docs/generated/db-schema.md` |
| Quality problem / tech debt | `docs/exec-plans/tech-debt-tracker.md` |
| Incident postmortem | `docs/exec-plans/completed/<date>-postmortem.md` |

---

## Mutation Rules

| What changed | Also update |
|---|---|
| `AGENTS.md` (roles) | `ARCHITECTURE.md` |
| `ARCHITECTURE.md` | Affected design-docs |
| Plan completed | Move `exec-plans/active/` → `exec-plans/completed/` + update `docs/PLANS.md` |
| Quality drift found | `docs/QUALITY_SCORE.md` + `exec-plans/tech-debt-tracker.md` |
| Arch decision made | Row in `ARCHITECTURE.md` + linked design-doc |
| DB migration applied | `docs/generated/db-schema.md` |
| New UI pattern adopted | `docs/DESIGN.md` and/or `docs/FRONTEND.md` |
| Security policy changed | `docs/SECURITY.md` |
| SLO or incident process changed | `docs/RELIABILITY.md` |
| Product principle changed | `docs/PRODUCT_SENSE.md` + `docs/design-docs/core-beliefs.md` |
| New file added to harness | `docs/OPERATIONS.md` File Map 업데이트 |
| New library reference added | `docs/references/` + `docs/OPERATIONS.md` File Map (해당 시) |
| New design-doc or product-spec added | 해당 디렉토리의 `index.md` 업데이트 |
