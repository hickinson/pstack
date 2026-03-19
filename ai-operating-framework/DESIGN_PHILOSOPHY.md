# Design Philosophy

## Core proposition

AI should be used through a structured operating model rather than through ad hoc prompting.

The framework is built on the belief that the most durable advantage comes from:
- explicit workflow
- modular behaviours
- reusable artefacts
- evidence-based completion
- human judgement at decision boundaries
- portability across tools

## Design principles

### 1. Workflow first
Design around the recurring stages of work, not around individual prompts or tools.

### 2. One core, multiple overlays
The core operating logic should stay stable. Different contexts should adapt it without breaking it.

### 3. Tool-agnostic centre, tool-aware edges
Put principles, templates, and behaviours in files. Put vendor-specific details at the edge.

### 4. Human judgement at the boundary
AI can help frame, plan, draft, review, and verify. Humans remain accountable for sensitive judgement and final sign-off where needed.

### 5. Evidence before completion
A task is not done because the AI says so. It is done when the output has passed the relevant quality, review, and verification gates.

### 6. Keep it lean
The framework should help real work move. It should not become a bureaucratic layer that users work around.

### 7. Earn automation
Only turn a pattern into an automation when it has proven repeatable, bounded, and valuable.

## Design constraints

This framework intentionally avoids:
- giant master prompts
- too many agents
- heavy governance in personal use
- brittle dependence on one platform
- fake autonomy
- unnecessary complexity presented as sophistication

## Practical intent

This framework should help with:
- planning and decomposition
- research and context handling
- repeatable drafting
- review and verification
- documentation and handover
- safer adaptation into professional and enterprise settings

## Future direction

Later versions may add:
- tool adapters
- MCP integration profiles
- approval routing
- logging patterns
- platform mappings

Those should be added only after the core workflow proves useful in practice.