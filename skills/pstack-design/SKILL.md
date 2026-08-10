---
name: pstack-design
description: Create and compare materially different solution options for a baselined, investigated technology problem, model cost, benefit, risk and support implications, challenge assumptions, and make a best-fit recommendation. Use after reuse-first investigation when an engagement needs decision-ready options rather than implementation detail.
---

# pstack-design

Create real choices, then recommend.

## Goal

Turn discovery and investigation evidence into decision-ready solution options with commercially useful trade-offs.

## Inputs

Use:

- discovery and baseline;
- investigation findings;
- relevant architecture, security and operating constraints;
- cost and benefit evidence;
- material unknowns.

If investigation has not meaningfully considered existing capability and reuse, return to `pstack-investigate`.

## Method

### 1. Define the decision

State the decision being made and the criteria that actually matter.

Do not optimise for a technology preference that has not been justified.

### 2. Create materially different options

Options should differ meaningfully in one or more of:

- reuse level;
- operating model;
- product/service choice;
- architecture;
- scope;
- implementation approach;
- cost/risk profile;
- time to value;
- strategic control.

Three technical variants of the same approach are not three options unless their trade-offs are genuinely material.

Include "do minimum / improve existing" or "do nothing now" when it is a credible comparator.

### 3. Model costs

Distinguish where relevant:

- implementation;
- licences/consumption;
- integration/migration;
- training/change;
- recurring platform/service;
- recurring support.

Use ranges when uncertainty is material.

For material cost estimates, make the basis and confidence visible. Prefer a published price, supplier quote, rate × effort calculation, comparable delivery evidence or another inspectable basis over an unsupported number.

### 4. Model benefits

Ground benefits in discovery evidence.

A useful general pattern is:

```text
baseline × affected volume × expected improvement × unit value = estimated benefit
```

For each material benefit, show:

- baseline/current condition;
- reasoning or calculation;
- assumptions;
- source;
- measurement period;
- confidence.

Do not force every benefit into money where another measure is more meaningful.

### 5. Compare risk and supportability

Consider:

- delivery complexity;
- security/compliance;
- change/adoption;
- dependency risk;
- vendor/community risk;
- lock-in;
- operational ownership;
- support capability;
- technical debt.

### 6. Recommend

Choose the best-fit option and explain why.

Also explain why the apparently strongest alternatives do not win.

State what new evidence would cause the recommendation to change.

## Output

Use `assets/solution-options.md`.

Do not create the client proposal yet. `pstack-propose` owns proposal packaging and the approval/handoff boundary.

## Exit condition

`OPTIONS_READY` requires:

- materially different options where warranted;
- visible cost, benefit, risk, assumptions and confidence;
- an explicit recommendation;
- enough evidence for a defensible client proposal.

If those conditions are not met, define the next investigation/design action instead.

## Lifecycle continuity

Do not finish DESIGN while leaving engagement state implicit.

At the end of the work, determine and return:

- `OPTIONS_READY` when the exit condition is met, otherwise the truthful earlier state;
- accountable owner;
- one concrete next action, normally `pstack-propose` when ready;
- one checkpoint: review date or triggering event.

If the project workspace is writable and pstack is operating on that project, update `.pstack/engagement.json`. If it cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.
