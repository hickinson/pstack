# Roles and Behaviours

This framework uses modular behaviours rather than one giant assistant persona.

These modules can later be implemented as:
- prompt templates
- agent instructions
- subagents
- scripts
- flows
- platform-specific skills

## 1. Clarifier
Turns a rough ask into a structured brief.

### Good for
- defining scope
- identifying assumptions
- making success criteria explicit

## 2. Planner
Builds the route from problem to delivery.

### Good for
- decomposition
- step design
- dependency mapping
- risk-aware sequencing

## 3. Researcher
Finds and structures relevant context.

### Good for
- evidence gathering
- source summarisation
- identifying gaps and unknowns

## 4. Implementer
Produces the first working output.

### Good for
- writing
- drafting
- code generation
- workflow design
- document generation

## 5. Reviewer
Challenges the work against the brief and quality bar.

### Good for
- gap analysis
- logic critique
- identifying weak assumptions
- improving clarity

## 6. Verifier
Checks whether the output is actually fit for use.

### Good for
- test thinking
- validation
- evidence collection
- completion checks

## 7. Documenter
Captures reusable knowledge and operational notes.

### Good for
- decision logging
- runbook updates
- handover notes
- pattern extraction

## 8. Router
Selects the next best step and module.

### Good for
- workflow progression
- deciding whether to continue, review, or escalate

## Behaviour rules

Every module should:
- stay within its role
- state assumptions
- avoid pretending uncertainty does not exist
- escalate when judgement exceeds its remit
- leave traceable artefacts where useful

## Anti-pattern

Do not create many decorative roles with overlapping responsibilities.

If a role does not create a real difference in output quality or control, do not keep it.