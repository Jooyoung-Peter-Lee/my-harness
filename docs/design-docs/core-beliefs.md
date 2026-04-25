# Core Beliefs

> These are the foundational engineering and product convictions for this project.
> Every significant architectural or product decision should be traceable back to one of these.
> Reviewed and updated at major milestones.

---

## Engineering Beliefs

### 1. Simple beats clever
Readable, obvious code outlasts clever code. When in doubt, choose the approach a new team member can understand on day one.

### 2. Boundaries are the hardest part
The most important design decisions are about what crosses a boundary — between services, between layers, between teams. Get these right before optimizing internals.

### 3. Boring technology is a feature
Prefer proven, widely-understood tools over novel ones unless there is a concrete, measurable reason to do otherwise. The ecosystem, documentation, and hiring pool matter.

### 4. Observability is not optional
You cannot improve what you cannot measure. Logging, metrics, and tracing are first-class concerns, not afterthoughts.

### 5. Tests are documentation that executes
A test suite describes what the system is supposed to do. Write tests that would catch the bugs you're most afraid of, not tests that inflate coverage numbers.

---

## Product Beliefs

### 6. Speed is a feature
Latency is a UX concern. A slow product is a broken product.

### 7. Default to less
Ship the smallest version that validates the assumption. Complexity is a cost you pay forever.

### 8. Reversibility over optimality
A reversible decision made today beats an irreversible decision made perfectly. Prefer architectures that can be changed.

### 9. Users lie, but their behavior doesn't
Qualitative feedback is valuable; quantitative behavior is more valuable. Ship, measure, iterate.

---

## How to Use This Document

When making a significant decision, write down which belief it supports (or violates, and why that's acceptable this time). Over time this creates a log of when the team chose pragmatism over principle — which is healthy, as long as it's intentional.
