# pstack

pstack is an AI-assisted technology solution lifecycle system that turns poorly defined problems into evidence-based, commercially credible and implementable solution proposals; hands approved solutions cleanly into delivery; and verifies whether the promised benefits were actually realised.

## Start here

If you have a raw idea, client request, pain point, opportunity or proposed technology solution, start with **`pstack-discover`**.

Do not hunt through prompts or templates first. The skill should help separate the real problem from the proposed solution, establish what is known, expose missing evidence and create the first useful engagement artefact.

## Lifecycle

```text
IDEA → DISCOVERY → BASELINED → INVESTIGATING → OPTIONS_READY → PROPOSAL
     → APPROVED → IMPLEMENTATION_READY → BUILDING → LIVE
     → BENEFIT_REVIEW → CLOSED / ITERATE
```

Every active engagement must visibly record:

- current lifecycle state;
- next action;
- accountable owner;
- event trigger or review date.

An active engagement without a next checkpoint is unhealthy.

The lifecycle is stable, but the depth of analysis and artefacts is proportional to consequence, uncertainty, cost and stakeholder complexity. Proportionality reduces ceremony; it does not bypass gates.

## Six capabilities

### DISCOVER

Turn a vague problem or opportunity into a well-framed, evidence-seeking current-state assessment and baseline.

### INVESTIGATE

Establish what already exists and what can be configured, extended, integrated, bought or reused before bespoke build is considered. Reuse candidates must be assessed for fit and inherited debt rather than assumed suitable merely because they already exist.

### DESIGN

Create materially different solution options, model benefits, costs and risks, challenge assumptions and recommend the best-fit approach.

### PROPOSE

Convert the reasoning into a decision-quality, technically implementable proposition whose commercial depth is proportionate to the engagement, followed by a clean implementation handoff when explicitly approved.

### MANAGE

Maintain lifecycle state, enforce handoff gates, ensure next actions and checkpoints exist, accept delivery hand-back and trigger benefit reviews.

### LEARN

Compare estimated or expected outcomes with actual delivery cost, time, adoption and benefit where material, explain variance and retain lessons that improve future work.

## Delivery boundary

pstack owns:

```text
DISCOVER → INVESTIGATE → DESIGN → PROPOSE → HANDOFF
```

It delegates:

```text
BUILD → TEST → SHIP
```

to the project's normal technical environment, such as VS Code, GitHub, Copilot, Codex, Claude Code and/or gstack where useful.

pstack then resumes ownership for:

```text
BENEFIT REVIEW → LEARN
```

pstack does not recreate a coding-agent platform or software factory.

## Information boundary

**pstack contains methods. Projects contain context. Credential stores contain access.**

This public repository contains only generic reusable methods, schemas, templates, examples and behavioural evaluations.

Client, employer and project-specific information belongs in the relevant project, repository or workspace. Secrets do not belong in pstack.

## Engagement state

Projects using pstack should keep a small repository-native state record, normally:

```text
.pstack/engagement.json
```

`pstack-manage` owns the state contract and lifecycle-transition rules.

No database, bespoke UI or MCP dependency is required for the MVP.

## Agent Skills

pstack is expressed as six portable Agent Skills:

```text
skills/
├── pstack-discover/
├── pstack-investigate/
├── pstack-design/
├── pstack-propose/
├── pstack-manage/
└── pstack-learn/
```

Each skill encodes a distinctive pstack method rather than a generic AI persona. Supporting templates or reference material live with the skill that owns them.

See [`docs/USING_PSTACK.md`](docs/USING_PSTACK.md) for practical usage and host placement guidance.

## Evaluation

`evals/` contains small synthetic scenario-and-rubric tests for the behaviours pstack must preserve, including problem framing, reuse-before-build, commercial evidence, proportionality, state continuity and the delivery return path.

They are behavioural regression checks rather than exact-output tests. Run them manually while the method is still stabilising; automate only when repeated use proves the rubric is stable enough to justify an eval harness.

See [`evals/README.md`](evals/README.md).

## Governing contract

[`CONTRACT.md`](CONTRACT.md) is the authoritative pstack design contract.

## Repository structure

```text
pstack/
├── README.md
├── CONTRACT.md
├── skills/
│   ├── pstack-discover/
│   ├── pstack-investigate/
│   ├── pstack-design/
│   ├── pstack-propose/
│   ├── pstack-manage/
│   └── pstack-learn/
├── evals/
│   ├── README.md
│   └── scenarios/
└── docs/
    └── USING_PSTACK.md
```

Git history is the archive for superseded designs; the active tree contains only the current method.

## Design stance

pstack deliberately prefers:

- problem before solution;
- search before building;
- reuse before reinventing, with fit and inherited debt assessed explicitly;
- evidence before assertion;
- options before commitment;
- recommendation rather than mere listing;
- proportional rigour rather than fixed ceremony;
- measurement before promising;
- handoff before implementation;
- verification after shipping;
- learning before repeating;
- human accountability for consequential decisions;
- repository-native state and boring technology over unnecessary infrastructure.
