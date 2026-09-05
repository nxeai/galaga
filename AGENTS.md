# Galaga agent instructions

Galaga is a user-owned personal operating system for Codex. Work from the
user's goals, preserve their control, and keep learned personal context
separate from the publishable framework.

## Navigate by purpose

- For communication work, read the relevant files in
  `pillars/communication/`.
- For task formation or execution, read the relevant files in
  `pillars/tasks/`.
- Load files from `context/` only when they are relevant to the current work.
- Use `.agents/skills/` as job entrypoints. Keep those skills thin; the
  suffixed pillar files are the canonical job and evaluation definitions.
- Treat `.galaga/` as local runtime data, never as durable personal knowledge.

Do not load every file by default. Use the smallest relevant set of personal
context and framework guidance.

## Respect the decide and act boundary

Galaga helps the user decide what should happen and act on committed choices.
Do not treat the ability to act as evidence that an action is worthwhile or
authorized. Current user instructions, the immediate goal, and the facts of
the situation take precedence over learned defaults.

## Preserve the ownership boundary

Unsuffixed domain files are **personal artifacts**. Examples include
`COMMUNICATION.md`, `TASKS.md`, and the files in `context/`.

- They contain private, user-specific context.
- They may evolve through their bootstrap and update jobs.
- Improve their usefulness and fidelity; do not optimize for length.
- Never include them in an upstream Galaga contribution.
- Never overwrite them during a framework upgrade.

Files ending in `-SPEC.md`, `-BOOTSTRAP.md`, or `-UPDATE.md`, the contents of
`.agents/`, this file, and general project documentation are **framework
files**.

- Keep them general and safe to publish.
- Do not place personal facts, examples, credentials, or retrieved content in
  them.
- When usage reveals a generalizable improvement, prepare a clean
  framework-only change and encourage the user to contribute it upstream.
- Before creating an external issue or pull request, obtain the user's
  approval and verify that the contribution contains no private material.

## Learn carefully

- Treat observed behavior as evidence, not automatically as desired behavior.
- Prefer the user's current goal and declared aspirations over imitation of
  past habits.
- Do not turn one correction into a durable rule.
- Promote writing samples or other personal evidence into an authoritative
  artifact only after user review.
- Preserve uncertainty when evidence conflicts or is incomplete.
- It is valid for an update job to make no change.

## Keep runtime data transparent

Cached source material and synchronization state belong under `.galaga/`.
The user must be able to inspect and delete them. Distinguish deleting a local
copy from excluding future retrieval or removing learning already derived
from it.

## Skills

Never run a skill marked `disable-model-invocation: true` unless the user
explicitly invokes it.
