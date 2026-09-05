---
name: data-delete
description: Move Galaga's local personal artifacts and runtime data to the system Trash, or permanently delete them when explicitly requested. Does not delete data from external source systems.
---

# Delete data

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

## Deletion modes

- **Move to Trash (recommended):** Recoverable until the user empties the
  system Trash. The data has not been permanently deleted while it remains
  there.
- **Permanently delete:** Irreversible. Use only when the user explicitly
  chooses this mode.

## Workflow

1. Before using any tools, list every path in the default scope. Explain that
   external source data will remain and that future authorized jobs may
   retrieve it again. Ask the user to choose and confirm one of these options:
   move all listed data to the system Trash, which is recommended and
   recoverable until the Trash is emptied; or permanently delete all listed
   data, which is irreversible. Stop and wait for their answer.
2. After confirmation, resolve the current repository root and verify it is a
   Galaga repository.
3. Inventory which scoped paths exist without reading or displaying their
   contents. Check for other ignored or untracked files that appear to contain
   Galaga personal data.
4. If the discovered scope differs from what the user confirmed, report the
   difference and obtain new confirmation before proceeding. Never expand the
   deletion scope automatically.
5. Use resolved paths contained within the repository. Do not follow symlinks,
   use broad globs, or delete tracked framework files. For Trash mode, use the
   operating system's native Trash or Recycle Bin mechanism. If that mechanism
   is unavailable or fails, stop and report the failure; never fall back to
   permanent deletion. For permanent mode, delete only the exact confirmed
   paths and only after the user has explicitly selected that mode.
6. Verify the confirmed paths are absent from the repository and that tracked
   framework files and Git status were not changed by the operation.
7. Report what was moved or deleted. For Trash mode, state that the data
   remains recoverable and is not permanently deleted until the user empties
   the Trash. Include any remaining data or re-retrieval considerations.

If the user also wants external source data deleted, disconnected, or excluded
from future retrieval, treat that as a separate action with its own explicit
scope and authorization.
