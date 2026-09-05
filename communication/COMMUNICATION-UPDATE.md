# Update communication

## Purpose

Improve `COMMUNICATION.md` from new evidence, user feedback, and changing
goals while preserving its usefulness, provenance, and user-approved intent.
This job may be triggered manually or on a user-approved schedule.

## Evidence

Strong evidence includes:

- explicit user corrections or declared goals;
- the difference between a Codex draft and the user's final version;
- whether the user used, rejected, reframed, or abandoned a recommendation;
- user-authored communication in a previously underrepresented context; and
- outcomes or recipient responses when they are available and relevant.

Repeated behavior is not necessarily desired behavior. Received messages are
not evidence of the user's voice. Keep retrieved content and intermediate
analysis under `.galaga/`; retrieve incrementally and reuse valid cached
material.

## Workflow

1. Read `COMMUNICATION-SPEC.md` and the current `COMMUNICATION.md`. If the
   personal artifact is absent, stop and recommend the bootstrap job instead.
2. Review only new or newly relevant evidence since the prior run when
   possible.
3. Identify material gaps, contradictions, stale guidance, changed goals, and
   opportunities to make the artifact more useful or compact.
4. Determine whether each candidate change is isolated, contextual, broadly
   durable, or still uncertain.
5. Propose the smallest useful set of changes. Explain the evidence and the
   expected effect on future behavior.
6. Propose additions, replacements, or removals of authoritative writing
   samples when warranted.
7. Ask the user to accept, reject, edit, or narrow meaningful changes and
   sample selections. Batch review to respect the user's attention.
8. Apply approved changes without erasing supported nuance or user-authored
   guidance.
9. Re-evaluate the full artifact against `COMMUNICATION-SPEC.md`.
10. Summarize what changed, why, and what remains uncertain.

It is valid and often desirable for a run to make no change. Evidence
collection may run quietly, but new authoritative samples require user review.

## Forgetting and deletion

If the user removes evidence, distinguish among deleting the cached copy,
excluding future retrieval, disconnecting the source, and reconsidering
guidance derived from that evidence. Do not claim that Galaga has forgotten
something while derived guidance remains authoritative.

## Completion criteria

An update is complete when:

- meaningful changes have received user review;
- every applied change is supported by an explicit goal or appropriate
  evidence;
- the artifact remains compact, navigable, and internally coherent;
- the result satisfies `COMMUNICATION-SPEC.md`; and
- the run reports a change, a justified no-op, or a clearly stated unresolved
  question.
