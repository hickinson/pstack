# Scenario — delivery return path

## Capabilities under test

`pstack-manage` and `pstack-learn`

This scenario tests the lifecycle after pstack has handed an approved solution to normal delivery tooling.

## Starting input

> The engagement is `IMPLEMENTATION_READY` on 10 February 2030. The approved solution is a native-first workflow automation pilot. The implementation handoff is complete. Approved assumptions are £18k–£24k implementation cost, 6–8 weeks delivery, £4k annual recurring cost and an expected 35–45% reduction in 580 hours/month of processing effort. The accountable business owner is Alex Morgan. Delivery owner is Sam Patel.

### Phase 1 — delivery accepts

Tell pstack:

> On 10 February 2030, Sam Patel accepted delivery ownership. The delivery repository and backlog are established and implementation starts now.

Required behaviour:

- permit `IMPLEMENTATION_READY → BUILDING`;
- retain Alex Morgan as accountable business owner while recording delivery ownership appropriately;
- set a delivery-related next action/checkpoint rather than losing pstack state during build;
- avoid duplicating the engineering backlog inside pstack.

### Phase 2 — solution goes live

Then provide:

> The pilot went live on 31 March 2030 after 7 weeks. Actual implementation cost was £22,500 and expected recurring cost is £4,400/year. Testing and acceptance evidence exists in the delivery repository. One low-priority reporting feature was deferred with business-owner agreement. Operational owner is Jordan Lee. Measurement is live for processing time, adoption and exception rate. Set the benefit review for 12 May 2030, six weeks after go-live.

Required behaviour:

- require/use the delivery hand-back rather than treating deployment alone as sufficient;
- capture actual cost, duration, scope deviation, acceptance evidence references, operational ownership and measurement availability;
- permit `BUILDING → LIVE` only once the hand-back conditions are satisfied;
- establish the 12 May 2030 benefit-review checkpoint immediately;
- leave state as `LIVE`, not `CLOSED`;
- make the checkpoint visible enough that a host with native reminder/task capability could surface or schedule it without changing the portable state contract.

Critical failure:

- `LIVE` without a benefit-review checkpoint or usable measurement path.

### Phase 3 — review date reached

At the checkpoint provide:

> It is 12 May 2030. Average processing effort is now 365 hours/month, adoption is 88%, exception/rework rate is slightly better than baseline and there has been no material increase in support burden. The measurement sample is considered reliable.

Required behaviour:

- permit `LIVE → BENEFIT_REVIEW` because the checkpoint has been reached and actual evidence exists;
- compare the approved expectation with actual outcomes;
- calculate that processing effort fell by 215 hours/month, approximately 37% against the 580-hour baseline;
- report that £22,500 implementation cost and 7-week duration are within the approved ranges;
- report recurring cost as £400/year, or 10%, above the £4,000 estimate;
- review adoption and the deferred scope item rather than looking only at time saved;
- avoid claiming cashable savings unless the business case and evidence support that interpretation.

## Outcome A — close

Then tell pstack:

> The business owner confirms the result is satisfactory, the deferred reporting feature is not currently worth further investment and no additional change is requested.

Required behaviour:

- recommend `CLOSED`;
- capture project-specific learning;
- identify any genuinely reusable pstack-method learning separately;
- not require an artificial next action/checkpoint after closure.

## Outcome B — iterate

Run the review again from Phase 3, but instead tell pstack:

> Adoption is only 52% in one acquired agency because its local workflow differs materially. The group wants to address that gap before rolling the pattern out further.

Required behaviour:

- recommend `ITERATE`, not pretend the original implementation failed everywhere;
- identify the correct re-entry action based on the new evidence rather than automatically restarting the whole lifecycle;
- for this variant, treat fresh local discovery as a credible re-entry because the local workflow materially differs;
- allow `ITERATE → DISCOVERY` only when DISCOVERY truthfully represents the next work, rather than treating `ITERATE` as a bypass around lifecycle gates;
- set an accountable owner, concrete next action and checkpoint;
- preserve the successful evidence from the first implementation rather than discarding it.

## Critical failures

Fail the scenario if pstack:

- moves to `BUILDING` without delivery acceptance;
- moves to `LIVE` from deployment status alone;
- loses the benefit-review checkpoint;
- closes immediately after go-live;
- reviews benefits from memory rather than approved/actual evidence;
- treats a partial adoption problem as proof that the whole solution should be rebuilt;
- leaves `ITERATE` without owner, action and checkpoint;
- leaves `ITERATE` stranded with no valid way to re-enter the lifecycle.

## Pass signal

A strong result demonstrates that pstack genuinely leaves delivery alone while maintaining enough lifecycle continuity to resume ownership, verify the business case and either close cleanly or iterate from evidence.
