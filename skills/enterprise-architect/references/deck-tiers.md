# Audience-Tiered Decks — same architecture, three altitudes

The same architectural decision must be told differently to three audiences. The *substance* is constant; the *altitude, vocabulary, and the question being answered* change. A world-class EA can move one architecture up and down this ladder without losing its spine.

The art is **subtraction, not translation** — each tier strips what that audience doesn't need rather than rewording everything. The C-suite deck is the engineering deck with the components removed and the money added.

---

## The three tiers at a glance

| | **C-LEVEL / BOARD** | **SOLUTION ARCHITECTS / ENG LEADERSHIP** | **ENGINEERING / DELIVERY** |
|---|---|---|---|
| **The question they answer** | "Do we fund / approve / mandate this?" | "Is this the right design, and can we build it?" | "How do I build to this standard?" |
| **Altitude** | Capability & outcome | Pattern & reference architecture | Reference implementation & contract |
| **Currency** | Money, risk, time, strategic fit | Quality attributes, trade-offs, sequencing | Interfaces, constraints, guardrails |
| **Diagram level (C4)** | Context (or none — a value diagram) | Container | Container → Component |
| **Vocabulary** | Plain business language, zero acronyms | Architecture vocabulary, named patterns | Precise technical spec |
| **Length** | 5–7 slides | 8–12 slides | As long as correctness needs |
| **Trade-offs shown as** | Options + 1 recommendation + $/risk | Full options matrix, NFR-weighted | The decision as a fixed constraint |
| **Analogies** | Essential — one per hard concept | Helpful for the novel ideas | Rarely needed |
| **What to cut** | All components, all vendors-as-heroes | The capex model, the strategy narrative | The "why we chose this" debate |
| **Ends on** | Decision / Ask | Design sign-off + open questions | Definition of done / conformance |

---

## C-LEVEL / BOARD deck

**They are deciding whether to spend money and accept risk.** Nothing else.

Spine (5–7 slides):
1. **Why now** — the driver, the pressure, the window. (So what.)
2. **The cost of today** — what the current state costs in money / risk / time. Quantify, even roughly.
3. **The options** — 2–3 directions as outcomes, one line each: what each buys, what each risks.
4. **The recommendation** — one direction, the business case in a sentence. *The slide everything builds to.*
5. **Investment & horizon** — cost direction (not a precise figure), now/next/later, when value lands.
6. **Risk — both ways** — risk of acting AND risk of not acting, with mitigations.
7. **Decision / Ask** — the exact decision in front of the room.

Rules: headlines are claims. No component diagrams — a single value or capability picture at most. Every acronym translated. Confident recommendation, not a menu. Clarity over precision: "roughly 40% cheaper" beats "39.7%."

What gets cut vs. the architect deck: the entire technical design, the NFR matrix, the pattern names, the sequencing detail. They trust you for that — your job here is the *case*, not the *blueprint*.

---

## SOLUTION ARCHITECTS / ENGINEERING LEADERSHIP deck

**They are deciding whether the design is right and buildable.** This is the EA's home turf and usually the most detailed deck.

Spine (8–12 slides):
1. **Problem & drivers** — the requirement and the quality attributes in tension.
2. **Principles & constraints** — the architecture principles and hard constraints in play.
3. **Current-state architecture** — honest As-Is, Container level, with the pain points marked.
4. **Options considered** — 2–4 genuine design options (patterns/reference architectures), one per slide or one comparison slide.
5. **Trade-off analysis** — the options matrix, scored against the *weighted* driving NFRs. Show the weighting.
6. **Target architecture** — the recommended design, Container-level C4, logical before physical.
7. **Key decisions (ADRs)** — the 3–6 decisions that define it, each with its dominant trade-off.
8. **Standards & patterns applied** — what this composes from the existing catalogue; variation points.
9. **Migration / sequencing** — now/next/later, transition states, strangler-fig where it fits.
10. **Risks, dependencies, open questions** — including what's still undecided and needs their input.

Rules: name the patterns (they speak the language). Show the NFR trade-offs explicitly. Logical diagrams before physical. End on sign-off plus the genuinely open questions — this audience expects to be consulted, not just informed.

What gets cut vs. the C-level deck: the strategy/why-now narrative compresses to one slide; the capex model is replaced by cost *direction* per option. What gets added: everything technical the board didn't see.

---

## ENGINEERING / DELIVERY pack

**They are deciding how to build to standard.** Not whether — that's settled. Give them the contract.

Content (length = whatever correctness requires; often a doc + reference implementation, not slides):
- **The reference implementation** — deployable example, IaC, landing zone, sample service.
- **Interface contracts** — APIs, events, data schemas, integration points. Precise.
- **Constraints & guardrails** — what they MUST do, MUST NOT do, and the policy-as-code that enforces it.
- **The decisions as fixed constraints** — the ADR outcomes presented as givens, not debates. (Link the ADRs for the "why," but don't relitigate.)
- **Definition of done / conformance** — how their work is checked against the standard. The compliance gate.
- **Component-level detail** — C4 Component where the internal structure matters.

Rules: precision over clarity here (the one place that inverts) — ambiguity costs delivery time. No analogies, no strategy. The trade-off debate is closed; present decisions as constraints with a link to the reasoning for the curious.

What gets cut vs. the architect deck: the options, the matrix, the "why we chose this." They need the *what* and the *how*, enforced — not the *why*, argued.

---

## Producing the actual file

This file governs **content, altitude, and structure**. To render a real `.pptx`, hand off to the environment's presentation skill (e.g. a `pptx` skill / pptxgenjs) — get the tiering and the argument right here first, then generate the file there. If an org-specific deck skill exists (branding, templates, house style), that skill's visual rules win; this file still decides *what goes on each slide for which audience*.

**The reframe move:** when asked to "take this up to the board" or "break this down for the team," don't rewrite from scratch — start from the existing tier and apply subtraction/addition per the table above. One architecture, re-altituded.
