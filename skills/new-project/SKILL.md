---
name: new-project
description: Assist a user in creating a lean project with build, measure, and learn tasks
---

# New Build-Measure-Learn Project Skill

A detailed workflow that leads a user through the set-up of a new BML project. Each
project is structured as a Directed Acyclic Graph (DAG) of iterative loops — each
loop is a snapshot in time, with directed edges flowing Build → Measure → Learn and
then into the next loop's Build stage.

Guide the user through the following steps interactively, asking one section at a time.

---

## Step 1: Project Name and Hypothesis

Ask the user for:
- A short project name
- The core **hypothesis** the project is testing — what assumption or patron/staff need
  is being addressed?

Remind them: a good hypothesis is explicit and testable. The Learn step will confirm
or refute it. (OODA analogy: this is the Orient → Decide moment before the first loop.)

---

## Step 2: Build Phase — Minimum Viable Product (MVP)

Help the user define the MVP. Ask:

1. **What is the minimum functionality** needed for patrons or staff to meaningfully
   interact with the service? Warn against scope creep — the MVP must be lean enough
   to release quickly but complete enough not to alienate users with a rough experience.

2. **Who will build it?** Options to surface:
   - Internal library staff or librarians
   - Third-party vendor or open-source product (with trial period)
   - AI coding agents (e.g., Claude Code, GitHub Copilot)
   - A combination of the above

3. **API and integration needs**: Does the MVP need to connect to existing library
   systems? Note relevant API styles: RESTful (GET/PUT/POST/DELETE), OpenAPI spec,
   streaming formats (RSS, ActivityPub), or linked-data (RDF/JSON-LD/Turtle).

4. **Metrics instrumentation**: Before leaving the Build phase, confirm the MVP will
   be able to *capture* the metrics identified in Step 3. Suggest privacy-respecting
   analytics (Plausible, Matomo) over commercial options (Google Analytics) as more
   aligned with library values.

Produce a bulleted **Build task list** for the user to confirm before moving on.

---

## Step 3: Measure Phase — Actionable Metrics

Help the user identify actionable metrics — measurements that directly test the
hypothesis from Step 1. Warn explicitly about **vanity metrics** (e.g., raw visitor
counts) that feel good but don't reveal whether patron needs are being met.

Ask:

1. **What specific patron or staff interactions** should be tracked? (Examples: time
   to complete a task, successful search completions, checkout rates, workflow
   step durations.)

2. **Does the workflow span multiple departments?** If so, identify the overall
   end-to-end metric (e.g., total ordering-to-shelf time) *and* per-step metrics so
   bottlenecks can be found.

3. **Demand source differentiation**: Is the pull coming from patron-initiated
   requests or automated acquisition plans? Patron-initiated requests should be
   prioritized in the metrics.

4. **Andon-style alerting**: Should staff be notified if a workflow step exceeds a
   time threshold? If so, note the notification channel (email, Slack, etc.).

5. **If evaluating a vendor product**: Structure the trial period as a single BML
   iteration. Confirm whether the vendor's product will expose the metrics needed to
   test their marketing claims.

Produce a bulleted **Measure task list** (metrics to collect, tools, owner) for
the user to confirm.

---

## Step 4: Learn Phase — Analysis and Next Iteration

Help the user plan how they will analyze results and capture organizational knowledge.

Ask:

1. **Who will review the metrics?** (library staff, administration, patrons)
   Remind the user that communicating results clearly — including context and
   narrative — is part of the Learn step, not a follow-on activity.

2. **Decision criteria**: What outcome would cause a *minor tweak* to the MVP vs.
   a *major pivot*? Inconclusive metrics are not failure — they signal the hypothesis
   needs refinement before the next loop.

3. **Organizational memory**: How will the lessons from this loop be documented and
   shared with others in the library? The goal is diffusing tacit knowledge into
   explicit, reusable form.

4. **Next loop**: What is the updated hypothesis going into BML Loop 2? Confirm that
   the Learn output feeds directly into the next Build stage.

Produce a bulleted **Learn task list** (analysis, communication, documentation,
next hypothesis draft) for the user to confirm.

---

## Step 5: Project Summary

Produce a structured project summary:

```
Project: <name>
Hypothesis: <statement>

BML Loop 1
  Build:
    - <task list>
  Measure:
    - <metric> | <tool/method> | <owner>
  Learn:
    - <analysis task> | <owner>
    - Communication plan: <audience, format>
    - Organizational memory: <how captured>
    - Next hypothesis: <draft>
```

Ask the user if they want to save this to a file or open a tracking issue.
