# Contributing

Thanks for your interest in improving the **enterprise-architect** skill. Contributions of all sizes are welcome — sharpening a rule, fixing a typo, or adding a reference file.

## Reporting issues

Open a GitHub issue and include:

- **What you expected** the skill to do, and **what it did** instead.
- The **prompt or scenario** that triggered it (redact anything confidential — the skill is meant to stay organisation-agnostic, and so should bug reports).
- If it's a triggering problem (the skill activated when it shouldn't, or didn't when it should), say which.

## Proposing changes (pull requests)

1. Fork the repo and create a branch.
2. Make the change, keeping it scoped — one idea per PR, the same way the skill keeps one idea per slide.
3. In the PR description, state the **claim**: what the change makes the skill do better, and why.
4. Open the PR against `main`.

## Skill writing style

This repo is a Claude Skill, not application code. Changes to `SKILL.md` and the reference files should hold the same bar the skill itself sets:

- **Frameworks are lenses, not recitations.** TOGAF, Zachman, C4, Wardley, DDD and the rest are thinking tools applied silently. Don't add content that lectures the audience by framework name; add content that makes the *judgement* better.
- **Be concise.** Prefer a tight table or a short list to prose. If a paragraph can be a row, make it a row. Every added line competes for model attention.
- **Claim-style headings.** Headers and slide titles carry the message — "Hub-and-spoke cuts integration cost 40%," not "Integration Approach." Avoid label-style headers.
- **Respect the three-zone structure.** `SKILL.md` is laid out as PRIMACY (identity, hard rules, output lock) → MIDDLE (method, frameworks, artifacts, diagnostics) → RECENCY (verification). Put new material in the zone that matches its job; don't bloat PRIMACY with detail that belongs in a reference file.
- **Keep it agnostic.** No company, person, client, or proprietary context — ever. The skill must work for any enterprise out of the box.
- **Load on demand.** Deep detail goes in `references/`, read only when a task needs it. Keep `SKILL.md` lean.

## License

By contributing, you agree that your contributions are licensed under the [MIT License](LICENSE) that covers this project.
