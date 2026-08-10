---
name: pstack-investigate
description: Investigate how a baselined technology or process problem could be solved by searching for existing capability before bespoke build. Use when an engagement is BASELINED or INVESTIGATING and needs evidence on configure, extend, integrate, buy, reuse or build choices, including products, existing platforms, services, libraries, patterns and open source.
---

# pstack-investigate

Search before building.

## Goal

Establish credible solution routes using evidence, with particular discipline around reuse.

The output should make it difficult to recommend bespoke development merely because it was the first idea.

## Inputs

Use:

- completed discovery and baseline;
- known systems, platforms and contracts;
- security, compliance and data constraints;
- budget and timing realities;
- architecture or operating-model constraints;
- available internal capability.

If the problem is not sufficiently baselined to compare options meaningfully, return to `pstack-discover`.

## Investigation routes

Consider each route where relevant:

1. **CONFIGURE** — use capability already available with configuration only.
2. **EXTEND** — extend an existing platform or application.
3. **INTEGRATE** — connect existing systems or services.
4. **BUY** — acquire a suitable mature service or product.
5. **REUSE** — use trusted components, libraries, patterns or open source.
6. **BUILD** — create bespoke capability where justified.

This is not an absolute hierarchy.

A later route may be better because of:

- functional fit;
- security;
- compliance;
- licensing;
- lock-in;
- supportability;
- skills;
- integration complexity;
- data residency;
- total cost;
- strategic control.

## Method

### 1. Inventory what already exists

Look first at:

- current platforms and licences;
- capabilities already paid for;
- existing internal applications/services;
- integration capability;
- organisation-approved patterns and components;
- relevant products/services already in use.

### 2. Search externally where useful

Research current products, services, libraries, standards and mature open-source options when external evidence is needed.

Prefer authoritative and current sources for claims that can change.

Record what was searched rather than simply saying "research was done".

Treat vendor evidence carefully:

- vendor documentation can establish a product's claimed capability, supported integration, licensing rule or published price;
- vendor marketing, testimonials and case-study outcome claims do not establish the benefit that this engagement will realise;
- do not carry vendor productivity or ROI claims into the client business case without independent evidence or an explicit, clearly labelled assumption.

### 3. Assess candidates consistently

For each serious candidate, consider:

- fit to the problem;
- implementation effort;
- integration effort;
- security/compliance;
- licensing and commercial model;
- vendor/community maturity;
- lock-in;
- supportability;
- internal skills;
- recurring cost;
- delivery risk;
- material limitations.

### 4. Record rejected candidates

Rejection evidence matters.

Do not silently drop an apparently strong reuse route because bespoke development feels more flexible.

### 5. Build the bespoke case last

If bespoke capability is recommended, state why the better-looking configure/extend/integrate/buy/reuse candidates are inadequate.

"More control" is not enough on its own.

### 6. Hand findings to DESIGN

Use `assets/investigation.md`.

Do not turn investigation findings into three superficial variants of the same option. `pstack-design` owns the comparative solution design.

## Handoff to DESIGN

INVESTIGATE is complete when:

- relevant reuse routes have been considered;
- strong candidates and rejected candidates are evidenced;
- important risks and unknowns are visible;
- the information is sufficient to design materially different options.

When those conditions are met:

- keep the engagement at `INVESTIGATING`;
- set the next action to run `pstack-design`;
- set an appropriate design review date or event checkpoint.

`OPTIONS_READY` is earned only after `pstack-design` has compared materially different options and made a recommendation.

If the investigation is not complete, remain `INVESTIGATING` with a concrete investigation action and checkpoint.

## Lifecycle continuity

Do not finish INVESTIGATE while leaving engagement state implicit.

At the end of the work, determine and return:

- current state: normally `INVESTIGATING`;
- accountable owner;
- one concrete next action;
- one checkpoint: review date or triggering event.

If the project workspace is writable and pstack is operating on that project, update `.pstack/engagement.json`. If it cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.
