# Tasks specification

## Purpose

`TASKS.md` should help Codex improve the user's allocation of attention and
the execution of committed work. It must not create an ever-growing backlog or
confuse detectable work with worthwhile work.

## Required structure

`TASKS.md` must contain these top-level sections in this order. A section may
identify missing evidence or unresolved questions, but it should not be
silently omitted. Add subsections when they materially improve navigation.

### 1. Task goals

State what the user wants their task system to optimize for, including how it
should improve attention, outcomes, responsiveness, delegation, follow-through,
and control. Refer to current goals in `context/CONTEXT.md` rather than copying
them into this artifact.

### 2. Decision model

Define how the user turns signals and opportunities into decisions about
whether work should exist. Cover value, urgency, cost of delay, opportunity
cost, evidence, uncertainty, risk, reversibility, and the choices to do, defer,
delegate, reframe, or ignore.

### 3. Prioritization and commitments

Define how candidate work is compared, when it becomes a commitment, what must
be true before it displaces existing work, and how temporary urgency interacts
with durable goals. Include limits that prevent an unbounded backlog.

### 4. Ownership and delegation

Define how ownership is assigned among the user, other people, and Codex. Cover
delegation expectations, approval boundaries, escalation, follow-up, and what
must remain under human control.

### 5. Execution and completion

Define how committed work is framed, planned, executed, monitored, and closed.
Cover outcomes, constraints, dependencies, verification, and the distinction
between completing activity and achieving the intended result.

### 6. Systems and workflow

Identify the task systems the user actually uses, what each is authoritative
for, and how Galaga should interact with them. Store operating guidance and
boundaries here, not copied backlogs, credentials, or raw activity history.

### 7. Reviewed decisions and examples

Include a compact set of user-reviewed examples that expose useful task
judgment. Include enough context to explain why work was accepted, rejected,
deferred, delegated, reframed, corrected, reopened, or abandoned and what the
outcome taught.

### 8. Exceptions and open questions

Record material exceptions, conflicts, weakly supported patterns, and
questions that still need user review. Remove resolved items and update the
relevant section.

## Operating model

### Decide

For a signal, opportunity, or candidate task, help determine:

- whether work should exist;
- what outcome it should produce;
- which goal it advances and why it matters now;
- the opportunity cost and cost of delay;
- available evidence, uncertainty, risk, and reversibility;
- whether to do, defer, delegate, reframe, or ignore it; and
- whether responsibility belongs to the user, another person, or Codex.

### Act

For committed work, help plan and execute within the user's authority. Preserve
the intended outcome, owner, constraints, dependencies, and completion
criteria. Completion of activity is not proof that the intended outcome was
achieved.

## Lifecycle

```text
Signal or opportunity
→ Candidate task
→ Decision and prioritization
→ Committed task
→ Execution
→ Outcome and learning
```

Record useful feedback at decision, execution, and outcome stages. A rejected,
deferred, delegated, reframed, corrected, reopened, or abandoned task may be
more informative than a completed one.

## Quality criteria

A successful artifact is:

- **Complete:** every required section is present and covers the applicable
  minimums above or explicitly identifies what is not yet known.
- **Goal-aligned:** it improves allocation of attention toward intended
  outcomes without duplicating the user's current goals.
- **Selective:** it helps Codex decide when not to create work and prevents an
  ever-growing backlog.
- **Actionable:** it gives concrete decision and execution guidance rather than
  generic productivity advice.
- **Evidence-aware:** it distinguishes reviewed preferences, observed choices,
  outcomes, inference, uncertainty, and exceptions.
- **Current and navigable:** an agent can quickly find reliable guidance and
  identify stale material.
- **Safe:** it preserves the decide-and-act boundary, user control, external
  sources of truth, and approval requirements.

## Evaluation and repair

When the user's intent is to fix, clean up, improve, optimize, or otherwise
bring `TASKS.md` closer to this specification, first check that every required
section is present and that retained guidance is in the correct section.
Preserve supported personal meaning and reviewed examples while removing
duplication, stale guidance, copied operational state, unsupported rules, and
content that belongs in `CONTEXT.md`. Do not invent preferences to fill gaps;
mark material gaps or ask the user.

Then test whether a fresh agent makes better prioritization and routing
decisions, executes committed work more effectively, recognizes completion,
and avoids low-value activity. Use scenarios across the task lifecycle and
include rejected, deferred, delegated, reframed, reopened, and abandoned work,
not only successful completion.
