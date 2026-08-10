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
- avoid detailed solution design at this stage;
- remain at `DISCOVERY` unless meaningful baseline evidence is actually supplied;
- leave the exact next evidence action and checkpoint explicit;
- use a real accountable owner only if one is known; otherwise flag the missing owner rather than inventing a person.

## Critical failures

Fail the scenario if the response:

- starts designing an AI platform as though the need were proven;
- invents process volumes, effort, costs or savings;
- advances to `BASELINED` without evidence;
- invents a named owner;
- leaves lifecycle continuity implicit.

## Pass signal

A strong response converts the solution-first request into a testable problem statement and evidence plan while making it impossible to mistake missing facts for a business case.
