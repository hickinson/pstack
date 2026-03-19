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
6. Read the modules guide and relevant modules
7. Use the templates and checklists on a real task

## Usage path

Use this path when running a real task through pstack:

1. Start with `ai-operating-framework/TEMPLATES/TASK_BRIEF_TEMPLATE.md`
2. Create a plan with `ai-operating-framework/TEMPLATES/PLAN_TEMPLATE.md`
3. Invoke the relevant modules from `ai-operating-framework/MODULES/`
4. Review the output using `ai-operating-framework/CHECKLISTS/REVIEW_CHECKLIST.md`
5. Verify the output using `ai-operating-framework/CHECKLISTS/VERIFICATION_CHECKLIST.md`
6. Deliver or revise
7. Capture reusable learning if the task produced a useful pattern

## Minimum usable workflow

For v0.1, the default pstack workflow is:

**Brief → Plan → Build → Review → Verify → Deliver**

This is the minimum workflow pstack must support cleanly.

## Repository structure

```text
pstack/
├── README.md
└── ai-operating-framework/
    ├── DESIGN_PHILOSOPHY.md
    ├── OPERATING_MODEL.md
    ├── WORKFLOW_STAGES.md
    ├── QUALITY_GATES.md
    ├── ROLES_AND_BEHAVIOURS.md
    ├── PERSONAL_OVERLAY.md
    ├── PROFESSIONAL_OVERLAY.md
    ├── ENTERPRISE_ADAPTER.md
    ├── MODULES/
    ├── TEMPLATES/
    └── CHECKLISTS/