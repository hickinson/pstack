# pstack

pstack is a portable AI operating framework for structuring work in a more repeatable, AI-native, and tool-agnostic way.

It is designed to help turn ad hoc prompting into a practical workflow that can be used across personal work, professional work, and more constrained enterprise environments over time.

## What pstack is

pstack is:
- a workflow-first operating framework
- a lightweight repository of reusable patterns for AI-assisted work
- a portable core with context-specific overlays
- a practical system for moving from idea to delivery with clearer structure, review, and verification
- a foundation for future tool-specific adapters without being trapped inside one tool

## What pstack is not

pstack is not:
- a giant prompt library
- a monolithic autonomous agent system
- a tool-specific framework
- a replacement for human judgement
- a reason to add process where none is needed
- a complete enterprise governance model

## The v0.1 backbone

These files form the real operating spine of pstack v0.1:

1. `ai-operating-framework/DESIGN_PHILOSOPHY.md`
2. `ai-operating-framework/OPERATING_MODEL.md`
3. `ai-operating-framework/WORKFLOW_STAGES.md`
4. `ai-operating-framework/QUALITY_GATES.md`
5. `ai-operating-framework/TEMPLATES/TASK_BRIEF_TEMPLATE.md`
6. `ai-operating-framework/TEMPLATES/PLAN_TEMPLATE.md`
7. `ai-operating-framework/CHECKLISTS/REVIEW_CHECKLIST.md`
8. `ai-operating-framework/CHECKLISTS/VERIFICATION_CHECKLIST.md`

If pstack works in practice, it will be because these files work together.

## Reading path

Use this reading path if you are new to pstack:

1. `ai-operating-framework/DESIGN_PHILOSOPHY.md`
2. `ai-operating-framework/OPERATING_MODEL.md`
3. `ai-operating-framework/WORKFLOW_STAGES.md`
4. `ai-operating-framework/QUALITY_GATES.md`
5. Choose the relevant overlay:
   - `ai-operating-framework/PERSONAL_OVERLAY.md`
   - `ai-operating-framework/PROFESSIONAL_OVERLAY.md`
   - `ai-operating-framework/ENTERPRISE_ADAPTER.md`
6. Read `ai-operating-framework/MODULES/README.md`
7. Use the templates and checklists on a real task

## Usage path

Use this path when running a real task through pstack:

1. If starting with a rough idea, use `ai-operating-framework/TEMPLATES/IDEA_CAPTURE_TEMPLATE.md`
2. Refine the idea with `ai-operating-framework/MODULES/IDEA_PROCESSOR.md`
3. Decide whether the work belongs in the discovery lane or the build lane
4. If the work is still exploratory, use discovery templates such as:
   - `ai-operating-framework/TEMPLATES/CURRENT_STATE_ASSESSMENT_TEMPLATE.md`
   - `ai-operating-framework/TEMPLATES/OPPORTUNITY_REGISTER_TEMPLATE.md`
   - `ai-operating-framework/TEMPLATES/PROPOSAL_RECOMMENDATION_TEMPLATE.md`
5. If the task is already clear enough to execute, create a task brief with `ai-operating-framework/TEMPLATES/TASK_BRIEF_TEMPLATE.md`
6. Create a plan with `ai-operating-framework/TEMPLATES/PLAN_TEMPLATE.md`
7. Invoke the relevant modules from `ai-operating-framework/MODULES/`
8. Review the output using `ai-operating-framework/CHECKLISTS/REVIEW_CHECKLIST.md`
9. Verify the output using `ai-operating-framework/CHECKLISTS/VERIFICATION_CHECKLIST.md`
10. Deliver or revise
11. Capture reusable learning if the task produced a useful pattern

## Minimum usable workflows

For v0.1, pstack now supports two practical lanes:

### Discovery lane

**Idea → Assess → Register → Recommend → Decide**

Use this when the work is still exploratory and you need to understand the current state, capture opportunities, and form a recommendation before delivery work begins.

### Build lane

**Idea → Brief → Plan → Build → Review → Verify → Deliver**

Use this when the task is already clear enough to define, plan, and execute.

If the task is already clear, you can skip the idea step and start at the brief.

## Repository structure

```text
pstack/
├── README.md
└── ai-operating-framework/
    ├── DESIGN_PHILOSOPHY.md
    ├── OPERATING_MODEL.md
    ├── WORKFLOW_STAGES.md
    ├── QUALITY_GATES.md
    ├── PERSONAL_OVERLAY.md
    ├── PROFESSIONAL_OVERLAY.md
    ├── ENTERPRISE_ADAPTER.md
    ├── MODULES/
    │   ├── README.md
    │   └── *.md
    ├── TEMPLATES/
    │   └── *.md
    └── CHECKLISTS/
        └── *.md
```

## Essential for v0.1

These matter most right now:

- `ai-operating-framework/DESIGN_PHILOSOPHY.md`
- `ai-operating-framework/OPERATING_MODEL.md`
- `ai-operating-framework/WORKFLOW_STAGES.md`
- `ai-operating-framework/QUALITY_GATES.md`
- `ai-operating-framework/TEMPLATES/TASK_BRIEF_TEMPLATE.md`
- `ai-operating-framework/TEMPLATES/PLAN_TEMPLATE.md`
- `ai-operating-framework/CHECKLISTS/REVIEW_CHECKLIST.md`
- `ai-operating-framework/CHECKLISTS/VERIFICATION_CHECKLIST.md`
- the core module files in `ai-operating-framework/MODULES/`

## Secondary for v0.1

These are useful, but not part of the tightest operating spine:

- `ai-operating-framework/TEMPLATES/DELIVERY_TEMPLATE.md`
- `ai-operating-framework/TEMPLATES/DECISION_LOG_TEMPLATE.md`
- `ai-operating-framework/TEMPLATES/CURRENT_STATE_ASSESSMENT_TEMPLATE.md`
- `ai-operating-framework/TEMPLATES/OPPORTUNITY_REGISTER_TEMPLATE.md`
- `ai-operating-framework/TEMPLATES/PROPOSAL_RECOMMENDATION_TEMPLATE.md`
- `ai-operating-framework/CHECKLISTS/PROFESSIONAL_SAFETY_CHECKLIST.md`
- `ai-operating-framework/CHECKLISTS/WEEKLY_OPERATING_RHYTHM.md`
- deeper use of `ai-operating-framework/ENTERPRISE_ADAPTER.md`
- more advanced documentation and capture patterns

## Current v0.1 focus

The goal of v0.1 is not to expand pstack.

The goal is to make it:
- coherent
- opinionated
- usable in day-to-day work
- portable across tools
- simple enough to evolve through real usage

## Design stance

pstack follows a few strong rules:

- workflow first
- durable principles over tool tricks
- one core, multiple overlays
- modules as reusable behaviours
- evidence before completion
- human judgement at meaningful boundaries
- simplification over documentation theatre

## How pstack should evolve

pstack should evolve through real use.

That means:
- test it on real tasks
- identify friction
- simplify where needed
- only add structure that proves its value
- defer tool-specific adapters until the portable core is stable

## Current status

pstack is being tightened into a coherent v0.1 framework.

The current priority is:
1. clarify the backbone
2. reduce overlap
3. improve navigation
4. make the minimum workflow clean
5. test it on real work