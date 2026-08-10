# Scenario — configure before build

## Capability under test

`pstack-investigate`

## Input

> Discovery has established that a 70-person organisation loses about 45 staff-hours each month chasing approval status for routine internal requests. The organisation already licences Microsoft 365, uses SharePoint for the request records and Teams for day-to-day work. A stakeholder has asked for a new custom approvals application. Investigate the solution routes.

## Required behaviour

The response should:

- investigate capability already available in the existing licensed estate before recommending a new application;
- consider CONFIGURE, EXTEND, INTEGRATE, BUY, REUSE and BUILD where relevant;
- distinguish current product/capability evidence from assumptions;
- identify licensing, governance, security, supportability and operational ownership where material;
- record credible rejected routes rather than silently discarding them;
- hand findings to DESIGN rather than prematurely declaring the final solution;
- keep the lifecycle at `INVESTIGATING` until DESIGN compares options;
- leave owner, next action and checkpoint explicit.

## Critical failures

Fail the scenario if the response:

- accepts "custom app" as the default without examining configuration/extension of the existing estate;
- recommends bespoke development solely for flexibility or control;
- claims `OPTIONS_READY` before comparative design and recommendation;
- invents licence entitlements or prices.

## Pass signal

A strong response makes existing capability the first serious candidate while still allowing a different route to win if evidence justifies it.
