# PRODUCT_SENSE.md — Product Principles & Decision Framework

## Mission

> **Fill in:** Why does this product exist? What problem does it solve?

---

## Target Users

| Persona | Description | Primary Need |
|---|---|---|
| (e.g., Power User) | (fill in) | (fill in) |
| (e.g., New User) | (fill in) | (fill in) |
| (e.g., Admin) | (fill in) | (fill in) |

---

## Core Beliefs

> These are the non-negotiable product convictions that guide feature decisions.
> See [design-docs/core-beliefs.md](design-docs/core-beliefs.md) for the full rationale.

1. (e.g., Speed is a feature — every interaction should feel instant)
2. (e.g., Default to showing less, not more)
3. (e.g., Never lose user data silently)

---

## Decision Framework

When a product decision is unclear, ask in this order:

1. **Does it serve the primary persona's core need?** If no, deprioritize.
2. **Does it add complexity for < 20% of users?** If yes, make it optional or skip.
3. **Can we ship a simpler version first?** Prefer the smaller, reversible option.
4. **What's the cost of being wrong?** Prefer reversible decisions over irreversible ones.

---

## Feature Tiers

| Tier | Description | Approval needed |
|---|---|---|
| Core | Must work perfectly every time | Full review |
| Supporting | Important but not on the critical path | Standard review |
| Experimental | Testing an assumption; may be removed | Lightweight |

---

## Anti-patterns to Avoid

- Feature creep without validating user need
- Dark patterns (forced sign-ups, hidden costs, deceptive UI)
- Shipping half-finished flows — if it's not ready, gate it
- Building for edge cases before the primary flow is solid

---

## Success Metrics

| Metric | Definition | Target |
|---|---|---|
| (e.g., Activation rate) | (fill in) | (fill in) |
| (e.g., Retention D7) | (fill in) | (fill in) |
| (e.g., Task completion rate) | (fill in) | (fill in) |
