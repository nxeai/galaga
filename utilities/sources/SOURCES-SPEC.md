# Sources specification

## Status

This is an initial cross-cutting contract. Source-specific behavior remains to
be designed and battle-tested.

Galaga should retrieve only sources the user has placed in scope. Each source
must have an understandable purpose, authority level, access boundary, and
provenance. Distinguish user-authored material from received, quoted,
generated, or system-authored content.

Source retrieval should be incremental when possible. Jobs should reuse valid
local material, avoid repeated broad pulls, and make exclusions visible. A
source's availability does not grant authority to change it or act through it.
