# Bootstrap context

## Purpose

Create the first useful `CONTEXT.md` from explicit user input and a bounded
review of relevant evidence. This is normally a one-time, manually triggered
job, but it must be safe to rerun intentionally.

## Inputs and boundaries

Before gathering context, establish:

- which areas of the user's life and work are in scope;
- which sources, people, or topics are excluded;
- what information is too sensitive or unnecessary to retain;
- which goals are current and which are merely possible; and
- the user's desired review depth.

Prefer a focused interview and representative evidence over exhaustive
collection. Retrieved material and intermediate analysis belong under
`.galaga/`, not in the durable artifact.

## Workflow

1. Read `CONTEXT-SPEC.md` and, if present, the current `CONTEXT.md`. Absence
   means context has not been bootstrapped.
2. Gather only information likely to improve communication or task decisions.
3. Separate facts, preferences, aspirations, inferred patterns, goals,
   constraints, relationships, systems, and uncertainty.
4. Remove unnecessary sensitive detail and avoid duplicating authoritative
   operational systems.
5. Present material interpretations and proposed goals to the user for
   correction, qualification, or rejection.
6. Create or update `CONTEXT.md` with endorsed durable context.
7. Evaluate the artifact against `CONTEXT-SPEC.md` and repair supported
   deficiencies without inventing context.

## Completion criteria

Bootstrap is complete when the user has reviewed consequential retained
context, uncertainty is visible, the artifact satisfies the specification,
and no private material has entered a framework file.
