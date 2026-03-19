# Workflow Stages

This framework uses one universal workflow.

Not every task needs the same depth, but every meaningful task should follow this shape.

## Stage 1: Intake
Capture the raw request, idea, or problem.

### Output
- a rough task record

## Stage 2: Clarify
Turn the rough ask into a defined task.

### Output
- objective
- constraints
- inputs
- outputs
- success criteria
- assumptions

## Stage 3: Classify
Determine the operating context and risk.

### Classify by context
- personal
- professional
- enterprise-adapted

### Classify by risk
- low
- medium
- high

### Output
- chosen overlay
- required controls

## Stage 4: Plan
Break the work into steps.

### Output
- plan
- sequence
- dependencies
- risks
- validation approach

## Stage 5: Gather context
Retrieve the minimum useful context needed to do good work.

### Output
- evidence pack
- source notes
- open questions

## Stage 6: Execute
Create the draft, artefact, analysis, design, code, or workflow.

### Output
- working output

## Stage 7: Review
Critique the output against the brief and the framework standards.

### Output
- review findings
- required revisions
- risks or gaps

## Stage 8: Verify
Produce evidence that the output is fit for purpose.

### Output
- checks run
- evidence recorded
- issues found or cleared

## Stage 9: Approve or escalate
Where needed, a human approves, requests revision, or escalates.

### Output
- approved
- revise
- escalate

## Stage 10: Deliver
Prepare the final output for use, handover, or publication.

### Output
- final artefact
- summary
- handover note where needed

## Stage 11: Capture learning
Record what should become reusable.

### Output
- decision note
- pattern
- improvement idea
- future automation candidate

## Compression rule

Small personal tasks may compress stages 1 to 6 into one pass.

Professional and enterprise work should make stages 3, 7, 8, and 9 more explicit.

---

## Minimum usable workflow (v0.1)

For most tasks, pstack uses a simplified execution flow:

**Brief → Plan → Build → Review → Verify → Deliver**

This is the default operating loop.

Not every task requires every stage, but meaningful work should not skip:
- review
- verification

---

## Mapped files

Each stage maps directly to files in the repository.

### Brief
Define the task clearly:
- `TEMPLATES/TASK_BRIEF_TEMPLATE.md`
- optionally use `MODULES/CLARIFIER.md`

---

### Plan
Decide how the task will be executed:
- `TEMPLATES/PLAN_TEMPLATE.md`
- optionally use `MODULES/PLANNER.md`

---

### Build
Produce the output:
- `MODULES/IMPLEMENTER.md`
- optionally supported by:
  - `MODULES/RESEARCHER.md`
  - `MODULES/ROUTER.md`

---

### Review
Critically assess the output:
- `MODULES/REVIEWER.md`
- `CHECKLISTS/REVIEW_CHECKLIST.md`

---

### Verify
Confirm correctness and validity:
- `MODULES/VERIFIER.md`
- `CHECKLISTS/VERIFICATION_CHECKLIST.md`

---

### Deliver
Package or share the output:
- `TEMPLATES/DELIVERY_TEMPLATE.md` (if needed)

---

## Practical execution loop

In practice, work is rarely linear.

You will often loop between stages:

- Brief ↔ Clarify
- Plan ↔ Adjust
- Build ↔ Research
- Review ↔ Improve
- Verify ↔ Rework

This is expected.

The goal is not rigid sequence.

The goal is:
- clarity of intent
- structured execution
- deliberate review
- explicit verification

---

## When to use the full stage model

The full set of workflow stages is useful when:

- work is complex
- multiple stakeholders are involved
- traceability is important
- the task spans multiple iterations

For simple tasks, use the minimum workflow.

---

## Key principle

Do not expand the workflow for the sake of completeness.

Use the simplest version that maintains:
- clarity
- quality
- confidence in the result