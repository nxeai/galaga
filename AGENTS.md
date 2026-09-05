# Galaga agent instructions

Galaga is a user-owned personal operating system for Codex. Work from the
user's goals, preserve their control, and keep learned personal context
separate from the publishable framework.

## Use the personal pillars

Galaga's three personal pillar files contain the user-specific guidance that
makes the framework useful:

- `context/CONTEXT.md` contains durable goals, circumstances, relationships,
  constraints, and other shared context. Use only the relevant portions when
  personal context would improve the current decision or action.
- `communication/COMMUNICATION.md` contains the user's communication judgment,
  goals, and reviewed writing examples. Use it when deciding, drafting, or
  reviewing email, chat, document comments, pull requests, or other
  communication.
- `tasks/TASKS.md` contains the user's approach to forming, prioritizing,
  deciding, and executing work. Use it for task-related decisions and actions.

Galaga should normally run from the user's Local checkout, not an additional
worktree, because its personal artifacts are ignored by Git and belong to the
checkout where they were created. If a personal file is absent in a worktree,
do not assume the user has never bootstrapped it. Briefly recommend continuing
in Local, or obtain confirmation that the user intentionally wants to keep
separate personal artifacts in that worktree.

Before work that depends on a pillar, check whether its personal file exists.
If it does not, invoke the corresponding `bootstrap-context`,
`bootstrap-communication`, or `bootstrap-tasks` skill. Briefly explain what is
missing and what the bootstrap wants to do, obtain the user's approval, and
guide them through any necessary questions and review. Do not give the user
complicated setup instructions or silently create a personal artifact.

Use the `start` skill to guide a new user through all missing pillars. Use
`.agents/skills/` as job entrypoints and keep those skills thin; the suffixed
domain files are the canonical job and evaluation definitions. Treat
`.galaga/` as local runtime data, never as durable personal knowledge.

Do not load every file by default. Use the smallest relevant set of personal
context and framework guidance.

## Respect the decide and act boundary

Galaga helps the user decide what should happen and act on committed choices.
Do not treat the ability to act as evidence that an action is worthwhile or
authorized. Current user instructions, the immediate goal, and the facts of
the situation take precedence over learned defaults.

## Preserve the ownership boundary

Unsuffixed domain files are **personal artifacts**. Examples include
`COMMUNICATION.md`, `TASKS.md`, and `CONTEXT.md`.

- They contain private, user-specific context.
- They are ignored by Git and may be absent before bootstrap.
- They may evolve through their bootstrap and update jobs.
- Improve their usefulness and fidelity; do not optimize for length.
- Never include them in an upstream Galaga contribution.
- Never overwrite them during a framework upgrade.

If a required personal artifact is absent, treat the corresponding pillar as
not bootstrapped. A bootstrap job may create it after the required user review;
an update job must not silently substitute for bootstrap.

Do not override the personal-artifact ignore rules merely to create a backup.
Only version personal artifacts after the user has intentionally chosen a
private repository or other private storage boundary and explicitly asks to
track them.

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
