# pstack evaluations

These evaluations protect the distinctive behaviours of pstack without turning the repository into a model benchmark or brittle exact-output test suite.

They are deliberately scenario-and-rubric based.

## What the evals test

The evals ask whether pstack consistently:

- starts from the problem rather than the requested technology;
- refuses to invent missing baseline evidence;
- searches for configure, extend, integrate, buy and reuse routes before defaulting to bespoke build;
- creates materially different options and makes a recommendation;
- keeps commercial claims traceable to evidence, calculations and confidence;
- preserves human approval boundaries;
- leaves lifecycle state, owner, next action and checkpoint explicit;
- hands approved work into delivery without recreating the engineering process;
- accepts delivery hand-back and returns to benefit review;
- compares promised and actual outcomes before closing or iterating.

## Evaluation philosophy

### Judge behaviour, not prose

Do not require an exact answer or wording.

A response passes when the required behaviour is visible and the prohibited behaviour is absent.

### Use synthetic context

The scenarios contain invented organisations and figures. Do not put real client, employer or confidential information in this repository.

### Keep the model blind to the rubric

When running an eval manually, give the agent only the scenario's `Input` and any explicitly phased evidence at the point instructed.

The evaluator should use the remainder of the file as the rubric.

### Test a fresh interaction

Prefer a fresh session or clean context so previous conversation does not accidentally provide missing evidence or decisions.

### Reuse across hosts

The same scenario should be usable with any host that can run the relevant Agent Skill. Differences in formatting are acceptable; differences in method behaviour are not.

## Running an eval

1. Use the pstack version or branch being evaluated.
2. Make the relevant pstack skill available to the host.
3. Start from a clean interaction.
4. Provide only the scenario `Input` section.
5. Supply later evidence only when the scenario explicitly says to do so.
6. Allow current external research only when the scenario requires investigation of current products or capabilities.
7. Capture the resulting artefact and lifecycle state.
8. Score each required behaviour as pass or fail.
9. Treat any critical failure as an overall scenario failure.
10. Record method defects separately from model-specific presentation differences.

## Common critical failures

Unless a scenario says otherwise, these are critical:

- invented baseline values or fabricated evidence;
- treating a proposed technology as an already-proven requirement;
- recommending bespoke build without meaningful reuse investigation;
- using supplier marketing claims as the client's benefit case;
- presenting unsupported commercial numbers as facts;
- inferring human approval;
- advancing lifecycle state without satisfying its gate;
- leaving an active engagement without a truthful owner, next action or checkpoint;
- marking a solution `LIVE` without delivery hand-back and a benefit-review return path;
- closing without reviewing realised outcomes.

## Outcome labels

Use one of:

- **PASS** — the method behaved as intended;
- **PASS WITH FINDINGS** — the scenario completed correctly but exposed a method/documentation improvement worth making;
- **FAIL** — one or more critical behaviours were violated.

A pass is not proof that the prose is perfect. A failure is evidence that the method or its implementation needs attention.

## Automation

Do not build an eval harness yet.

Run these scenarios manually while the v2 method is still stabilising. Automate only when repeated runs show that the rubric and expected behaviours are stable enough to justify maintenance cost.
