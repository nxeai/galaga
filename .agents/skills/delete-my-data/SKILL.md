---
name: delete-my-data
description: Inventory and delete Galaga's local personal artifacts and runtime data when the user asks to erase or reset their Galaga data. Does not delete data from external source systems.
---

# Delete my data

Delete Galaga data transparently without damaging the reusable framework.

## Scope

The default deletion scope is limited to these paths in the current Galaga
repository:

- `context/CONTEXT.md`
- `communication/COMMUNICATION.md`
- `tasks/TASKS.md`
- `.galaga/`

Deleting these local copies does not delete source data from email, chat,
documents, code hosts, or other external systems. It also does not prevent a
future authorized job from retrieving that data again.

## Workflow

1. Resolve the current repository root and verify it is a Galaga repository.
2. Inventory which scoped paths exist, reporting paths and approximate sizes
   without reading or displaying their contents.
3. Check for other ignored or untracked files that appear to contain Galaga
   personal data. Report possible omissions, but do not expand the deletion
   scope automatically.
4. Explain exactly what will be deleted, whether the operation is recoverable,
   and what external or future-retrieval data will remain.
5. Ask the user for explicit confirmation of the exact deletion scope
   immediately before deleting anything.
6. Use resolved paths contained within the repository. Do not follow symlinks,
   use broad globs, or delete tracked framework files. Prefer a recoverable
   trash operation when available unless the user requests permanent deletion.
7. Verify the confirmed paths are absent and that tracked framework files and
   Git status were not changed by the deletion.
8. Report what was removed, whether it is recoverable, and any remaining data
   or re-retrieval considerations.

If the user also wants external source data deleted, disconnected, or excluded
from future retrieval, treat that as a separate action with its own explicit
scope and authorization.
