# Using pstack

pstack is intended to be used from the project, repository or workspace that contains the real engagement context.

The pstack repository contains reusable methods. It should not become the store for client-specific material.

## Start from the problem

For a new engagement, start with `pstack-discover`.

A direct invocation can be as simple as:

```text
Use pstack-discover on this:

A recruitment group is buying agencies and thinks AI could help standardise
and streamline their operations.
```

If the host supports automatic Agent Skill discovery, describing the raw problem naturally may be enough to trigger the skill.

You should not have to locate and complete a separate idea-capture form before discovery can begin.

## Suggested project-side layout

Keep the active state small and machine-readable:

```text
project/
└── .pstack/
    └── engagement.json
```

Keep substantive lifecycle artefacts with the project's other documentation, for example:

```text
project/
├── .pstack/
│   └── engagement.json
└── docs/
    └── pstack/
        ├── discovery.md
        ├── investigation.md
        ├── solution-options.md
        ├── proposal.md
        ├── implementation-handoff.md
        ├── delivery-handback.md
        └── benefit-review.md
```

This is a convention, not a required repository framework. Adapt paths when the project already has an established documentation structure.

## Create artefacts progressively

Do not create seven empty documents at engagement start.

Create an artefact when the lifecycle reaches the point where it is useful:

| State/capability | Typical artefact |
|---|---|
| DISCOVERY / BASELINED | `discovery.md` |
| INVESTIGATING | `investigation.md` |
| OPTIONS_READY | `solution-options.md` |
| PROPOSAL | `proposal.md` |
| APPROVED / IMPLEMENTATION_READY | `implementation-handoff.md` |
| LIVE | `delivery-handback.md` |
| BENEFIT_REVIEW | `benefit-review.md` |

The engagement state should always identify what happens next even when no new document is needed.

## Skill sequence

The normal solution path is:

```text
pstack-discover
      ↓
pstack-investigate
      ↓
pstack-design
      ↓
pstack-propose
      ↓
implementation handoff
      ↓
normal delivery environment
      ↓
delivery hand-back
      ↓
pstack-learn
```

Each lifecycle skill must leave the engagement state truthful and usable. When the project workspace is writable, the skill should create or update `.pstack/engagement.json`; otherwise it should return the exact state values that need to be written.

This keeps current state, accountable owner, next action and checkpoint from being lost between capabilities.

`pstack-manage` is cross-cutting, but it is not a mandatory extra ceremony between every lifecycle skill. Use it when you need to:

- create, inspect or repair engagement state explicitly;
- check lifecycle health;
- validate a disputed or consequential transition;
- record or verify approval;
- hand work to delivery;
- accept delivery hand-back;
- establish or repair a benefit-review checkpoint.

## Delivery is deliberately external

After `IMPLEMENTATION_READY`, use the project's normal engineering and delivery tools.

That may include:

- VS Code;
- GitHub;
- GitHub Copilot;
- OpenAI Codex;
- Claude Code;
- gstack;
- existing CI/CD and testing tools.

Do not copy their coding, review, QA or release capabilities into pstack unless repeated use demonstrates a real lifecycle gap.

## Agent Skill placement

The canonical source lives under this repository's `skills/` directory.

When using a host that supports the open Agent Skills format, install or copy the required pstack skill into the host's supported skill location.

Common project-level locations include:

```text
.github/skills/
.agents/skills/
.claude/skills/
```

Host conventions evolve. Prefer the current native mechanism of the tool you are using rather than adding a pstack-specific installer in the MVP.

A skill should remain self-contained: its `SKILL.md` plus any owned `assets/` or `references/`.

## Evidence and project context

Store evidence where it naturally belongs in the project.

For example:

- source documents stay in the client/project document store;
- code stays in the delivery repository;
- issues and PRs stay in GitHub;
- credentials stay in credential stores;
- decision and solution artefacts can link to those sources.

Avoid copying large evidence packs into pstack lifecycle documents.

## Engagement health

For any state other than `CLOSED`, `.pstack/engagement.json` should contain:

- owner;
- next action;
- checkpoint.

A checkpoint is either:

```json
{
  "type": "review_date",
  "value": "2026-08-17"
}
```

or:

```json
{
  "type": "event",
  "value": "Client supplies process-volume data"
}
```

If one of those elements is missing, use `pstack-manage` to repair the engagement before adding more process.

## Human approval

The AI may prepare and challenge the proposal.

It may not infer the transition:

```text
PROPOSAL → APPROVED
```

That transition requires explicit human approval attributable to an accountable person.

## Working with sensitive engagements

Use the security, data, access and approval controls of the client or employer environment.

pstack does not weaken those controls and does not make an external integration acceptable merely because an AI tool can technically access it.

Use least privilege and minimise data shared with AI systems.

## Finishing the loop

Going live is not the end of a pstack engagement.

Delivery should hand actual implementation information back, and the engagement should immediately have a benefit-review checkpoint.

The benefit review then asks:

- Did it cost what we expected?
- Did it take as long as expected?
- Did people adopt it?
- Did the expected benefit materialise?
- Which assumptions failed?
- What should future work do differently?

Close the engagement only when that learning has been captured or further iteration is not currently justified.
