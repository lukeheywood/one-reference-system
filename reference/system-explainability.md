# System Explainability

This document defines system explainability as an engineering property: the ability of a system to describe itself in deterministic, inspectable terms.

It is written as a neutral reference for evaluating any system (software, platform, workflow, or socio-technical system), especially before adding AI augmentation.

---

## Definition

A system is *explainable* if it can deterministically answer the following questions using inspectable artifacts (not human memory):

- **WHAT exists?** (components, interfaces, data, contracts)
- **WHY does it exist?** (purpose, responsibilities, boundaries)
- **HOW does it work?** (flows, dependencies, constraints)
- **WHEN did events occur?** (timelines, ordering, triggers)
- **WHAT ran?** (executions, jobs, workflows, commands)
- **WHAT changed?** (diffs, releases, config changes, migrations)
- **WHAT is assumed?** (invariants, preconditions, scope, trust boundaries)
- **WHAT is unknown?** (gaps, unresolved questions, blind spots)

Explainability is not “good documentation.”
Explainability is the presence of a living, reproducible account of system reality.

---

## Deterministic vs Inferential Explanation

There are two broad ways systems get “explained”:

### Deterministic explanation
Explanation is derived from authored and inspectable artifacts:
- contracts, schemas, invariants
- versioned configuration
- execution logs with identifiers
- release notes and diffs
- run reports and provenance metadata

Deterministic explanations are:
- reproducible
- auditable
- diffable over time
- resilient to staff turnover

### Inferential explanation
Explanation is reconstructed by interpretation:
- “what we think happened”
- “how it usually works”
- dashboards without provenance
- model guesses over opaque state
- tribal knowledge and escalation chains

Inferential explanations are:
- fragile
- hard to audit
- dependent on specific people
- prone to drift under operational pressure

Most “messy systems” are messy because they rely on inferential explanation as the primary truth source.

---

## Why Explainability Matters (Operationally)

Systems that cannot explain themselves create hidden costs:

- **Tribal knowledge accumulation:** key information lives in individuals
- **Slow incident response:** time is spent reconstructing what happened
- **Low change confidence:** upgrades and migrations feel risky
- **AI instability:** AI outputs drift because the underlying system truth is not explicit
- **Identity coupling:** individuals become the “system interpreter,” which scales poorly

Explainability reduces these costs by moving system truth into inspectable artifacts.

---

## Explainability Surfaces

A practical explainability implementation typically includes:

### 1) Inventory surface (WHAT)
- component and interface inventory
- data stores and schemas
- ownership mapping (who owns what)

### 2) Contract surface (WHY / HOW)
- explicit responsibilities and boundaries
- invariants and constraints
- allowed/prohibited behaviors
- assumptions and trust boundaries

### 3) Execution surface (WHAT ran / WHEN)
- run identifiers and provenance
- job/workflow manifests
- input/output artifact tracking
- structured run reports

### 4) Change surface (WHAT changed)
- versioning and release notes
- config diffs
- migration records
- promotion rules (what is allowed to become “official”)

### 5) Gap surface (WHAT is unknown)
- known unknowns list
- failing checks and incomplete areas
- drift detection and unresolved questions

A system does not need all surfaces to begin improving.
It must have enough surfaces to answer the most important questions with inspectable evidence.

---

## Readiness Checklist (Quick Rubric)

Use this checklist to assess explainability readiness.

### Level 0 — Opaque
- System knowledge is mostly in people’s heads
- Logs exist but are not tied to runs or decisions
- Changes are hard to trace to outcomes

### Level 1 — Documented (but not grounded)
- Documentation exists but is static
- It does not reliably reflect runtime reality
- Incidents require human reconstruction

### Level 2 — Inspectable
- System can produce an inventory snapshot
- Key workflows produce run artifacts
- Changes are recorded and diffable

### Level 3 — Governed
- Contracts and invariants exist and are versioned
- There are regression gates / checks for drift
- Promotion rules determine what becomes “official”

### Level 4 — Explainable under load
- The system can answer “what ran / what changed / what’s assumed” during incidents
- Explanations are reproducible and cite artifacts
- AI augmentation uses deterministic surfaces as inputs, not as guesses

---

## Relationship to AI Augmentation

AI augmentation becomes safer when explainability is present.

A useful heuristic:

- If the system cannot deterministically answer “what exists” and “what ran,”
  AI will tend to amplify ambiguity.
- If the system can produce inspectable truth surfaces,
  AI can be used effectively for summarisation, translation, synthesis, and reporting.

AI does not replace explainability.
AI benefits from explainability.

---

## Practical Next Step

To improve explainability in any system, start by implementing one export:

**A deterministic “system snapshot”** that includes:
- current inventory (WHAT)
- recent runs (WHAT ran / WHEN)
- recent changes (WHAT changed)
- explicit assumptions (WHAT is assumed)
- known gaps (WHAT is unknown)

If that snapshot can be produced reliably and diffed over time, explainability is no longer aspirational.
It becomes a real system property.
