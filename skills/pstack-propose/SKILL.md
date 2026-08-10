---
name: pstack-propose
description: Turn evidence, reuse investigation and recommended solution options into a decision-quality technology proposal with visible assumptions, then create an implementation-ready handoff only after explicit human approval. Use when an engagement is OPTIONS_READY or PROPOSAL, when a proposal or concise decision record needs drafting or challenge, when approval must be recorded, or when an approved solution must be handed cleanly to delivery.
---

# pstack-propose

Make the recommendation decision-quality and commercially credible where commercial analysis is material, without disconnecting it from the evidence.

## Inputs

Use:

- discovery and baseline;
- investigation findings;
- solution-options comparison;
- selected recommendation;
- relevant client or project constraints and responsibilities.

If the recommendation is not supported by evidence or materially different options were required but not considered, return to the relevant earlier capability.

## Proportionate output

The lifecycle gate is stable; the size of the artefact is not.

Scale proposal depth according to consequence, uncertainty, cost, stakeholder complexity and the need for a durable external decision record.

For client-facing, high-cost, regulated, security-sensitive or otherwise consequential work, a fuller client-quality proposal is normally appropriate.

For a low-risk personal, exploratory or small internal project, a concise decision record may satisfy `PROPOSAL` when it makes the decision inspectable by capturing:

- the problem or desired outcome;
- the evidence that is material to the decision;
- serious options considered;
- the recommendation and why it wins;
- material costs, risks, constraints and exclusions;
- what success will look like.

Do not manufacture financial ROI, a procurement-style business case or stakeholder ceremony merely to make a small project look formal.

Adjacent lifecycle states may be satisfied in one interaction when every gate is genuinely met. This compresses ceremony; it does not remove the need for explicit approval or an implementation-ready handoff.

## Part 1 — Proposal or decision record

Use `assets/proposal.md` where its structure is useful. Do not fill sections mechanically when they are immaterial.

### Preserve traceability

The proposition should make it possible to understand:

- what problem exists;
- what evidence supports it;
- what options were considered;
- why the recommendation wins;
- what it is expected to cost where material;
- what value or outcome is expected;
- which assumptions and uncertainties remain.

Do not convert weak evidence into confident sales language.

### Commercial credibility

Only model cost and benefit dimensions that are material to the decision.

Where relevant, separate:

- one-off implementation cost;
- licence/consumption cost;
- migration/integration cost;
- training/change cost;
- recurring platform/service cost;
- recurring support cost.

Use ranges when appropriate.

For material cost and benefit claims, show the basis and confidence rather than presenting an unsupported number as fact.

Non-financial outcomes are valid. Do not invent a monetary value simply because the method can model one.

### Implementability

The proposition should be specific enough that the approved direction can later be handed to delivery without reinterpretation.

It does not need to contain the final engineering plan.

### Proposal state

When the decision-quality proposition exists, the engagement may move to `PROPOSAL`.

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

Recommend `IMPLEMENTATION_READY` only when delivery can understand, to the depth material for the engagement:

- problem and outcome;
- approved option;
- scope and exclusions;
- functional expectations;
- important non-functional requirements;
- architecture/platform/integration/data/security constraints;
- dependencies;
- assumptions and unresolved questions;
- acceptance criteria;
- benefit or outcome targets and measurement method;
- approved cost/time assumptions where material;
- operational/support expectations;
- remaining risks;
- accountable owners.

After that point, build/test/ship belongs to the project's normal delivery environment.

## Lifecycle continuity

Do not finish PROPOSE while leaving engagement state implicit.

At each actual gate, keep state aligned to reality:

- `PROPOSAL` when the decision-quality proposition exists but approval has not been explicitly recorded;
- `APPROVED` only after attributable human approval is recorded in the proposal, decision record or another durable project record;
- `IMPLEMENTATION_READY` only after the approved implementation handoff satisfies the gate above.

For the current truthful state, determine and return:

- accountable owner;
- one concrete next action;
- one checkpoint: review date or triggering event.

If the project workspace is writable and pstack is operating on that project, update `.pstack/engagement.json`. If it cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.

## Output

Return:

1. proposal/decision-record readiness or gaps;
2. proportionate proposition artefact when requested;
3. approval status;
4. implementation-handoff readiness or gaps;
5. exact next action and checkpoint.

Do not perform software delivery work inside this skill.
