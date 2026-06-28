# Frameworks — Working Detail (apply as lenses, never recite by name)

The audience should feel the rigour, not see the scaffolding. Use these as method; translate the output into plain capability/outcome language.

---

## TOGAF ADM — the engagement method

The Architecture Development Method is the spine of a full EA engagement. Phases:

- **Preliminary** — establish architecture capability, principles, governance, tooling.
- **A. Architecture Vision** — scope, stakeholders, drivers, high-level target, value proposition. *This is where executive buy-in is won.*
- **B. Business Architecture** — capabilities, value streams, org, processes. *What the business does, before any tech.*
- **C. Information Systems** — Data Architecture + Application Architecture. *What information exists and what applications act on it.*
- **D. Technology Architecture** — platforms, infrastructure, networks, the runtime. *The "where it runs."*
- **E. Opportunities & Solutions** — group changes into work packages; identify transition architectures.
- **F. Migration Planning** — sequence, dependencies, cost/value, roadmap.
- **G. Implementation Governance** — ensure delivery conforms to the architecture; architecture contracts.
- **H. Architecture Change Management** — handle change requests, keep the architecture living.
- **Requirements Management** (centre) — continuous, feeds every phase.

**How to use it:** Don't walk a stakeholder through phases A–H. Use ADM to *structure your own thinking* and to know which question you're answering. A roadmap request is mostly E+F. A "should we do this" request is mostly A+B. A target-state request spans B–D with the gap analysis in E.

**BDAT layers** — when a problem feels muddled, locate it: is this a **Business** problem (capability, process), a **Data** problem (ownership, model, flow), an **Application** problem (service boundaries, integration), or a **Technology** problem (platform, infra)? Most "architecture disagreements" are people arguing across different layers.

---

## C4 Model — diagramming for mixed audiences

Four zoom levels. Pick the level for the audience; don't mix levels on one diagram.

1. **Context** — the system as a box, its users, and the external systems it talks to. *For executives and non-technical stakeholders.*
2. **Container** — the major deployable/runnable units (apps, services, data stores) and how they communicate. *For architects and tech leads — usually the most useful EA level.*
3. **Component** — the internal building blocks of one container. *For developers of that container.*
4. **Code** — classes/structure. *Rarely needed at EA level; usually auto-generated.*

**EA default:** Context and Container. Always draw the **logical** view before the **physical**. Show flow and responsibility, not infrastructure detail, unless infrastructure *is* the point.

---

## Quality Attributes / NFRs (ISO 25010) — what actually decides trade-offs

Functional requirements say what the system does; quality attributes decide *how you build it* and dominate most architecture choices. The load-bearing set:

- **Reliability / Resilience** — availability, fault tolerance, recoverability (RTO/RPO).
- **Security** — confidentiality, integrity, authenticity, non-repudiation, auditability.
- **Performance Efficiency** — latency, throughput, resource utilisation.
- **Scalability** — vertical/horizontal, elasticity.
- **Maintainability** — modularity, testability, changeability.
- **Cost** — capex/opex, build/run, TCO (not in ISO 25010 but always present at EA level).
- **Compatibility / Interoperability** — integration, standards conformance.
- **Observability** — can you see what it's doing in production.
- **Compliance** — regulatory and policy conformance.

**The discipline:** for any decision, name the **2–3 NFRs that actually drive it**. Optimising all of them equally is impossible and is the signature of weak architecture. Trade-offs are usually pairwise: consistency vs. availability, latency vs. cost, flexibility vs. simplicity, security vs. usability.

---

## Wardley Mapping — strategy, sourcing, where to invest

Map components on two axes: **value-chain position** (visible to user → invisible) vs. **evolution** (Genesis → Custom-built → Product → Commodity/Utility).

**Why it matters for EA:** it tells you *build vs. buy vs. rent*. Build only in **Genesis/Custom** where differentiation lives; buy products in the middle; rent commodities (don't build your own auth, queue, or VM platform). It exposes when teams are custom-building something the market has commoditised — the most common waste in enterprise IT.

---

## Capability Mapping — aligning IT to the business

A capability is **what the business does**, expressed as a noun phrase ("Settlement Processing", "Customer Onboarding"), independent of *how* or *who*. Build a tiered map (L1 broad → L2/L3 granular).

**Uses:** overlay **maturity** and **strategic importance** to create a heat map — high-importance/low-maturity cells are where investment goes. Spot duplication (same capability built three times across business units) and gaps. Capability maps are the bridge that lets you talk to executives in *their* language while driving technology decisions underneath.

---

## Domain-Driven Design — service boundaries done right

- **Bounded Context** — an explicit boundary within which a model and its ubiquitous language are consistent. The antidote to the "one giant canonical model" failure.
- **Ubiquitous Language** — shared, precise vocabulary between domain experts and engineers, per context.
- **Context Mapping** — how bounded contexts relate (partnership, customer-supplier, conformist, anti-corruption layer, shared kernel).
- **Strategic vs. Tactical DDD** — at EA level you care about the *strategic* part: where the boundaries are. Tactical patterns (aggregates, entities) are delivery-level.

**Use it to** decompose monoliths and define service ownership so boundaries match business meaning, not technical convenience — which, via Conway's Law, also shapes team structure.

---

## Cloud Well-Architected & Adoption Frameworks

**Well-Architected pillars** (common across hyperscalers): Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimisation, Sustainability. Use as a **review lens** for any cloud target architecture — walk each pillar, find the weakest, decide if the trade is acceptable.

**Cloud Adoption Framework (org level):** Strategy → Plan → Ready (landing zones) → Adopt (migrate/innovate) → Govern → Manage. This is the *enterprise* cloud journey, distinct from designing one workload. Landing zones, guardrails (policy-as-code), and governance are the EA's domain; individual workload migration is delivery's.

---

## Risk, Security & Compliance frameworks

- **NIST CSF** — Identify, Protect, Detect, Respond, Recover. A clean structure for talking security posture to executives.
- **CIS Controls / Benchmarks** — concrete, prioritised hardening controls; good for "are we configured correctly" audits.
- **ISO 27001** — ISMS; control framework for formal certification/regulatory contexts.
- **Zero Trust** — never trust, always verify; identity as the perimeter; least privilege; assume breach.

**EA stance:** security and compliance are quality attributes and **principles**, not bolt-ons. "Secure by design" means the control is in the pattern, not in a remediation backlog.

---

## Zachman Framework — the completeness lens

A 6×6 matrix: interrogatives (**What, How, Where, Who, When, Why**) × perspectives (Contextual, Conceptual, Logical, Physical, Detailed, Operational). Zachman is **taxonomy, not method** — you don't "do" Zachman. Use it as a **checklist**: have I addressed *Why* (motivation/drivers), *Who* (org/roles), *When* (timing/sequencing), not just *What* and *How*? It catches the dimensions architects routinely skip.

---

## ArchiMate — formal modelling notation

When a rigorous, tool-backed, layered model is genuinely required (large transformation, regulatory traceability), ArchiMate provides standard notation across Business, Application, and Technology layers with defined relationships. Most of the time a C4 diagram plus prose is faster and clearer; reach for ArchiMate only when formal modelling is the requirement, not the default.
