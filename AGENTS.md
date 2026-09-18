# Agent Guidance — MASI Bus

Read this before editing protocol semantics, examples, benchmark material, or governance documentation.

## Repository boundary

MASI Bus is currently a **reference message schema and example artifact**, not a live orchestration or enforcement runtime.

Do not claim that a documented rule is already enforced unless executable evidence exists in this repository.

## Epistemic-integrity gate

Read [`docs/EPISTEMIC_INTEGRITY.md`](docs/EPISTEMIC_INTEGRITY.md).

Before proposing a change, preserve these distinctions:

```text
observation != interpretation
interpretation != proposal
proposal != authorization
peer agreement != authorization
successful execution != authorization
```

A blocker does not enlarge scope. A favorable result does not mint authority. Agreement among modules does not create a governing grant.

When a requested objective cannot be completed without exceeding the authorized boundary, preserve the conflict and use the protocol's escalation semantics rather than silently redefining the task or evidence.

Do not delete, rewrite, or hide negative evidence, failed attempts, provenance, or disagreement merely to make an example, benchmark, or protocol narrative appear successful.

## Change discipline

Protocol changes should distinguish:

- current schema fact;
- example convention;
- proposed future runtime behavior;
- governance requirement;
- empirical claim.

Do not collapse those categories.

If a change would alter authority meaning, execution eligibility, trust semantics, or the relationship between proposal and authorization, make that semantic change explicit in documentation and tests rather than smuggling it through an example or naming convention.
