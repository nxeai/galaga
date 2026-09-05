---
name: data-summarize
description: Give the user a lightweight, read-only summary of the personal artifacts and runtime data Galaga currently has. Does not retrieve new data or modify the repository.
---

# Summarize data

Show what Galaga has so far without overwhelming the user or exposing raw
source material unnecessarily.

## Scope

Summarize the current state of:

- `context/CONTEXT.md`
- `communication/COMMUNICATION.md`
- `tasks/TASKS.md`
- `.galaga/`

## Workflow

1. Check which personal artifacts exist. Treat an absent artifact as not yet
   bootstrapped.
2. Read the existing personal artifacts and summarize their major areas of
   coverage, maturity, uncertainty, and obvious gaps.
3. Inspect `.galaga/` at the metadata level: report available source or cache
   categories, approximate size, and freshness when discoverable. Do not load
   raw cached messages, documents, or other source content merely to summarize
   the cache.
4. Produce a concise overview organized by context, communication, tasks, and
   runtime data. State what is absent or stale when relevant.

Keep the default response short and high-level. Do not quote personal
artifacts, enumerate sensitive details, retrieve external data, run bootstrap
or update jobs, or modify any file. Offer deeper inspection only when it would
help the user and let them choose the area.
