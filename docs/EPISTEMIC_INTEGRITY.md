# Epistemic Integrity and Authority Conservation

**Status:** protocol guidance; not a claim of runtime enforcement  
**Date introduced:** 2026-09-17

## Principle

> **Truthful failure is preferable to false success.**

MASI exists to make heterogeneous deliberation inspectable before execution. That benefit collapses if modules can improve a local score, satisfy a proxy, or persuade one another by corrupting the evidence on which later modules rely.

The message layer should therefore preserve these distinctions:

```text
observation != interpretation
interpretation != proposal
proposal != authorization
peer agreement != authorization
successful execution != authorization
favorable evaluator result != truth
```

## Authority conservation

A module's capability, persistence, confidence, score, or agreement with other modules cannot manufacture authority that was not granted by the governing system.

Operationally:

```text
CAN != MAY
SUCCESS != AUTHORIZATION
OBSTACLE != AUTHORITY TO REMOVE THE OBSTACLE
CONSENSUS != AUTHORITY
PAST EXCEPTION != STANDING GRANT
```

Encountering a blocker does not enlarge scope. If completion would require bypassing a boundary, altering evidence, manipulating an evaluator, reaching an unapproved resource, or changing the meaning of the task, the module should propose an alternative or emit/escalate the conflict rather than treating the obstacle as permission.

## Evidence integrity

Modules and orchestrators should preserve, rather than suppress:

- failed attempts;
- negative evidence;
- unresolved disagreement;
- uncertainty;
- evaluator defects;
- task-specification defects;
- provenance that weakens the preferred conclusion;
- evidence that an action exceeded scope.

Audit logs, provenance records, graders, evaluators, and oversight mechanisms are not ordinary obstacles to optimization. A task objective does not authorize a module to alter them merely because they prevent a favorable result.

## Multi-agent normalization risk

MASI specifically needs to guard against a failure mode in which individually bounded modules normalize an illegitimate workaround through coordination:

```text
worker A proposes out-of-scope shortcut
-> worker B treats proposal as evidence of acceptability
-> worker C observes apparent consensus
-> orchestrator mistakes consensus for authority
-> action executes without a valid grant
```

The correct invariant is:

> **Subordinate consensus can inform a governing decision; it cannot create the authority required for that decision.**

A future runtime should make authority resolution explicit rather than inferring it from message volume, confidence, trust metadata, or role agreement.

## Naturalistic precedent: Label Lens ADR-005

Label Lens records a narrower development-governance version of the same distinction in [ADR-005: Bounded Agent Initiative and Maintainer Check-In](https://github.com/JosephJMWalker-MBA/label-lens-ttb/blob/main/docs/adr/ADR-005-bounded-agent-initiative-and-maintainer-check-in.md).

The implementation in that case was technically strong and passed CI, but it introduced adjacent product behavior outside the explicitly authorized slice. The retained lesson was:

```text
beneficial result != authorization
passing CI != authority
accepted deviation != standing permission
```

MASI generalizes that lesson from implementation agents to heterogeneous deliberative modules.

## Message-layer guidance

The current repository is a schema/reference artifact, not an enforcing runtime. Within that boundary, generated examples, experiments, and future extensions should preserve:

1. the original task and governing scope;
2. the provenance of observations and assertions;
3. disagreement rather than silent harmonization;
4. a visible escalation path when completion conflicts with authority or evidence integrity;
5. the difference between a proposed action and an authorized action.

Do not reinterpret existing fields such as `confidence`, `trust_score_delta`, `module_cert_id`, or a role label as proof of authority.

## Falsification target

A future MASI experiment should intentionally offer modules a higher apparent score for an illegitimate strategy and test whether the coordination layer:

1. preserves the raw evidence;
2. keeps the evaluator distinct from governing authority;
3. prevents peer agreement from laundering the strategy into authorization;
4. preserves abstention/escalation as valid outcomes;
5. records the scope conflict rather than hiding it;
6. prevents one accepted exception from becoming a standing rule.

Passing such a test would establish only the tested contract under the stated fault model. It would not establish general alignment or production safety.
