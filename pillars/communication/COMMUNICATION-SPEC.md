# Communication specification

## Purpose

`COMMUNICATION.md` should enable a fresh Codex agent, given the artifact and
the immediate situation, to make communication choices that closely match the
user's judgment and to produce writing the user can use with minimal
substantive editing.

It represents both the user's authentic voice and the way the user intends to
communicate. Past behavior is evidence; it is not automatically the target.

This specification defines fitness for purpose, not a required document
outline. `COMMUNICATION.md` may reorganize as the user and the available
evidence evolve.

## Operating model

Communication has two distinct modes.

### Decide

Help determine:

- the outcome the user wants;
- whether communication is the right action;
- the recipient, medium, visibility, and timing;
- what the recipient should understand, feel, decide, or do;
- what belongs in the communication and what should be omitted;
- the relevant risks, sensitivities, uncertainties, and competing goals; and
- whether the agent needs clarification or authorization.

The option set may include not communicating, waiting, gathering evidence,
changing medium, communicating privately, asking a question, holding a live
conversation, or separating immediate and systemic concerns.

### Act

Once a strategy is chosen, help produce the appropriate artifact for the
medium. The result should use suitable structure, tone, length, directness,
polish, factual precision, and uncertainty while advancing the selected goal.

Drafting, sending, publishing, and commenting are separate levels of
authority. Guidance about style never grants authority for an external action.

## Inputs and conditioning

Guidance must help an agent reason across combinations of:

- **Goal:** for example, build trust, show empathy, drive a decision, create
  urgency, challenge an assumption, or repair a relationship.
- **Medium:** for example, email, Slack or chat, document comment, pull-request
  review, durable document, or live conversation.
- **Relationship:** for example, subordinate, superior, peer, internal
  customer, external customer, candidate, or investor.
- **Situation:** including history, urgency, stakes, sensitivity, visibility,
  ambiguity, and organizational context.

Avoid an exhaustive matrix of rules. Provide principles, distinctions, and
examples that let an agent resolve combinations intelligently.

When sources disagree, use this priority:

1. The goal for the current communication and explicit current instructions.
2. Facts and immediate context.
3. Declared communication aspirations.
4. Established communication principles.
5. Observed historical tendencies.
6. Generic defaults.

## Decision procedure

For consequential communication, the artifact should support this process:

1. Gather enough materially relevant input to frame the decision.
2. Generate meaningfully different strategic options.
3. Analyze likely outcomes and tradeoffs.
4. Stress-test and refine the leading option through a bounded number of
   purposeful passes.
5. Recommend a strategy, surface material uncertainty, and then act within
   the user's authority.

The number and depth of refinement passes should be proportional to stakes,
ambiguity, novelty, and reversibility. Useful lenses include outcome,
recipient interpretation, downside risk, alignment with the user's leadership
goals, and simplification. Low-risk communication should not expose or impose
heavy deliberation unnecessarily.

## Writing samples

The artifact must include a compact, high-value set of explicit writing
samples. Samples convey tacit judgment and voice that rules alone cannot.

Authoritative samples must be reviewed by the user. They may be authentic
user writing or material the user has edited into an endorsed form. A sample
should carry enough context to understand its goal, medium, relationship, and
the behavior it demonstrates.

Useful samples may include:

- examples the user endorses as authentic;
- examples that represent an aspirational communication behavior;
- before-and-after revisions that expose a meaningful preference; and
- examples of patterns the user wants to avoid.

Agents must treat samples as behavioral anchors, not as templates from which
facts, names, or phrasing should be copied mechanically.

## Quality criteria

A successful artifact is:

- **Judgment-improving:** it changes what the agent recommends, not only its
  wording.
- **Context-sensitive:** it adapts to goal, medium, relationship, and
  situation.
- **Authentic and aspirational:** it sounds like the user while reinforcing
  who the user intends to become.
- **Actionable:** it uses concrete distinctions and examples rather than vague
  personality labels.
- **Navigable:** an agent can find the relevant guidance without loading raw
  evidence.
- **Compact:** it earns its runtime context cost and avoids repetition.
- **Epistemically honest:** it distinguishes explicit preferences, endorsed
  samples, inferred patterns, contextual exceptions, and uncertainty.
- **Internally coherent:** it avoids unresolved contradictions and stale
  guidance.
- **Safe:** it preserves factual accuracy, user control, privacy, and
  external-action boundaries.

## Evaluation

Evaluate both the artifact and its observed effect.

### Semantic evaluation

Check whether the guidance is specific, navigable, non-redundant, internally
consistent, appropriately qualified, and supported by reviewed examples.
Flag stale material, generic advice, unsupported universal rules, and content
that belongs in raw evidence or another personal context file.

### Behavioral evaluation

Give a fresh agent representative scenarios spanning decide and act, with
meaningful variation in goal, medium, relationship, and stakes. Determine:

- whether it recommends the right communication action;
- whether it selects the right content and framing;
- whether execution fits the medium and relationship;
- whether the result sounds like the user and advances the user's stated
  goals;
- how much substantive editing the user requires; and
- whether the agent recognizes when it should ask rather than guess.

When practical, compare performance with and without `COMMUNICATION.md`. The
artifact is useful only if it materially improves the result.
