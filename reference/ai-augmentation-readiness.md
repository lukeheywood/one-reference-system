# AI Augmentation Readiness

This document defines when and how a system is ready to be augmented with AI.

It builds on the explainability criteria defined in
[`system-explainability.md`](./system-explainability.md).

AI augmentation is treated as a dependent capability.
It does not compensate for missing system truth.

---

## Core Principle

AI should only be applied once a system can explain itself deterministically.

If a system cannot answer:
- what exists
- what ran
- what changed
- what is assumed

then AI will amplify ambiguity rather than reduce it.

---

## Readiness Levels

### Level 0 — Not Ready
- System truth lives primarily in people
- Outputs require interpretation or reconstruction
- AI responses rely on inference over opaque state

**AI impact:** High hallucination risk, low trust

---

### Level 1 — Partially Ready
- Some inventories and logs exist
- Documentation is present but not reliably grounded
- Explanations still require human mediation

**AI impact:** Useful for summarisation, unsafe for decision support

---

### Level 2 — Explainable
- Deterministic inventories exist
- Executions produce identifiable run artifacts
- Changes are traceable and diffable

**AI impact:** Safe for reporting, synthesis, translation, and Q&A

---

### Level 3 — Governed
- Explicit contracts and invariants are defined
- Drift detection and regression checks exist
- Promotion rules constrain what becomes “official”

**AI impact:** Safe for planning support, analysis, and scoped automation

---

### Level 4 — Explainable under load
- The system can explain itself during incidents
- Explanations cite artifacts, not interpretation
- AI reads from deterministic truth surfaces

**AI impact:** Reliable augmentation without identity or trust collapse

---

## Unsafe AI Patterns

The following patterns indicate premature AI use:

- Using AI to infer system behavior from logs alone
- Treating AI output as system truth
- Allowing autonomous actions without deterministic context
- Replacing inspection with model interpretation

These patterns create opaque intermediaries and weaken governance.

---

## Safe AI Roles (Once Ready)

When readiness is achieved, AI can safely be used for:
- explanation and summarisation
- translation between technical and non-technical views
- report generation from inspection artifacts
- comparison and diff interpretation
- question answering over declared system truth

AI remains a **reader and synthesiser**, not the system’s authority.

---

## Practical Gate

Before applying AI, a system should be able to emit:

- a deterministic system snapshot
- a recent execution report
- a change log with provenance
- a declared assumptions list

If these artifacts exist and are diffable, AI augmentation is appropriate.
If not, explainability should be addressed first.
