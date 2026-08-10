---
name: pstack-learn
description: Review a live pstack solution against its original business case by comparing estimated and actual cost, duration, recurring cost, adoption and benefits, explaining variance and separating project-specific lessons from reusable pstack method improvements. Use when an engagement reaches BENEFIT_REVIEW or when deciding whether a live solution should close or iterate.
---

# pstack-learn

Test whether the promised value survived contact with reality.

This is a benefit and solution-lifecycle review, not a generic engineering retrospective.

## Inputs

Use:

- original discovery baseline;
- approved proposal;
- implementation handoff;
- delivery hand-back;
- actual operational and benefit evidence;
- stakeholder/user feedback where relevant.

Do not rely on memory of what was promised when the source artefacts exist.

## Method

### 1. Reconstruct the original business case

Identify:

- expected implementation cost;
- expected delivery duration;
- expected recurring cost;
- expected benefits;
- material assumptions;
- expected adoption or operating change.

### 2. Capture actuals

Use real evidence where available for:

- delivery cost/effort;
- duration;
- recurring cost;
- adoption;
- usage;
- process performance;
- benefit measures;
- operational/support impact.

Mark unavailable actuals as unknown rather than backfilling convenient estimates.

### 3. Calculate variance

Compare estimated and actual measures consistently.

Do not treat variance as failure by default.

Explain:

- what changed;
- why;
- whether the original assumption was weak;
- whether delivery changed;
- whether external conditions changed;
- whether the measurement itself is limited.

### 4. Review benefits

Assess whether the original benefit mechanism occurred.

For example, if the proposal assumed:

```text
10 minutes saved × 5,000 cases
```

check both:

- whether approximately 10 minutes was actually saved;
- whether the affected case volume was actually around 5,000.

### 5. Review adoption and operations

A technically live solution may not realise benefits if:

- people do not use it;
- workarounds remain;
- support burden is higher than expected;
- upstream/downstream processes did not change;
- quality fell;
- measurement was not instrumented.

Make those effects visible.

### 6. Capture learning

Separate:

**Project-specific learning**
- facts that belong only to this client, service or delivery.

**Reusable method learning**
- generic lessons that could improve future pstack discovery, investigation, design, proposal or handoff.

Do not move client-specific information into the public pstack repository.

### 7. Decide close or iterate

Use `assets/benefit-review.md`.

Recommend:

- `CLOSED` when the review is complete and no further change is currently justified; or
- `ITERATE` when additional change is justified.

If iterating, identify the correct re-entry action rather than automatically restarting discovery.

## Lifecycle continuity

Do not finish LEARN while leaving engagement state implicit.

During an active review, keep the state at `BENEFIT_REVIEW` with an owner, next action and checkpoint.

When the review is complete:

- use `CLOSED` when no further change is currently justified; or
- use `ITERATE` when further change is justified, with a concrete re-entry action and checkpoint.

If the project workspace is writable and pstack is operating on that project, update `.pstack/engagement.json`. If it cannot be updated safely, return the exact state-file values that should be written.

The user should not have to remember to invoke `pstack-manage` merely to preserve lifecycle continuity.

## Output quality

A good benefit review makes it possible to answer:

- Did we deliver what was approved?
- Did it cost what we expected?
- Did it take as long as expected?
- Did ongoing cost match expectations?
- Did people adopt it?
- Did the expected benefit occur?
- Which assumptions failed?
- What should we do differently next time?
- Should this engagement close or iterate?
