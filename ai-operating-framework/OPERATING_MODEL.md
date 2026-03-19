# Operating Model

This file explains how pstack is structured and how to use it in practice.

It is the bridge between the design philosophy and real execution.

---

## Purpose

The purpose of the operating model is to:

- define how the repository is organised
- explain how work moves through the system
- distinguish between what is read and what is used
- make the framework usable, not just understandable

---

## The five layers of pstack

pstack is organised into five layers.

Each layer has a distinct role.

| Layer | Purpose | Used when |
|------|--------|----------|
| Core | Defines principles and structure | Read at the start and revisited occasionally |
| Overlays | Adapts the framework to context | Chosen per task |
| Modules | Reusable AI behaviours | Invoked during work |
| Templates | Working artefacts | Used to define and structure tasks |
| Checklists | Quality and safety controls | Used before completion |

---

## Core

The core defines how pstack works.

Files:
- DESIGN_PHILOSOPHY.md
- WORKFLOW_STAGES.md
- QUALITY_GATES.md

The core should remain:
- tool-agnostic
- stable over time
- focused on durable principles

---

## Overlays

Overlays adapt the core for different contexts.

Files:
- PERSONAL_OVERLAY.md
- PROFESSIONAL_OVERLAY.md
- ENTERPRISE_ADAPTER.md

Overlays define:
- how strict the process should be
- what level of governance is required
- how tools and integrations should be used

---

## Modules

Modules are reusable behaviours.

They represent repeatable ways of using AI to perform parts of work.

Examples:
- Clarifier
- Planner
- Implementer
- Reviewer
- Verifier

Modules:
- are portable
- are not tied to any one tool
- can be invoked manually or later implemented as agents

Each module defines:
- when to use it
- what inputs it expects
- what outputs it produces
- a default invocation pattern

---

## Templates

Templates create working artefacts.

They are used to structure work before and during execution.

Examples:
- Task brief
- Plan
- Review record
- Delivery output

Templates ensure:
- work is not purely conversational
- decisions are made explicit
- outputs are structured and reusable

---

## Checklists

Checklists act as control points.

They are used to prevent:
- premature completion
- hidden assumptions
- unverified outputs

Examples:
- task start checklist
- review checklist
- verification checklist

Checklists should be:
- lightweight
- used consistently
- focused on decision quality, not bureaucracy

---

## How work moves through pstack

Work flows through the system in stages.

The detailed stages are defined in `WORKFLOW_STAGES.md`.

For practical use, pstack v0.1 uses a simplified flow:

**Brief → Plan → Build → Review → Verify → Deliver**

---

## Minimum usable workflow

For most tasks, the following flow is sufficient:

1. Create a task brief  
   → `TEMPLATES/TASK_BRIEF_TEMPLATE.md`

2. Create a plan  
   → `TEMPLATES/PLAN_TEMPLATE.md`

3. Execute using modules  
   → `MODULES/*`

4. Review the output  
   → `MODULES/REVIEWER.md`  
   → `CHECKLISTS/REVIEW_CHECKLIST.md`

5. Verify the output  
   → `MODULES/VERIFIER.md`  
   → `CHECKLISTS/VERIFICATION_CHECKLIST.md`

6. Deliver or revise  

This is the core operating loop.

---

## What is read vs what is used

Not all files are used in the same way.

### Read occasionally
- DESIGN_PHILOSOPHY.md
- OPERATING_MODEL.md
- WORKFLOW_STAGES.md
- QUALITY_GATES.md
- overlays

### Used regularly
- TEMPLATES/*
- MODULES/*
- CHECKLISTS/*

If the framework is working correctly, most time is spent in:
- templates
- modules
- checklists

---

## Portability

pstack is designed to be portable.

This means:

- no dependency on a single tool
- modules can be invoked in any AI interface
- templates can be used in any environment
- integrations (such as MCP) sit outside the core

Tool-specific implementations should be treated as adapters, not the framework itself.

---

## Evolution approach

pstack should evolve through use, not theory.

This means:

- start with the minimum workflow
- run real tasks through the system
- identify friction
- simplify before adding complexity
- only add structure that proves useful

The goal is not completeness.

The goal is usability and durability.