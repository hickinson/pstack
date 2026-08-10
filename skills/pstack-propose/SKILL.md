---
name: pstack-propose
description: Turn evidence, reuse investigation and recommended solution options into a client-quality technology proposal with visible commercial assumptions, then create an implementation-ready handoff only after explicit human approval. Use when an engagement is OPTIONS_READY or PROPOSAL, when a proposal needs drafting or challenge, when approval must be recorded, or when an approved proposal must be handed cleanly to delivery.
---

# pstack-propose

Make the recommendation commercially credible without disconnecting it from the evidence.

## Inputs

Use:

- discovery and baseline;
- investigation findings;
- solution-options comparison;
- selected recommendation;
- relevant client constraints and responsibilities.

If the recommendation is not supported by evidence or materially different options were required but not considered, return to the relevant earlier capability.

## Part 1 — Proposal

Use `assets/proposal.md`.

### Preserve traceability

The proposal should make it possible to understand:

- what problem exists;
- what evidence supports it;
- what options were considered;
- why the recommendation wins;
- what it is expected to cost;
- what value is expected;
- which assumptions and uncertainties remain.

Do not convert weak evidence into confident sales language.

### Commercial credibility

Separate:

- one-off implementation cost;
- licence/consumption cost;
- migration/integration cost;
- training/change cost;
- recurring platform/service cost;
- recurring support cost.

Use ranges when appropriate.

For material cost and benefit claims, show the basis and confidence rather than presenting an unsupported number as fact.

### Implementability

The proposal should be specific enough that the approved direction can later be handed to delivery without reinterpretation.

It does not need to contain the final engineering plan.

### Proposal state

When the client-quality proposal exists, the engagement may move to `PROPOSAL`.

It must not move itself to `APPROVED`.

## Human approval gate

`PROPOSAL → APPROVED` requires explicit, attributable human approval.

Do not infer approval from:

- positive language;
- the user asking for implementation details;
- no objections;
- an AI review;
- technical feasibility.

Capture an approval reference that identifies who approved what and when.

## Part 2 — Implementation handoff

After approval, use `assets/implementation-handoff.md`.

The handoff should carry the approved business and solution decisions into delivery while leaving room for normal engineering refinement.

Delivery may refine implementation detail.

Delivery must escalate rather than silently reopen or contradict an approved business or solution decision.

## Implementation-ready gate

Recommend `IMPLEMENTATION_READY` only when delivery can understand:

- problem and outcome;
- approved option;
- scope and exclusions;
- functional expectations;
- important non-functional requirements;
- architecture/platform/integration/data/security constraints;
- dependencies;
- assumptions and unresolved questions;
- acceptance criteria;
- benefit targets and measurement method;
- approved cost/time assumptions;
- operational/support expectations;
- remaining risks;
- accountable owners.

After that point, build/test/ship belongs to the project's normal delivery environment.

## Lifecycle continuity

Do not finish PROPOSE while leaving engagement state implicit.

At each actual gate, keep state aligned to reality:

- `PROPOSAL` when the client-quality proposal exists but approval has not been explicitly recorded;
- `APPROVED` only after attributable human approval is recorded in the proposal or another durable project record;
- `IMPLEMENTATION_READY` only after the approved implementation handoff satisfies the gate above.

For the current truthful state, determine and return:

- accountable owner;
- one concrete next action;
- one checkpoint: review date or triggering event.

If the project workspace is writable and pstack is operating on that project, update `.pstack/engagement.json`. If it cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.

## Output

Return:

1. proposal readiness or gaps;
2. proposal artefact when requested;
3. approval status;
4. implementation-handoff readiness or gaps;
5. exact next action and checkpoint.

Do not perform software delivery work inside this skill.
