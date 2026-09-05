# Tasks specification

## Status

This is a provisional specification. It captures the decisions made so far
without fixing a detailed task model before real use.

## Purpose

`TASKS.md` should help Codex improve the user's allocation of attention and
the execution of committed work. It must not create an ever-growing backlog or
confuse detectable work with worthwhile work.

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

## Initial quality criteria

A successful artifact should be goal-aligned, evidence-aware, selective,
actionable, current, and honest about uncertainty. It should clarify the
boundary between deciding and acting, preserve external systems as their own
sources of truth, and help Codex know when not to create work.

The eventual behavioral evaluation should test whether a fresh agent makes
better prioritization and routing decisions, executes committed work more
effectively, and avoids low-value activity. Detailed criteria remain to be
battle-tested and refined.
