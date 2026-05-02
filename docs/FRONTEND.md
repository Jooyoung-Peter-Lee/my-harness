# FRONTEND.md — Frontend Conventions & Patterns

## Framework & Runtime

> **프로젝트 시작 시 아래 테이블을 채우세요.**

| Concern | Choice | Notes |
|---|---|---|
| Framework | (e.g., Next.js 15 App Router) | |
| Language | TypeScript (strict mode) | |
| Package manager | (e.g., pnpm / bun) | |
| Bundler | (e.g., Turbopack / Vite) | |

---

## File & Folder Conventions

```
src/
├── app/               # Routes (App Router) or pages/
├── components/
│   ├── ui/            # Primitive/design-system components
│   └── <feature>/     # Feature-specific components
├── hooks/             # Custom React hooks
├── lib/               # Utility functions, helpers
├── styles/            # Global CSS, tokens
└── types/             # Shared TypeScript types
```

- One component per file
- File name matches export name (PascalCase for components, camelCase for utils)
- Co-locate tests with source: `Button.tsx` + `Button.test.tsx`

---

## Component Rules

> **Next.js App Router 기준입니다. 다른 프레임워크 사용 시 해당 항목을 조정하세요.**

- Prefer Server Components by default; use `"use client"` only when needed
- Props interfaces named `<ComponentName>Props`
- No inline styles — use Tailwind classes or CSS Modules
- Avoid `any`; use `unknown` and narrow types explicitly

---

## State Management

> **프로젝트 시작 시 아래 테이블을 채우세요.**

| Scope | Approach |
|---|---|
| Server state | (e.g., React Query / SWR / Server Actions) |
| Global client state | (e.g., Zustand / Jotai / Context — use sparingly) |
| Form state | (e.g., React Hook Form + Zod) |
| URL state | (e.g., `nuqs` / `useSearchParams`) |

---

## Data Fetching

> **Next.js App Router 기준입니다. 다른 프레임워크 사용 시 해당 항목을 조정하세요.**

- Fetch on the server where possible (RSC)
- Use typed API clients — never `fetch` raw JSON without parsing
- All API responses validated with Zod at the boundary
- Errors surfaced via error boundaries or toast notifications

---

## Performance Targets

| Metric | Target |
|---|---|
| LCP | < 2.5s |
| CLS | < 0.1 |
| INP | < 200ms |
| Bundle size (initial JS) | < 200kb gzipped |

---

## Testing Approach

- Unit: components and hooks with Vitest + Testing Library
- Integration: key user flows
- E2E: critical paths (auth, checkout, etc.) with Playwright
- No snapshot tests unless the team explicitly agrees
