---
description: Construct a new BML iteration for an existing Lean project that just finished a previous BML iteration
---

# Next Build-Measure-Learn Iteration Skill

Help the user plan the next iteration of an existing BML project. In the DAG model,
each iteration is a new graph — the Learn outputs of the previous loop become the
directed inputs to this loop's Build stage. The prior loop's nodes are in the past
and cannot be changed; this iteration starts fresh with updated hypotheses.

Guide the user through the following steps interactively, one section at a time.

---

## Step 1: Review the Previous Loop

Before planning anything new, establish what the previous iteration produced. Ask:

1. **What loop number is this?** (e.g., BML Loop 2, Loop 3)

2. **What hypothesis was tested in the previous loop?** Was it confirmed, refuted,
   or were the results inconclusive? Remind the user that inconclusive results are not
   failure — they signal the question or measurement approach needs refinement.

3. **What were the key actionable metrics collected?** Ask the user to distinguish
   between metrics that actually tested the hypothesis vs. any vanity metrics
   (e.g., raw visitor counts) that crept in.

4. **What did the Learn step conclude?** Summarize:
   - What worked and should be carried forward
   - What needs minor tweaking
   - Whether a **pivot** (significant change in direction) or **persevere**
     (continue with adjustments) decision was made

5. **What organizational knowledge was captured and shared?** The Learn step should
   have diffused lessons beyond the immediate project team — confirm this happened
   or flag it as a task for this iteration's Learn step.

---

## Step 2: Updated Hypothesis for This Loop

Based on the previous loop's Learn outputs, help the user draft a refined hypothesis.

- If the prior hypothesis was **confirmed**: the new hypothesis should extend or
  deepen the validated assumption — what's the next unknown to test?
- If the prior hypothesis was **refuted**: the new hypothesis should reflect the
  pivot — what different assumption does the new direction test?
- If results were **inconclusive**: the new hypothesis may be the same but with
  better-defined measurement criteria.

The hypothesis must remain explicit and testable. The Learn step of this loop will
again confirm or refute it.

---

## Step 3: Build Phase — Incremental MVP Changes

Help the user define what changes to make to the MVP this iteration. Ask:

1. **What specific changes does the pivot or persevere decision require?**
   - Minor tweaks (UI polish, additional fields, performance improvements)
   - Significant changes (new architecture, new technology, new workflow)
   - A full pivot (e.g., from a standalone app to a plugin within an existing platform)

2. **Does the platform choice still fit?** Revisit whether the current technology
   is a pull platform (loosely coupled, API-first, easy to iterate on) or if friction
   in the previous loop suggests reconsidering the stack.

3. **Are there new API or integration requirements** introduced by the pivot or new
   hypothesis? (RESTful, OpenAPI, streaming feeds, linked-data formats)

4. **Metrics instrumentation for this loop**: Are the measurement gaps identified
   in the previous Learn step addressed in this build? Poor metric coverage in the
   prior loop is a Build task, not just a Measure task.

Produce a bulleted **Build task list** scoped to changes from the prior MVP.

---

## Step 4: Measure Phase — Refined Metrics

Based on lessons from the prior Measure step, help the user sharpen the metrics plan.

Ask:

1. **Which metrics from the previous loop are carried forward?** Which are dropped
   because they proved to be vanity metrics or were superseded?

2. **What new actionable metrics does the updated hypothesis require?** Be specific:
   what patron or staff interaction, at what granularity, with what threshold signals
   success or failure?

3. **Were there measurement gaps in the prior loop?** (e.g., log parsing workarounds,
   missing instrumentation, vendor refusing to share data) — address these explicitly
   in this iteration's Build tasks.

4. **Andon-style alerting**: Should any workflow step thresholds be adjusted based on
   what was learned, or are new alerting rules needed?

5. **Demand source differentiation**: Has the balance of patron-initiated vs.
   automated pull changed? Adjust metric priorities accordingly.

Produce a bulleted **Measure task list** (metric, tool/method, owner, success threshold).

---

## Step 5: Learn Phase — Planning the Analysis

Help the user plan how this loop's results will be analyzed and communicated.

Ask:

1. **Who needs to see the results of this loop?** Has the audience expanded (e.g.,
   library administration, a vendor, other departments) based on what was learned?

2. **What are the pivot/persevere criteria for this loop?** Make them explicit before
   the loop runs so the decision isn't made post-hoc.

3. **How will the knowledge from this loop be captured and diffused?**  
   Remind the user: the goal is not just evaluating this project but making tacit
   knowledge explicit so others in the library can remix and reapply it.

4. **Draft the hypothesis for BML Loop N+1.** Even if preliminary, sketching
   the next question keeps the DAG moving forward.

Produce a bulleted **Learn task list** (analysis, communication, documentation,
next hypothesis draft).

---

## Step 6: Iteration Summary

Produce a structured summary for this loop:

```
Project: <name>
BML Loop: <N>

Prior Loop Outcome:
  Hypothesis: <was it confirmed / refuted / inconclusive>
  Decision: <pivot / persevere>
  Key lessons: <bullet points>

BML Loop <N> Plan
  Updated Hypothesis: <statement>

  Build:
    - <change or new task>

  Measure:
    - <metric> | <tool/method> | <owner> | <success threshold>

  Learn:
    - <analysis task> | <owner>
    - Communication plan: <audience, format>
    - Organizational memory: <how captured>
    - Next hypothesis (Loop <N+1> draft): <statement>
```

Ask the user if they want to save this to a file or open a tracking issue.
