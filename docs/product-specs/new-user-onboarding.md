# Product Spec: New User Onboarding

**Status:** Draft
**Author:** (fill in)
**Date:** YYYY-MM-DD

---

## Problem

> What pain does this solve? What happens today without this feature?

New users land in the product with no guidance, leading to high drop-off before they reach the first meaningful action.

---

## Goal

> What does success look like? How will we know it worked?

A new user completes their first meaningful action within 5 minutes of signing up.

**Success metric:** Activation rate (% users who complete first action within 24h) ≥ (fill in target)

---

## User Personas

- **Primary:** (fill in — e.g., solo developer signing up for the first time)
- **Secondary:** (fill in — e.g., team member invited by an admin)

---

## User Stories

- As a new user, I want to understand what the product does immediately after signing up.
- As a new user, I want to complete my profile so other users can identify me.
- As a new user, I want to be guided to my first meaningful action.

---

## Scope

### In scope
- Welcome screen after sign-up
- Profile setup step (name, avatar)
- First-action prompt (product-specific)
- Onboarding progress indicator

### Out of scope
- Email drip campaign (separate spec)
- In-app tooltip tours (Phase 2)

---

## Flow

```
Sign Up
  └── Email verification
        └── Welcome screen ("Here's what you can do")
              └── Profile setup (name, avatar) [skippable]
                    └── First action prompt
                          └── → Main product
```

---

## Design Notes

- Use the existing onboarding layout component from design system
- Progress indicator: step dots (not percentages)
- Every step must be skippable — never block the user

---

## Open Questions

- [ ] Do we require email verification before onboarding, or after?
- [ ] What is the "first meaningful action" for this product?

---

## Acceptance Criteria

- [ ] User can complete onboarding in < 2 minutes
- [ ] All steps are skippable
- [ ] Onboarding state persists on refresh
- [ ] Returning users do not see onboarding again
