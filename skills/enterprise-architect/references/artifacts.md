# Artifact Structures — produce in the right shape

Identify the deliverable, produce exactly this structure. Keep every artifact concise and claim-led.

---

## Architecture Decision Record (ADR)

The unit of record for *why* a decision was made. Short, durable, one decision each.

```
# ADR-NNN: [Short decision title, stated as the decision]

## Status
Proposed | Accepted | Superseded by ADR-XXX | Deprecated

## Context
The forces at play: the driver, the constraints, the requirement, the
quality attributes in tension. 3–6 sentences. State assumptions.

## Decision
"We will [decision]." One sentence of decision, then the reasoning.

## Options Considered
- Option A — what it optimises / what it trades / why rejected (or chosen)
- Option B — ...
- Option C — ...

## Consequences
Positive: what this enables.
Negative: what this costs or constrains (be honest — every decision has these).
Follow-ons: what now needs to happen / what this commits us to.
```

**Rule:** an ADR with no negative consequences is incomplete. The value is in recording the trade-off so future architects understand *why*, not just *what*.

---

## Architecture Pattern

A reusable solution *shape*. Technology-independent. Tells the approach, not the product.

```
# Pattern: [Name]

## Problem
The recurring problem this solves, in one or two sentences.

## Context & Forces
When this situation arises; the competing forces that make it hard
(e.g. need for resilience vs. need for low latency).

## Solution
The shape of the solution — described abstractly, with a logical
diagram if useful. NOT a specific implementation.

## Trade-offs
What adopting this pattern costs you. Always present.

## When to use / When NOT to use
Explicit applicability. The "when not to" is what separates a real
pattern from cargo-culting.

## Related patterns
Patterns that combine with, compete with, or extend this one.
```

Common ones worth knowing cold: Circuit Breaker, Bulkhead, Retry-with-backoff, Strangler Fig, Sidecar, Ambassador, Anti-Corruption Layer, CQRS, Event Sourcing, Saga, Hub-and-Spoke, Publish-Subscribe, API Gateway, Backends-for-Frontends, Cache-Aside, Sharding, Leader Election, GitOps, Landing Zone.

---

## Reference Architecture

A domain blueprint applying patterns + standards. Technology-aware, not yet a running thing.

```
# Reference Architecture: [Domain, e.g. "Event-Driven Integration"]

## Business Drivers
Why this reference architecture exists; the outcomes it serves.

## Principles Applied
The architecture principles that constrain this design.

## Logical View
The capability/component view and the flows between them (C4 Container
level is usually right). Logical before physical.

## Key Architecture Decisions
The 3–6 decisions that define this architecture (link to ADRs).
For each: the decision and the dominant trade-off.

## Quality Attributes Addressed
The 2–3 NFRs this architecture is optimised for, and the targets
(e.g. RTO < 15 min, p99 latency < 200 ms).

## Standards & Patterns Used
Which org standards and which patterns this composes.

## Variation Points
Where teams are allowed to differ, and where they must not.
```

---

## Target Architecture

Where we are going, the gap, and how we get there.

```
# Target Architecture: [Scope]

## Current State (As-Is)
Honest summary of today, including the pain points / drivers for change.

## Target State (To-Be)
The destination. Capability and logical view. What's different and why.

## Gap Analysis
What must change across People / Process / Technology to get from
As-Is to To-Be. Group into themes.

## Migration Path
Sequenced — Now / Next / Later — ordered by dependency and value, not
by ease. Identify transition states (the architecture doesn't have to be
valid only at the endpoints). Strangler-fig over big-bang where possible.

## Risks & Dependencies
The things that could derail this and what de-risks them.

## Decision / Ask
What's needed to proceed (funding, mandate, a go decision).
```

---

## Capability Map

```
# Capability Map: [Business Area]

L1 capabilities (broad business functions), decomposed to L2/L3.
Each capability = a noun phrase, "what" not "how".

Overlay two signals per capability:
- Maturity (e.g. 1–5 or Low/Med/High)
- Strategic importance (Low/Med/High)

Heat: High-importance + Low-maturity = invest here first.
Flag: same capability delivered by multiple systems = duplication.
Gap: a needed capability with no owning system.
```

Present as a tiered grid or table. The output is an **investment signal**, expressed in business language.

---

## Standard / Principle

A standard nobody can comply with — or that has no governance — is documentation, not a standard.

```
# Standard: [Name]   (or Principle: [Name])

## Statement
The rule, stated imperatively. "All services MUST [X]."

## Rationale
The business / risk / quality reason. Why this rule exists.

## Implications
What teams must now do differently. The cost of compliance.

## Compliance Measure
How adoption/conformance is *verified* (automated check, gate, audit).
Without this, it's aspiration, not a standard.

## Exceptions
The sanctioned path to deviate (who approves, on what grounds, for how
long). Standards without exception paths get bypassed silently.
```

Good architecture **principles** are durable and trade-off-aware, e.g. "Buy before build," "Secure by design," "Data is an asset with a single owner," "Design for failure," "Standardise to simplify, vary only where it differentiates."

---

## Trade-off / Options Analysis

The core EA deliverable: a decision, defended.

```
# Options Analysis: [Decision]

## Driving Quality Attributes
The 2–3 NFRs that dominate THIS decision (weight them — they are not equal).

## Options
For each option (2–4 total):
- What it is (briefly)
- What it optimises
- What it sacrifices
- Cost direction (build/run, capex/opex)
- Key risk

## Comparison
A matrix: Options (rows) × Criteria (cols), scored against the WEIGHTED
driving attributes. Show the weighting — an unweighted matrix hides the
real decision.

## Recommendation
ONE option. The reasoning. The conditions under which you'd choose
differently (what would tip it).
```

**The one rule that matters:** end with a recommendation, not a matrix. The matrix is the working; the recommendation is the job.
