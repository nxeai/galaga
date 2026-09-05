# Bootstrap context

## Purpose

Create the first useful `CONTEXT.md` from explicit user input and a bounded
review of relevant evidence. This is normally a one-time, manually triggered
job, but it must be safe to rerun intentionally.

## Inputs and boundaries

Establish these progressively during the interview rather than presenting them
as an up-front checklist or approval bundle:

- which areas of the user's life and work are in scope;
- which sources, people, or topics are excluded;
- what information is too sensitive or unnecessary to retain;
- which goals are current and which are merely possible; and
- the user's desired review depth.

Prefer a focused interview and representative evidence over exhaustive
collection. Retrieved material and intermediate analysis belong under
`.galaga/`, not in the durable artifact.

Invoking the bootstrap job is permission to begin the interview. It is not
permission to retrieve external data, access a new source, or write
`CONTEXT.md`. Ask for those permissions only when they become relevant and
concrete.

## Interaction model

Bootstrap is a guided conversation, not a configuration prompt.

- Briefly explain that Galaga will build the context one section at a time,
  show a complete draft for review, and write nothing until the user approves.
- Ask exactly one focused question per turn. A question may invite a natural
  answer but should not contain a long questionnaire or multiple unrelated
  decisions.
- Use each answer to choose the next best question. Ask a follow-up when an
  important ambiguity remains; otherwise move to the next area.
- Keep acknowledgements short. Do not repeatedly print the accumulated draft
  or make the user approve every individual fact.
- Let the user say that something is unknown, irrelevant, private, or better
  retrieved later. Do not force every detail to be populated.
- Do not ask the user to design `CONTEXT.md`; translate the conversation into
  the structure required by `CONTEXT-SPEC.md`.

When no context artifact exists, a useful opening is:

> I'll build your Galaga context with you one section at a time, then show you
> the complete draft before anything is saved. I won't pull from external
> sources unless we decide together that it would help.
>
> Let's start with your job: what is your current role, and what are you
> responsible for?

Adapt the wording naturally, but start collecting useful context in the first
turn. Do not ask a single yes-or-no question that combines scope, sources,
sensitivity, and permission to write.

## Workflow

1. Read `CONTEXT-SPEC.md` and, if present, the current `CONTEXT.md`. Absence
   means context has not been bootstrapped. If it exists, do not overwrite it;
   explain that bootstrap would rebuild it and confirm that this is the user's
   intent before continuing.
2. If the artifact is absent, give the brief orientation above and immediately
   ask the first useful question. Do not ask for general permission to proceed.
3. Interview the user one focused question at a time. Move through Job, Goals,
   People, Tools and systems, and Boundaries and standing context in a natural
   order. Gather enough to make each section useful, not every conceivable
   detail.
4. Synthesize Snapshot after the substantive sections are understood. Track
   unresolved consequential gaps under Open questions rather than extending
   the interview indefinitely.
5. Throughout the interview, separate facts, preferences, aspirations,
   inferred patterns, goals, constraints, relationships, systems, and
   uncertainty. Remove unnecessary sensitive detail and avoid duplicating
   authoritative operational systems.
6. If external evidence would materially improve a section, explain the
   specific source and benefit and ask permission at that point. Continue from
   user answers alone if the user declines.
7. Assemble a complete draft using every required section from
   `CONTEXT-SPEC.md`. Present the draft in the conversation and ask the user
   what they want corrected, qualified, removed, or added.
8. Revise the draft until the user endorses its consequential content. Then
   ask for explicit permission to write the reviewed draft to
   `context/CONTEXT.md`.
9. After approval, write the personal artifact and evaluate it against
   `CONTEXT-SPEC.md`. Repair only supported deficiencies; do not invent context
   or retrieve new data during finalization.
10. Report completion and offer one small, real task where the new context can
    immediately improve a decision or action.

## Completion criteria

Bootstrap is complete when the user has reviewed consequential retained
context, explicitly approved writing the draft, uncertainty is visible, the
artifact satisfies the specification, and no private material has entered a
framework file. Starting the interview, collecting answers, or presenting a
draft is progress, not completion.
