# Operating Model

## Overview

This framework has four layers:

1. Portable core
2. Personal overlay
3. Professional overlay
4. Enterprise-safe adapter concept

The same core workflow should remain recognisable across all four.

## 1. Portable core

The portable core contains:
- design philosophy
- operating model
- workflow stages
- roles and behaviours
- quality gates
- reusable templates
- reusable checklists

The core should stay durable and largely tool-agnostic.

## 2. Personal overlay

The personal overlay adapts the core for:
- experimentation
- side projects
- writing
- coding
- prototyping
- rapid iteration

It should stay light and fast.

## 3. Professional overlay

The professional overlay adapts the core for:
- explainability
- consistency
- safer practice
- better documentation
- clearer approval boundaries

It should be more structured, but still practical.

## 4. Enterprise-safe adapter concept

The enterprise adapter is not a separate framework.

It is a translation layer for more constrained environments where:
- tools are approved
- actions are bounded
- access is governed
- data boundaries matter
- logging and approvals may be required

## Integration concept

The framework assumes that tools sit below the operating model.

This means:
- prompts are replaceable
- tools are replaceable
- specific platforms are replaceable
- the workflow remains the same even when the implementation changes

## MCP position

MCP belongs in the integration layer as a portable capability adapter.

### Personal
MCP can be used more loosely for experimentation and capability extension.

### Professional
MCP should be scoped to approved use cases and documented patterns.

### Enterprise
MCP should be tightly governed, capability-scoped, auditable where needed, and wrapped through approved adapters.

## Universal rule

Reasoning, drafting, planning, review, and verification may be AI-assisted.

Final accountability, sensitive judgement, and high-risk actions should remain explicitly human-controlled unless formal governance says otherwise.