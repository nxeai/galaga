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
do not assume the user has never initialized it. Briefly recommend continuing
in Local, or obtain confirmation that the user intentionally wants to keep
separate personal artifacts in that worktree.

Before work that depends on a pillar, check whether its personal file exists.
Use the corresponding `update-context`, `update-communication`, or
`update-tasks` skill when initialization or learning is needed. Missing or
partial files are normal inputs to update. Explain the useful next step and
ask only questions that materially affect the current task.

Use the `start` skill to coordinate updates around a first useful outcome. Use
`.agents/skills/` as job entrypoints and keep those skills thin; the suffixed
domain files are the canonical job and evaluation definitions. Treat
`.galaga/` as local runtime data, never as durable personal knowledge.

Do not load every file by default. Use the smallest relevant set of personal
context and framework guidance.

## Follow the module convention

Every Galaga module uses the same three-file contract. A module is a durable
personal capability, such as context, communication, or tasks. Utility skills,
runtime infrastructure, and general documentation are not modules and do not
need this structure.

Put each module in a lowercase directory and use one canonical uppercase name
for all three files:

```text
<module>/
  <MODULE>.md
  <MODULE>-SPEC.md
  <MODULE>-UPDATE.md
```

For example:

```text
context/
  CONTEXT.md
  CONTEXT-SPEC.md
  CONTEXT-UPDATE.md
```

The three files have distinct responsibilities:

- `<MODULE>.md` is the user-owned personal artifact and the authority on that
  user for the module. It is local and Git-ignored. When Galaga creates or
  changes it, use the update workflow; the user may edit
  their own artifact directly at any time.
- `<MODULE>-SPEC.md` is the authority on the personal artifact's structure and
  fitness. It must define the required sections, what belongs in each section,
  what does not belong, quality criteria, and how to evaluate and repair the
  artifact. It defines the result, not the steps of a scheduled job.
- `<MODULE>-UPDATE.md` defines the single protocol for creating, enriching,
  correcting, and refreshing the personal artifact. Missing files are
  initialized; existing knowledge is preserved and improved incrementally.
  Rebuilding requires explicit user intent.

Skills in `.agents/skills/` are thin entrypoints into these canonical jobs.
Name module job skills `update-<module>` and have them
defer to the matching suffixed file rather than duplicate its instructions.

Whenever the user's intent is to bring `<MODULE>.md` closer to its intended
form, read `<MODULE>-SPEC.md` and use it as the authoritative contract. Requests
such as "fix," "cleanup," "improve," and "optimize" are examples, not an
exhaustive command vocabulary; follow the spirit of the request. Diagnose the
artifact against the required structure, put retained information in the
correct section, remove unsupported or misplaced material when authorized,
and verify the result against the spec. Preserve supported personal meaning
and uncertainty; structural authority is not permission to invent, silently
reinterpret, or discard user context.

Enforce this convention whenever adding or changing a module:

- Do not add a module without both committed suffix files and an explicit
  Gitignore rule for its unsuffixed personal artifact.
- Do not commit the unsuffixed personal artifact, personal examples, retrieved
  source material, or generated user data.
- Keep the specification separate from the update protocol. Do not introduce
  a separate first-run protocol or a template as a substitute for the spec.
- Do not accept a spec that leaves the personal artifact's structure to the
  implementing agent or lacks enough evaluation guidance to repair it.
- Keep names, references, update skills, and cross-module
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
- They are ignored by Git and may be absent before their first update.
- They evolve through their update jobs.
- Improve their usefulness and fidelity; do not optimize for length.
- Never include them in an upstream Galaga contribution.
- Never overwrite them during a framework upgrade.

## Run updates progressively

Update inputs are the immediate task, available evidence and authorized
sources, a bounded effort or retrieval budget, and the trigger (interactive
or scheduled). Infer missing inputs from the request; these are not a form
the user must complete. No first-run flag is required.

Prioritize the immediate outcome, explicit corrections, consequential stale
information, then gaps in coverage. The spec describes the desired steady
state; required sections may explicitly record unknown or unexplored areas.
Do not delay a useful result to complete an interview or fill every section.

Use existing authorization without repeatedly asking for it. Obtain approval
for new source access or expanded scope when needed. Review consequential
interpretations and authoritative samples with the user. Scheduled updates
work within established scope and queue unresolved review items without
requiring an interview. Never activate a schedule merely by running update.

Preserve existing knowledge unless the user requests a rebuild. A run can
create a useful partial artifact, improve an existing one, queue a review
item, or make no change. Report the actual outcome and remaining gaps; file
existence alone is not proof of complete coverage. Keep retrieval cursors,
pending evidence, and detailed processing state under `.galaga/`.

Do not override the personal-artifact ignore rules merely to create a backup.
Only version personal artifacts after the user has intentionally chosen a
private repository or other private storage boundary and explicitly asks to
track them.

Files ending in `-SPEC.md` or `-UPDATE.md`, the contents of
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
