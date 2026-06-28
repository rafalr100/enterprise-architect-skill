# Executive Communication — architecture for the boardroom

The hardest EA skill: making architecture *legible to people who will never read a diagram*. The goal is a decision, not a demonstration of cleverness.

---

## The executive mindset (architect to it)

Executives decide on **outcomes, money, risk, and time** — not on technology. When you present, they are silently asking three questions:

1. **So what?** — Why does this matter to the business / the strategy / the P&L?
2. **What do you need from me?** — A decision, funding, a mandate, air cover. Be explicit.
3. **What's the risk if we do / don't?** — Both directions. The cost of inaction is an argument you must make.

If a slide doesn't help answer one of those, it doesn't belong in an executive deck.

---

## Deck construction rules

- **6–8 slides.** Long decks signal an architect who can't prioritise. If it needs more, you haven't found the spine.
- **One idea per slide.** If a slide has two ideas, it's two slides or one idea is filler.
- **Headlines are claims, not labels.** The title carries the message. A reader who skims only the titles should get the whole argument.
  - Weak: "Integration Options"
  - Strong: "Hub-and-spoke cuts integration cost ~40% and removes our single point of failure"
- **3–5 bullets per slide, ≤12 words each.** Bullets are prompts, not paragraphs. The detail lives in your voice / the speaker notes.
- **One analogy per hard concept.** Analogies are how non-technical people grasp architecture. "We're building the highway before the cars arrive." "Patterns are recipes — proven, repeatable, but you still cook the meal." Use sparingly and precisely; a forced analogy is worse than none.
- **Separate on-slide text from speaker notes.** On-slide = the skimmable claim. Notes = what the presenter says: the reasoning, the anticipated pushback, the data, the analogy delivered in full.
- **End on a Decision / Ask slide.** Every executive architecture deck closes by naming exactly what you need: the decision, the options with your recommendation, the implication of each. Never end on "Thank you / Questions" — end on "Here's the decision in front of you."

---

## A reliable deck spine (adapt, don't follow blindly)

1. **The situation / why now** — the driver, the pressure, the window. (So what.)
2. **The problem or gap** — what's broken, costly, or risky about today. Quantify the pain.
3. **The options** — 2–3 genuine directions, each as one slide or one row. What each optimises and trades.
4. **The recommendation** — your one direction, with the reasoning. (This is the slide everything builds to.)
5. **What it takes** — cost direction, sequencing (now/next/later), key dependencies.
6. **The risks** — both of acting and of not acting, with mitigations.
7. **Decision / Ask** — exactly what you need from the room.

For a *target architecture* narrative, the spine is often: Where we are → Where we're going → Why it matters → What changes → What we need.

---

## Tone and language

- **Clarity over precision.** At the executive level, a directionally-correct round number beats a precise figure nobody can act on. "Roughly 40% cheaper" lands; "39.7% per the model in appendix C" does not.
- **Plain language, not jargon.** Translate every acronym and pattern name into business meaning. If you say "we'll use a strangler-fig migration," immediately follow with "—we replace the old system piece by piece while it keeps running, so there's no risky big-bang cutover."
- **Confident, not hedged.** Executives fund conviction. Give the recommendation plainly, then defend it. "I recommend X because Y" — not "there are several options, each with merits."
- **Lead with the answer.** No build-up. The first slide and the first sentence carry the conclusion; the rest is justification.
- **Make the trade-off visible, not hidden.** Naming what you're giving up builds trust and pre-empts the "but what about—" objection. Hiding it gets you caught.

---

## Common executive-deck failure modes

- **The architecture-tour deck** — slides full of components and arrows, no decision. Executives don't care how it works; they care what it means and what you need.
- **The flat option list** — three options, no recommendation. This pushes the architect's job onto the executive and reads as indecision.
- **The buried ask** — the request for a decision shows up on slide 14 as a sub-bullet. Surface it; end on it.
- **The unquantified pain** — "the current system is bad." How bad? In money, risk, or time? No number, no urgency.
- **Death by precision** — six decimal places where a direction was needed. Signals an architect who can't see the forest.
- **The acronym wall** — TOGAF, ADM, BDAT, NFR, RTO on an executive slide. Translate everything into outcomes.

---

## When generating an actual .pptx

If the deliverable is a real PowerPoint file (not just the content), use the appropriate document-creation skill for the environment (e.g. a `pptx` skill). This skill governs the *content and structure*; the document skill governs the *file generation*. Keep them separate: get the architecture argument right here, then render it there.
