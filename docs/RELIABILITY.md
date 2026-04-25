# RELIABILITY.md — Reliability Standards & Incident Response

## Service Level Objectives (SLOs)

| Service | Availability Target | Latency (p99) | Error Rate |
|---|---|---|---|
| API (read) | 99.9% | < 500ms | < 0.1% |
| API (write) | 99.5% | < 1000ms | < 0.5% |
| Background jobs | 99% | N/A | < 1% |

---

## Error Handling Standards

- **Never swallow errors silently** — log and surface them
- Use structured logging: `{ level, message, context, timestamp }`
- All unhandled promise rejections must be caught at the boundary
- HTTP errors must return a consistent shape:
  ```json
  { "error": { "code": "ERROR_CODE", "message": "Human readable", "details": {} } }
  ```
- Use typed error classes, not raw `Error` with string parsing

---

## Observability

| Signal | Tool | What to monitor |
|---|---|---|
| Logs | (e.g., Vercel Logs, Datadog) | Errors, warnings, slow queries |
| Metrics | (e.g., Vercel Analytics) | Request rate, error rate, latency |
| Traces | (fill in) | Slow transactions, DB queries |
| Alerts | (fill in) | SLO breaches, error spikes |

---

## Deployment Safety

- All deployments go to preview first
- Database migrations run separately from deploys
- Feature flags used for high-risk rollouts
- Rollback plan documented before any significant deploy
- No deploy on Fridays or before holidays without on-call coverage

---

## Incident Response

### Severity Levels

| Level | Definition | Response Time | Example |
|---|---|---|---|
| P1 | Complete outage or data loss | 15 min | DB down, auth broken |
| P2 | Major feature broken | 1 hour | Payments failing |
| P3 | Degraded experience | 4 hours | Slow load times |
| P4 | Minor issue | Next sprint | UI glitch |

### Response Steps

1. **Detect** — alert fires or user reports issue
2. **Triage** — assign severity, notify stakeholders
3. **Mitigate** — restore service (rollback if needed)
4. **Resolve** — fix root cause
5. **Postmortem** — write up in `docs/exec-plans/completed/` within 48h

---

## Data Integrity

- All writes are transactional where atomicity matters
- Soft deletes preferred over hard deletes for user data
- Backups: (fill in frequency and retention)
- No migration without a rollback script
