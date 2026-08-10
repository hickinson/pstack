---
name: pstack-discover
description: Turn a raw technology-related client problem, pain point, opportunity or proposed solution into an evidence-seeking problem definition, current-state assessment and measurable baseline. Use when an engagement is at IDEA or DISCOVERY, when someone asks what app, automation, AI, integration or system should be built before the underlying problem and baseline are proven, or when current process, evidence, stakeholders, constraints and baseline measures are unclear. While material baseline evidence is missing, stop at discovery and do not produce a solution architecture, feature backlog or build plan.
---

# pstack-discover

Start from the problem, not the requested technology.

## Goal

Produce a discovery artefact that is good enough to support reuse-first investigation without pretending that missing evidence is known.

## Inputs

Accept whatever exists, including:

- a raw idea;
- a client request;
- a pain point;
- a proposed solution;
- existing documents, interviews, observations or metrics;
- known constraints.

Do not require the user to complete another intake template before starting.

## Method

### 1. Separate problem from proposed solution

If the request is solution-first, explicitly restate:

- the proposed solution;
- the underlying problem or opportunity it appears intended to address;
- what evidence would prove the problem matters.

Challenge premature statements such as:

- "we need AI";
- "we need an app";
- "we should automate this";
- "we need a new platform".

Do not reject the idea. Reframe it as a hypothesis until evidence supports it.

### 2. Identify affected people and process

Establish:

- who performs or receives the process;
- who owns the outcome;
- where hand-offs occur;
- which systems, data and tools are involved;
- where time, cost, delay, error, risk or lost value appears.

### 3. Establish the current state

Describe what appears to happen today.

Prefer evidence from:

- direct observation;
- system data;
- process walkthroughs;
- documents;
- interviews;
- existing reporting.

Distinguish evidence from interpretation.

### 4. Build the baseline

Identify the measures needed to judge whether change would be worthwhile.

Typical measures include:

- transaction or case volume;
- frequency;
- elapsed time;
- staff effort;
- unit cost;
- error/rework rate;
- backlog;
- response time;
- conversion;
- service quality;
- risk exposure.

Do not invent values.

If a value is estimated, show the calculation or reasoning and mark it `ESTIMATED`.

### 5. Expose evidence gaps

Classify important statements as appropriate:

- `OBSERVED`;
- `SOURCED`;
- `ESTIMATED`;
- `ASSUMED`;
- `UNKNOWN`.

Call out missing evidence that could materially alter the problem definition or eventual business case.

### 6. Define the desired outcome

Express success as an outcome rather than a feature.

Prefer:

- "reduce manual processing time while maintaining quality"

over:

- "build an AI workflow".

### 7. Decide discovery status

Use `assets/discovery.md` as a template for the durable project output.

Recommend `BASELINED` only when there is enough evidence to support meaningful investigation and later benefit reasoning.

Otherwise keep the state at `DISCOVERY` and define the exact next evidence action.

## Stage boundary — hard stop

`DISCOVERY` is not permission to design the solution while adding a caveat that more evidence is needed.

If material baseline evidence is still missing, do **not** provide:

- a target solution architecture;
- a product or platform blueprint;
- a feature list or prioritised backlog;
- a vendor/product shortlist;
- a phased build or implementation plan;
- solution-specific technology choices;
- invented KPI targets or benefit claims.

This applies even when the user explicitly asks "what should we build?" or asks for a roadmap. Explain that solution design is premature, state what must be learned next, and stop at the discovery output.

A previous discovery note does not remove this boundary. If its baseline status is partial or insufficient, remain in `DISCOVERY`.

Detailed solution investigation belongs to `pstack-investigate`; materially different solution options belong to `pstack-design`.

## Artefact location and template safety

Files inside the installed skill are reusable method assets, not project working documents.

Treat `assets/discovery.md` as a read-only template. Never write project/client content back into:

- `.github/skills/`;
- `.agents/skills/`;
- `.claude/skills/`;
- the canonical pstack `skills/` tree.

When the project workspace is writable, create or update the project-side discovery artefact in the project's normal documentation location, normally `docs/pstack/discovery.md`, or an equivalent established project path.

Do not mutate the installed skill to record an engagement.

## Lifecycle continuity

Do not finish DISCOVER while leaving engagement state implicit.

At the end of the work, determine and return:

- current/recommended state: `DISCOVERY` or `BASELINED`;
- accountable owner;
- one concrete next action;
- one checkpoint: review date or triggering event.

Never invent an accountable owner or use a placeholder as though it were valid state. If no real accountable person is known, report the engagement as unhealthy, make owner assignment the smallest corrective action, and keep that gap explicit until a person is actually assigned.

If the project workspace is writable and pstack is operating on that project, create or update `.pstack/engagement.json` to reflect reality. The state contract may represent an unresolved owner as `null`; that is explicitly unhealthy until a real accountable person is assigned. Do not use strings such as `TBD`, `unknown` or `unassigned` merely to satisfy the schema.

If state cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.

## Output quality

A good discovery output makes these questions answerable:

- What problem are we actually solving?
- Who experiences it?
- What happens today?
- What evidence supports that?
- What does the current state cost or consume?
- What is still unknown?
- What outcome would count as better?
- What evidence should be gathered next?

Do not design solution options in depth during DISCOVER.

Initial opportunities may be noted only as hypotheses; do not turn them into a build recommendation before investigation and design.