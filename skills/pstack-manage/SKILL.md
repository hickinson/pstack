---
name: pstack-manage
description: Manage a pstack technology-solution engagement lifecycle, validate state transitions, flag missing owners or checkpoints, enforce approval and handoff boundaries, accept delivery hand-back, and trigger benefit review. Use when creating or checking .pstack/engagement.json, asking what should happen next in an existing pstack engagement, moving between lifecycle states, handing an approved solution to delivery, or returning a live solution to pstack.
---

# pstack-manage

Manage lifecycle state without becoming a project-management system.

## Inputs

Use the available project context, especially:

- `.pstack/engagement.json`, if it exists;
- completed pstack artefacts;
- explicit human decisions or approvals;
- delivery status and hand-back evidence.

Do not place client context in the pstack methods repository.

## Core rule

Every active engagement must have:

- current lifecycle state;
- accountable owner;
- non-empty next action;
- checkpoint defined as either a review date or triggering event.

`CLOSED` is the only state that may omit an active next action and checkpoint.

If any required field is missing, report the engagement as **unhealthy** and identify the smallest corrective action.

The lifecycle skills themselves must preserve this state continuity. `pstack-manage` is the explicit validator and repair/control skill; it is not a ritual that users should have to invoke between every successful lifecycle capability.

## Lifecycle

Use only these states:

```text
IDEA
DISCOVERY
BASELINED
INVESTIGATING
OPTIONS_READY
PROPOSAL
APPROVED
IMPLEMENTATION_READY
BUILDING
LIVE
BENEFIT_REVIEW
CLOSED
ITERATE
```

## Normal transitions

```text
IDEA → DISCOVERY
DISCOVERY → BASELINED
BASELINED → INVESTIGATING
INVESTIGATING → OPTIONS_READY
OPTIONS_READY → PROPOSAL
PROPOSAL → APPROVED
APPROVED → IMPLEMENTATION_READY
IMPLEMENTATION_READY → BUILDING
BUILDING → LIVE
LIVE → BENEFIT_REVIEW
BENEFIT_REVIEW → CLOSED
BENEFIT_REVIEW → ITERATE
```

Do not force an invalid transition just to make progress.

## Transition gates

### IDEA → DISCOVERY

Discovery has actively started.

### DISCOVERY → BASELINED

Require sufficient evidence to describe the current state and meaningful measures.

If material baseline evidence is missing, stay in `DISCOVERY`.

### BASELINED → INVESTIGATING

The problem is sufficiently grounded to begin reuse-first solution investigation.

### INVESTIGATING → OPTIONS_READY

Require:

- meaningful investigation of relevant configure/extend/integrate/buy/reuse/build routes;
- materially different viable options where warranted;
- an explicit recommendation.

### OPTIONS_READY → PROPOSAL

A client-quality, commercially credible proposal exists.

### PROPOSAL → APPROVED

Require explicit, attributable human approval.

Never infer approval from:

- silence;
- a positive draft review;
- the proposal existing;
- AI confidence;
- technical feasibility.

### APPROVED → IMPLEMENTATION_READY

Require an implementation handoff that lets delivery act without reconstructing the sales or discovery conversation.

### IMPLEMENTATION_READY → BUILDING

Require delivery acceptance or an explicit delivery owner taking responsibility.

### BUILDING → LIVE

Require:

- the solution to be live;
- delivery hand-back;
- material deviations and actual delivery information captured;
- a benefit-review trigger or review date.

### LIVE → BENEFIT_REVIEW

Move when the agreed review trigger/date is reached and relevant actual outcome evidence can be assessed.

### BENEFIT_REVIEW → CLOSED

Require the benefit review to be complete and no further iteration currently justified.

### BENEFIT_REVIEW → ITERATE

Use when the review justifies further change.

For `ITERATE`, define the next action and choose the appropriate re-entry point deliberately. Do not assume every iteration restarts at DISCOVERY.

## State file

Use `assets/engagement.json` as the starting shape and `references/engagement-state.schema.json` as the validation contract.

Keep the state file small. Do not add:

- task lists;
- conversation transcripts;
- credentials;
- full client evidence;
- duplicate histories;
- technical delivery backlog.

Git history already records changes to the state file.

When another pstack lifecycle skill has completed successfully, validate the state it leaves behind rather than requiring a redundant second ceremony. If the skill could not safely write project state, apply or return the smallest exact state-file update needed.

## Delivery hand-back

When delivery returns a live solution, use `assets/delivery-handback.md`.

The hand-back should link to delivery evidence such as repositories, PRs, releases, test evidence and runbooks rather than copying them into pstack.

## Output

When asked to manage or review an engagement, return:

1. current lifecycle health;
2. transition validity, if a transition is proposed;
3. missing evidence or gate conditions;
4. exact next action;
5. owner;
6. checkpoint;
7. state-file update required.

Make the smallest safe state change that reflects reality. Never advance state merely because the next document can be generated.
