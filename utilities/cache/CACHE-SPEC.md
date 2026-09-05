# Cache specification

## Purpose

The cache reduces repeated retrieval and token use while increasing
transparency and user control. It is a local, inspectable evidence layer, not
the durable personal model.

## Requirements

- Store cached source material, normalized extracts, indexes, and local
  synchronization state under `.galaga/`.
- Keep `.galaga/` ignored by Git.
- Preserve enough provenance and freshness information to understand the
  origin and validity of cached material.
- Prefer incremental retrieval and deduplication over repeatedly processing
  the same history.
- Let the user inspect and delete local material.
- Treat the cache as disposable and rebuildable.
- Do not require ordinary writing or task work to load the raw cache when a
  compact personal artifact is sufficient.

## Deletion semantics

Clearly distinguish:

1. deleting a local cached copy;
2. excluding an item or source from future retrieval;
3. disconnecting a source; and
4. reconsidering or removing durable guidance derived from deleted evidence.

Deleting cached material must not be represented as complete forgetting when
derived guidance remains in a personal artifact.
