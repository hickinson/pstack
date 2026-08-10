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

Every healthy active engagement must have:

- current lifecycle state;
- a real accountable owner;
- non-empty next action;
- checkpoint defined as either a review date or triggering event.

`CLOSED` is the only state that may omit an active next action and checkpoint.

If any required health condition is missing, report the engagement as **unhealthy** and identify the smallest corrective action.

Never invent an accountable owner or treat placeholders such as `TBD`, `unknown` or `unassigned` as healthy ownership. If no real accountable person is known, `owner` may be `null` in project state so the gap is represented truthfully; the engagement remains unhealthy until a real person is assigned.

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
ITERATE → appropriate earlier lifecycle state (gate-dependent)
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

### ITERATE → re-entry state

`ITERATE` may move to the earlier lifecycle state that truthfully represents the next work.

The target state's normal gate still applies. Re-entry must not be used to bypass missing discovery evidence, reuse investigation, proposal quality or human approval.

Examples:

- return to `DISCOVERY` when the problem, users, process or current state materially differs from what was previously understood;
- return to `INVESTIGATING` when the baseline remains useful but new solution routes must be examined;
- return to `PROPOSAL` when the solution decision or commercial proposition requires renewed human consideration;
- return to an approved/implementation state only when the existing approval remains valid for the proposed iteration and the relevant handoff gate is satisfied.

Preserve valid evidence and realised-benefit learning from the previous cycle rather than pretending the engagement is starting from nothing.

## State file

Use `assets/engagement.json` as the starting shape and `references/engagement-state.schema.json` as the validation contract.

The `owner` key is always present. A real person's name represents assigned accountability; `null` may be used only to represent unresolved ownership truthfully and always makes an active engagement unhealthy. Placeholder strings are not a valid substitute for ownership.

Keep the state file small. Do not add:

- task lists;
- conversation transcripts;
- credentials;
- full client evidence;
- duplicate histories;
- technical delivery backlog.

Git history already records changes to the state file.

When another pstack lifecycle skill has completed successfully, validate the state it leaves behind rather than requiring a redundant second ceremony. If the skill could not safely write project state, apply or return the smallest exact state-file update needed.

## Checkpoint activation

The checkpoint in `.pstack/engagement.json` is the portable source of truth, but a recorded date or event should not be mistaken for an active notification service.

When a checkpoint is created or repaired:

- keep the portable checkpoint in project state regardless of host;
- if the current host already provides a native reminder, task, scheduling or condition-watch capability, use or offer that native capability when it would materially reduce the chance of the checkpoint being forgotten;
- preserve normal host permission and confirmation semantics;
- do not make engagement health depend on a particular provider or reminder service;
- do not add a pstack scheduler, database, MCP server or bespoke notification runtime merely to activate checkpoints.

If no native activation is available, say clearly that the checkpoint is recorded but no external reminder has been created.

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
7. state-file update required;
8. checkpoint activation status when relevant.

Make the smallest safe state change that reflects reality. Never advance state merely because the next document can be generated.
