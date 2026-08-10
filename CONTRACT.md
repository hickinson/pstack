# pstack v2 Contract

This document is the authoritative design contract for pstack v2.

If another repository artefact conflicts with this contract, this contract takes precedence.

## 1. Purpose

**pstack is an AI-assisted technology solution lifecycle system that turns poorly defined problems into evidence-based, commercially credible and implementable solution proposals; hands approved solutions cleanly into delivery; and then verifies whether the promised benefits were actually realised.**

It is intended primarily for technology-led process improvement through software, applications, systems configuration, automation, AI, data, integration and related operating-model changes that save time, reduce cost, improve quality or enable new value.

## 2. Governing principles

- Problem before solution.
- Search before building.
- Reuse before reinventing.
- Evidence before assertion.
- Options before commitment.
- Recommend rather than merely list.
- Measure before promising.
- Handoff before implementation.
- Verify after shipping.
- Learn before repeating.
- Human accountability for consequential decisions.
- Prefer simple, inspectable and portable mechanisms over bespoke infrastructure.

## 3. Scope

pstack is a solution-lifecycle method, not a generic AI framework.

It helps an engagement move from a vague problem or opportunity to an approved and implementable solution, then returns after delivery to test whether the promised outcomes were achieved.

It may be used for:

- software and application improvement;
- configuration of existing platforms;
- systems integration;
- automation and AI;
- data and analytics solutions;
- operating-model changes coupled to technology;
- buying or reusing suitable products, services, libraries, patterns or open source.

## 4. Delivery boundary

pstack owns:

```text
DISCOVER → INVESTIGATE → DESIGN → PROPOSE → HANDOFF
```

It delegates:

```text
BUILD → TEST → SHIP
```

to the project's normal technical environment.

That environment may include VS Code, GitHub, Copilot, Codex, Claude Code, gstack or other suitable delivery tooling.

pstack then resumes ownership for:

```text
BENEFIT REVIEW → LEARN
```

pstack must therefore define both:

- proposal → implementation handoff;
- delivery → pstack hand-back.

## 5. Information boundary

**pstack contains methods. Projects contain context. Credential stores contain access.**

The public pstack repository contains only generic reusable methods, schemas, templates, examples, tests and portable adapters.

Client, employer and project-specific information belongs in the appropriate project, repository or workspace.

Secrets and credentials do not belong in pstack.

## 6. Lifecycle

The authoritative lifecycle is:

```text
IDEA → DISCOVERY → BASELINED → INVESTIGATING → OPTIONS_READY → PROPOSAL
     → APPROVED → IMPLEMENTATION_READY → BUILDING → LIVE
     → BENEFIT_REVIEW → CLOSED / ITERATE
```

### Lifecycle meanings

- **IDEA** — a problem, opportunity or proposed solution has been captured but not yet explored.
- **DISCOVERY** — the problem and current state are being understood.
- **BASELINED** — sufficient evidence exists to describe the current state and meaningful measures.
- **INVESTIGATING** — existing capabilities, products, integrations and reusable components are being examined.
- **OPTIONS_READY** — materially different options have been compared and a recommendation exists.
- **PROPOSAL** — a client-quality proposition exists and awaits a decision.
- **APPROVED** — an accountable human has explicitly approved the selected approach.
- **IMPLEMENTATION_READY** — the approved solution has an actionable technical handoff.
- **BUILDING** — delivery has accepted ownership and implementation is underway.
- **LIVE** — the solution is in use and delivery has handed actual results back to pstack.
- **BENEFIT_REVIEW** — actual outcomes are being compared with the business case.
- **CLOSED** — the engagement has completed and no further iteration is currently justified.
- **ITERATE** — further change is justified and the engagement has an explicit re-entry action.

## 7. Capability contracts

### DISCOVER

Purpose: turn a vague client problem or opportunity into a well-framed, evidence-seeking current-state assessment and baseline.

DISCOVER must:

- accept raw ideas directly;
- separate the problem from any suggested solution;
- identify affected people, processes, systems and outcomes;
- establish what is known versus assumed;
- seek evidence about the current state;
- establish a meaningful baseline where possible;
- expose missing evidence rather than inventing it;
- define measurable desired outcomes.

DISCOVER must not declare an engagement `BASELINED` when material baseline evidence is still absent.

### INVESTIGATE

Purpose: establish what already exists and what can be configured, extended, integrated, bought or reused before bespoke build is considered.

Every material investigation should consider, as appropriate:

1. Configure what already exists.
2. Extend an existing platform.
3. Integrate existing systems or services.
4. Buy a suitable mature service or product.
5. Reuse trusted components, libraries, patterns or open source.
6. Build bespoke capability only where justified.

This is not an absolute hierarchy. Security, fit, licensing, lock-in, supportability, operating model and total cost may justify a different choice.

A bespoke-build recommendation without meaningful evidence that alternatives were considered is incomplete.

### DESIGN

Purpose: create materially different solution options and recommend the best-fit approach.

DESIGN must:

- carry forward the discovery baseline and investigation findings;
- produce materially different options where warranted;
- compare cost, benefit, risk, complexity, dependencies and support implications;
- make assumptions visible;
- express confidence honestly;
- recommend an option rather than merely listing choices;
- state what evidence could change the recommendation.

Variations of the same technical approach do not count as materially different options unless the trade-offs are genuinely different.

### PROPOSE

Purpose: convert the reasoning into a commercially credible and technically implementable proposition.

PROPOSE must:

- retain traceability to evidence and baseline;
- describe options considered and the recommended approach;
- express delivery and ongoing costs;
- express expected value with visible assumptions and confidence;
- define scope, exclusions, risks, dependencies and responsibilities;
- require explicit human approval before moving to `APPROVED`;
- create a technical implementation handoff after approval.

PROPOSE must never self-approve a consequential decision.

### MANAGE

Purpose: keep the engagement healthy and enforce lifecycle boundaries.

MANAGE must:

- maintain current lifecycle state;
- ensure every active engagement has an accountable owner;
- ensure every active engagement has a non-empty next action;
- ensure every active engagement has an event trigger or review date;
- validate material lifecycle transitions;
- enforce the human approval boundary;
- confirm delivery acceptance at implementation handoff;
- accept delivery hand-back;
- create the benefit-review checkpoint when the solution goes live.

An active engagement without a next checkpoint is unhealthy.

### LEARN

Purpose: compare the business case with actual outcomes and improve future work.

LEARN must compare, where available:

- estimated versus actual implementation cost;
- estimated versus actual duration;
- estimated versus actual recurring cost;
- expected versus actual benefit;
- expected versus actual adoption and operating impact;
- material assumptions versus reality.

Project or client-specific learning stays with the project.

Only generic, reusable method learning should become a candidate change to pstack itself.

## 8. Engagement state and health

The minimum project-side state mechanism is a repository-native file, normally:

```text
.pstack/engagement.json
```

For every active engagement, it must contain:

- `schema_version`;
- `engagement_id`;
- `title`;
- `state`;
- `owner`;
- `next_action`;
- `checkpoint`;
- `updated_at`.

`checkpoint` must identify either:

- a review date; or
- an event that should trigger the next review or transition.

`CLOSED` is the only state that does not require an active next action and checkpoint.

Git history provides historical change tracking. pstack does not require a database or separate state service for the MVP.

## 9. Lifecycle transition rules

The normal transitions are:

```text
IDEA → DISCOVERY
DISCOVERY → BASELINED
BASELINED → INVESTIGATING
INVESTIGATING → OPTIONS_READY
OPTIONS_READY → PROPOSAL
PROPOSAL → APPROVED
APPROVED → IMPLEMENTATION_READY
IMPLEMENTATION_READY → BUILDING
BUILDING → LIVE
LIVE → BENEFIT_REVIEW
BENEFIT_REVIEW → CLOSED
BENEFIT_REVIEW → ITERATE
```

Transition criteria:

- **IDEA → DISCOVERY** — active discovery starts.
- **DISCOVERY → BASELINED** — sufficient evidence exists for meaningful investigation and benefit reasoning.
- **BASELINED → INVESTIGATING** — reuse-first investigation starts.
- **INVESTIGATING → OPTIONS_READY** — viable materially different options have been compared and a recommendation exists.
- **OPTIONS_READY → PROPOSAL** — a client-quality proposal exists.
- **PROPOSAL → APPROVED** — explicit, attributable human approval only.
- **APPROVED → IMPLEMENTATION_READY** — the implementation handoff is complete enough for delivery to act without reconstructing the proposal conversation.
- **IMPLEMENTATION_READY → BUILDING** — delivery accepts ownership.
- **BUILDING → LIVE** — the solution is live and delivery hand-back is complete.
- **LIVE → BENEFIT_REVIEW** — the agreed review trigger or date has been reached.
- **BENEFIT_REVIEW → CLOSED** — review is complete and no further iteration is currently justified.
- **BENEFIT_REVIEW → ITERATE** — further change is justified.

`ITERATE` deliberately has no single hard-coded next state. Its next action should identify the correct re-entry point based on what was learned.

## 10. Evidence and confidence discipline

pstack should consistently distinguish:

- **OBSERVED** — directly witnessed or measured.
- **SOURCED** — supported by an identifiable source.
- **ESTIMATED** — calculated or forecast from stated inputs.
- **ASSUMED** — treated as true for planning but not yet evidenced.
- **UNKNOWN** — material information that is not yet known.

Where estimates affect a recommendation or business case, confidence should be expressed explicitly, normally as:

- low;
- medium;
- high.

Confidence is not a substitute for evidence.

## 11. Commercial modelling discipline

Benefits should be grounded in a baseline where appropriate.

A useful general pattern is:

```text
baseline × affected volume × expected improvement × unit value = estimated benefit
```

Not every benefit is financial, but every material claim should identify:

- baseline or current condition;
- calculation or reasoning;
- source;
- assumptions;
- confidence;
- measurement period.

Costs should distinguish where relevant:

- implementation;
- licences or consumption;
- integration and migration;
- training and change;
- ongoing platform or service cost;
- ongoing support.

Use ranges when uncertainty is material. Do not invent precision.

## 12. Human accountability

AI may assist with framing, investigation, design, commercial modelling, drafting, review and verification.

A named human remains accountable for consequential decisions.

Explicit human approval is required before a proposal moves from `PROPOSAL` to `APPROVED`.

Sensitive actions involving money, people, legal or regulatory impact, security, service outcomes, restricted data or material reputation require proportionate human judgement and appropriate organisational controls.

## 13. Explicit non-goals

pstack v2 must not:

- create a coding-agent platform;
- recreate gstack;
- build a giant prompt library;
- create a monolithic master prompt;
- create a bespoke UI;
- add MCP by default;
- introduce a database in the MVP;
- automate consequential human approvals away;
- claim benefits without appropriate baseline or evidence;
- duplicate native planning, coding, review, test or release capability without a demonstrated gap.

## 14. Evolution rule

pstack should evolve through real engagements.

Add structure only when repeated use demonstrates a clear need.

Prefer:

1. native capability;
2. open standards;
3. repository-native formats;
4. reusable methods;
5. boring technology.

Automation must be earned by a pattern that is repeatable, bounded, useful and safe.
