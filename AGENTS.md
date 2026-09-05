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

## Follow the module convention

Every Galaga module uses the same four-file contract. A module is a durable
personal capability, such as context, communication, or tasks. Utility skills,
runtime infrastructure, and general documentation are not modules and do not
need this structure.

Put each module in a lowercase directory and use one canonical uppercase name
for all four files:

```text
<module>/
  <MODULE>.md
  <MODULE>-SPEC.md
  <MODULE>-BOOTSTRAP.md
  <MODULE>-UPDATE.md
```

For example:

```text
context/
  CONTEXT.md
  CONTEXT-SPEC.md
  CONTEXT-BOOTSTRAP.md
  CONTEXT-UPDATE.md
```

The four files have distinct responsibilities:

- `<MODULE>.md` is the user-owned personal artifact and the authority on that
  user for the module. It is local and Git-ignored. When Galaga creates or
  changes it, use the reviewed bootstrap or update workflow; the user may edit
  their own artifact directly at any time.
- `<MODULE>-SPEC.md` defines what the personal artifact must accomplish. It
  owns scope, required content or structure, quality criteria, boundaries, and
  evaluation. It defines fitness, not the steps of a job.
- `<MODULE>-BOOTSTRAP.md` defines how to create the first useful personal
  artifact or intentionally rebuild it. It owns inputs, permissions, evidence
  gathering, user questions and review, creation, and completion criteria.
- `<MODULE>-UPDATE.md` defines how to maintain an existing personal artifact
  from new evidence and feedback. It owns change detection, user review,
  incremental edits, no-change outcomes, and routing to bootstrap when the
  personal artifact is absent.

Skills in `.agents/skills/` are thin entrypoints into these canonical jobs.
Name module job skills `bootstrap-<module>` and `update-<module>` and have them
defer to the matching suffixed file rather than duplicate its instructions.

Enforce this convention whenever adding or changing a module:

- Do not add a module without all three committed suffix files and an explicit
  Gitignore rule for its unsuffixed personal artifact.
- Do not commit the unsuffixed personal artifact, personal examples, retrieved
  source material, or generated user data.
- Do not blur specification, initial creation, and ongoing maintenance into a
  single file or introduce a template as a substitute for the specification.
- Keep names, references, bootstrap and update skills, and cross-module
  onboarding or data-management guidance consistent with the module.
- Treat a change that violates this contract as incomplete and repair it
  before considering the framework change finished.

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
