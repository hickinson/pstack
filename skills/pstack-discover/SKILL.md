---
name: pstack-discover
description: Turn a raw technology-related client problem, pain point, opportunity or proposed solution into an evidence-seeking problem definition, current-state assessment and measurable baseline. Use when an engagement is at IDEA or DISCOVERY, when someone says they need an app, automation, AI, integration or system change before the underlying problem is proven, or when current process, evidence, stakeholders, constraints and baseline measures are unclear.
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

Use `assets/discovery.md` for the durable output.

Recommend `BASELINED` only when there is enough evidence to support meaningful investigation and later benefit reasoning.

Otherwise keep the state at `DISCOVERY` and define the exact next evidence action.

## Lifecycle continuity

Do not finish DISCOVER while leaving engagement state implicit.

At the end of the work, determine and return:

- current/recommended state: `DISCOVERY` or `BASELINED`;
- accountable owner;
- one concrete next action;
- one checkpoint: review date or triggering event.

If the project workspace is writable and pstack is operating on that project, create or update `.pstack/engagement.json` to reflect reality. If it cannot be updated safely, return the exact state-file values that should be written.

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

Initial opportunities may be noted, but detailed solution investigation belongs to `pstack-investigate`.
