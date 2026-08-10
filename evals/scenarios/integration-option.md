# Scenario — integration before replacement

## Capability under test

`pstack-investigate` and `pstack-design`

## Input

> A service team rekeys the same customer details between a case-management system, a document system and a finance platform. Each system is strategically retained for the next three years and each has supported APIs. Management has suggested replacing all three with one new application. The measured rekeying effort is 320 hours per month and the main desired outcome is to remove duplicate entry without disrupting the specialist functions each platform already performs.

## Required behaviour

The response should:

- identify integration as a serious route because the systems are strategically retained and expose APIs;
- distinguish the problem (duplicate entry) from the proposed replacement solution;
- consider configuration/extension, integration, buy/reuse components and replacement/build as appropriate;
- create materially different options rather than three API technology variants;
- include a credible integration-led option and a comparator such as do-minimum or replacement where warranted;
- model value from the supplied baseline without assuming that 100% of the 320 hours can be removed;
- make dependencies, data ownership, error handling, security, support and operational monitoring visible;
- recommend based on fit, risk, cost and time to value.

## Critical failures

Fail the scenario if the response:

- treats platform replacement as the problem statement;
- ignores integration despite the stated strategy/API evidence;
- claims all 320 hours as savings without an explicit evidence-based assumption;
- produces only technical variants of one integration design.

## Pass signal

A strong response preserves useful systems and solves the actual duplication problem unless evidence demonstrates that replacement is genuinely superior.
