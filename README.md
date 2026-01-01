# ONE — Reference System

This repository is the **living reference system** for ONE.

It exists to make the system *legible to itself* — to surface, in concrete terms, what exists, what runs, what is governed, and where drift is occurring.

This is not a demo or a product.  
It is the system’s **source of truth**.

---

## 🧭 What this repo is

The reference system anchors ONE’s internal coherence by:

- Enumerating components, workflows, interfaces, and data domains
- Classifying what is **ready**, **partial**, **draft**, or **unknown**
- Providing a formal inspection path that reports system state in black and white
- Making drift visible when ownership, contracts, or structure are missing

It allows the system to explain itself without narrative, inference, or hand-waving.

---

## 🔍 Inspection & explainability

This repository contains a **runnable inspection workflow** that:

- Consumes a project root
- Traverses declared registries, contracts, and filesystem domains
- Emits inspection artifacts, including:
  - a system snapshot (for example: `snapshot_20260101T011538Z.json`)
  - an inspection report

These artifacts describe:

- Which components and interfaces exist
- Their current readiness status
- Which contracts apply
- Where drift, gaps, or unowned assets are present

This inspection layer is intentionally **non-agentic**.  
It does not decide what to do — it reports what *is*.

---

## 🧱 Role within ONE

Within the broader ONE system, this repo functions as:

- The canonical reference point for **system truth**
- The bridge between execution and governance
- The gate that prevents imagined capability from replacing inspected reality

Other engines (Memory OS, Autopilot, Portfolio Engine) may execute workflows and produce outputs.

This repository ensures those capabilities are:
- declared,
- inspectable,
- and accountable over time.

---

## 🚧 Status & intent

Some structures in this repository are still evolving.  
Some artifacts intentionally surface **unknowns** or **FAIL/WARN states**.

That is expected.

The purpose of the reference system is not to appear complete, but to remain **honest**, **traceable**, and **drift-resistant** as the system grows.

---

*If other parts of ONE are the muscles and nerves,  
this repository is the mirror.*
