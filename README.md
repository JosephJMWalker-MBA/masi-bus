# MASI Bus

**Reference message schema for Modular Artificial Specialized Intelligence (MASI)**

MASI Bus is the shared communication protocol introduced in the published defensive disclosure:

> Joseph JM Walker, **“Coordinated, heterogeneous model composition under a shared governance and audit layer.”**  
> Technical Disclosure Commons, Defensive Publications Series, Article 9043, December 15, 2025.  
> https://www.tdcommons.org/dpubs_series/9043/

This repository preserves a concrete reference artifact for that disclosure: a JSON Schema, example messages, contribution guidance, and a benchmark-reporting template for experimenting with **Consult-Before-Execute (CBE)** coordination among specialized AI roles.

## Status

MASI Bus is an authored protocol and defensive-disclosure artifact. It is **not an adopted industry standard, certification authority, public registry, or production orchestration platform**.

The repository currently defines message structure and examples. It does not provide a runtime that discovers models, routes live traffic, computes authoritative trust scores, performs certification, or enforces governance across deployed AI systems.

Future concepts referenced in the project—such as a public module registry, certification process, DAO-style governance, or contributor-credit system—should be treated as proposed ecosystem ideas unless and until they are separately implemented.

## What the Schema Represents

A MASI Bus message can carry:

- a message type such as task initiation, role analysis, critique, arbitration, resolution, final output, or escalation;
- the sending role or module;
- a task identifier;
- analysis, assertions, and a proposed action;
- reported confidence, cost, trust-score delta, and optional risk quantification;
- optional module credentials and ethical flags; and
- an audit-trail object containing timestamps, prior-message references, and conflicts.

These fields provide a common envelope for heterogeneous modules to communicate in a way that can be inspected and audited. The presence of a field such as `confidence`, `trust_score_delta`, or `module_cert_id` does **not** by itself establish that the value is calibrated, independently verified, or issued by a functioning certification system.

## Repository Contents

- `schema/masi-bus-schema.json` — MASI Bus reference JSON Schema, version 1.0
- `examples/01_task_init.json` — example task initialization message
- `examples/02_wisdom_analysis.json` — example Wisdom-role analysis
- `examples/03_foresight_critique.json` — example Foresight-role critique
- `examples/04_empathy_evaluation.json` — example Empathy-role evaluation
- `examples/05_precision_resolution.json` — example Precision-role resolution proposal
- `benchmarks/TEMPLATE.md` — template for reporting empirical or clearly identified simulated benchmark results
- `CONTRIBUTING.md` — contribution and extension guidance

## Quick Start

1. Use `schema/masi-bus-schema.json` as the structural contract for a MASI Bus message.
2. Inspect the files in `examples/` for a sample CBE-style sequence.
3. Validate your own messages with a JSON Schema Draft 2020-12 validator.
4. If you experiment with a module or extension, document its evidence and assumptions separately from the protocol itself.

## Design Intent

The protocol explores a shift from one monolithic model making an opaque end-to-end decision toward multiple specialized roles exchanging explicit, inspectable artifacts before execution.

The broader MASI disclosure frames this around ideas including:

- **Consult-Before-Execute** coordination;
- heterogeneous specialized roles;
- explicit disagreement and critique;
- governance and auditability;
- trust and risk metadata; and
- escalation when modules cannot safely resolve a conflict.

MASI Bus is the message-layer artifact for exploring those ideas. It does not prove that any particular role decomposition, trust metric, or governance scheme improves model quality or safety; those claims require empirical evaluation.

## Provenance

This repository is intended to accompany and implement part of the terminology and protocol structure described in Technical Disclosure Commons Article 9043. The publication is the parent conceptual disclosure; this repository is the reference schema and example-message artifact.

The term **MASI Bus** is therefore retained intentionally rather than treated as a generic event-bus name.

## Licensing

The repository currently declares its protocol/schema material for public use under **CC0 1.0 Universal**, with attribution requested where practical. The associated Technical Disclosure Commons publication is a separate published work and is governed by the licensing terms displayed on its publication page.

Contributions remain subject to their own applicable licensing unless explicitly dedicated otherwise. See `CONTRIBUTING.md` before submitting changes.

## Core Philosophy

**Competition → Cooperation**  
**Secrecy → Transparency**  
**Scale race → Sustainable commons**

---

**Author:** Joseph J.M. Walker, MBA  
**Organization named in the original repository materials:** Pair A Dimes, Inc.  
**Reference publication:** Technical Disclosure Commons, Defensive Publications Series, Article 9043
