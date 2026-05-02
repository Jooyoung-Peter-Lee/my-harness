# SECURITY.md — Security Policies & Standards

## Principles

1. **Least privilege** — every component gets only the access it needs
2. **Defense in depth** — don't rely on a single control
3. **Fail secure** — on error, deny access rather than grant it
4. **Never trust user input** — validate and sanitize at every boundary

---

## Authentication & Authorization

> **프로젝트 시작 시 아래 테이블을 채우세요.** 확정 전까지 플레이스홀더로 유지합니다.

| Concern | Approach | Notes |
|---|---|---|
| Auth provider | (e.g., Clerk, Auth.js) | |
| Session management | (e.g., JWTs, server sessions) | |
| Password policy | (delegated to provider) | |
| MFA | (e.g., optional / required for admin) | |
| Role model | (e.g., RBAC: admin, member, viewer) | |

### Rules
- Never implement custom auth — use a vetted provider
- Authorization checks happen server-side, never rely on client
- Admin routes require explicit role check, not just authentication
- Session tokens never stored in `localStorage` — use `httpOnly` cookies

---

## Input Validation

- All user input validated with a schema library (e.g., Zod) at the API boundary
- Never interpolate user input into SQL, shell commands, or HTML
- File uploads: validate type, size, and content before storage
- Rate limiting on all public-facing endpoints

---

## Secrets Management

- No secrets in source code — ever
- Use environment variables; pull via platform CLI (e.g., `vercel env pull`, `doppler run`, `.env` file)
- Rotate secrets on: personnel offboarding, suspected exposure
- Secrets follow naming convention: `<SERVICE>_<TYPE>` (e.g., `STRIPE_SECRET_KEY`)
- Audit secret access quarterly

---

## OWASP Top 10 Mitigations

| Threat | Mitigation |
|---|---|
| Injection | Parameterized queries, Zod validation |
| Broken auth | Vetted auth provider, short-lived tokens |
| XSS | Framework escaping, CSP headers |
| IDOR | Server-side ownership checks on every resource |
| Security misconfiguration | IaC review, no default credentials |
| Sensitive data exposure | Encrypt at rest and in transit, no PII in logs |
| CSRF | SameSite cookies, CSRF tokens on state-changing forms |

---

## Dependency Security

- Run `npm audit` (or equivalent) in CI
- Dependabot / Renovate enabled for automated dependency updates
- No packages with known critical CVEs in production
- Review new dependencies before adding: check maintenance status and download count

---

## Incident Response (Security)

1. **Contain** — revoke compromised credentials, disable affected feature
2. **Assess** — determine scope and data exposure
3. **Notify** — inform affected users per legal obligations (GDPR etc.)
4. **Fix** — patch root cause
5. **Review** — add regression test and update this doc
