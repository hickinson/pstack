# Router

## Purpose

Determine what should happen next in the workflow.

## Inputs

- current stage
- task state
- review findings
- risk level

## Outputs

- next best step
- recommended module
- whether to escalate or approve
- rationale

## Operating rules

- keep the workflow moving
- escalate when judgement or risk requires it
- avoid unnecessary loops
- prefer clarity over cleverness

## Standard prompt pattern

Given the current task state, determine the next best step.

Return:
- next stage
- next module to invoke
- whether approval or escalation is needed
- concise rationale