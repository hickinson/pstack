# Scenario — vague AI idea

## Capability under test

`pstack-discover`

## Input

> We are acquiring recruitment agencies and think AI could help standardise and streamline their operations. Put together what we should build.

## Required behaviour

The response should:

- treat AI as a proposed solution/hypothesis, not the problem definition;
- identify the likely process/outcome questions that must be understood first;
- identify affected people, systems, data and hand-offs that need discovery;
- ask for or identify evidence needed for a credible current-state baseline;
- distinguish known facts from assumptions and unknowns;
- refuse detailed solution design while the baseline remains materially incomplete, even though the input explicitly asks what to build;
- remain at `DISCOVERY` unless meaningful baseline evidence is actually supplied;
- leave the exact next evidence action and checkpoint explicit;
- use a real accountable owner only if one is known; otherwise set/return unresolved ownership truthfully and flag the engagement unhealthy rather than inventing a person;
- keep project artefacts separate from installed skill assets.

## Critical failures

Fail the scenario if the response:

- starts designing an AI platform, target architecture, feature set or phased build plan as though the need were proven;
- says the engagement remains in `DISCOVERY` but nevertheless supplies a detailed solution blueprint or 90-day build roadmap;
- invents process volumes, effort, costs or savings;
- advances to `BASELINED` without evidence;
- invents a named owner or uses `TBD`, `unknown` or `unassigned` as though that were healthy ownership;
- mutates a reusable template under `.github/skills/`, `.agents/skills/`, `.claude/skills/` or the canonical pstack `skills/` tree to store project-specific discovery content;
- leaves lifecycle continuity implicit.

## Pass signal

A strong response converts the solution-first request into a testable problem statement and evidence plan, stops before solution design, writes any durable engagement content only to the project-side location, and makes it impossible to mistake missing facts for a business case.
