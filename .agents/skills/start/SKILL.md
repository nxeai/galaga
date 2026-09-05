---
name: start
description: Guide a new or partially configured Galaga user through creating any missing personal pillar files, then demonstrate Galaga on one real piece of work.
---

# Start Galaga

Onboard the user without making them understand Galaga's internal files or
jobs.

## Workflow

1. Determine whether Galaga is running in the user's Local checkout or an
   additional worktree. If it is a worktree, explain that Git-ignored personal
   files do not normally follow the user there and recommend starting the
   Galaga thread in Local. Do not bootstrap in the worktree unless the user
   confirms they intentionally want separate personal artifacts there.
2. Check whether these personal artifacts exist without reading their
   contents:
   - `context/CONTEXT.md`
   - `communication/COMMUNICATION.md`
   - `tasks/TASKS.md`
3. Briefly explain which artifacts are missing, what each missing pillar will
   help Galaga do, and that the resulting files are local and ignored by Git.
   Explain any proposed source access or external action separately.
4. Ask for approval to set up the missing pillars. Stop and wait for the
   user's answer before retrieving personal data or creating an artifact.
5. After approval, run the relevant bootstrap skills, normally in this order:
   `bootstrap-context`, `bootstrap-communication`, then `bootstrap-tasks`.
   Skip artifacts that already exist unless the user asks to rebuild them.
6. Keep the interaction conversational. Ask only necessary clarifying
   questions, preferably one at a time. Explain what Galaga wants to do before
   doing it and preserve every source, privacy, review, and external-action
   boundary in the underlying bootstrap job.
7. Do not consider a pillar ready until its personal artifact has been
   populated and reviewed as required by its bootstrap job. The user may pause
   or decline any pillar without losing completed work.
8. After setup, demonstrate value on one real, current piece of work. If the
   user already identified one during onboarding, use it. Otherwise ask for
   one. Prefer a useful in-thread result with no external side effect, such as
   drafting a real communication without sending it or turning a real task
   into a decision and recommended next action.

If every personal artifact already exists, do not rerun bootstrap. Tell the
user Galaga is ready and continue with the first useful action.
