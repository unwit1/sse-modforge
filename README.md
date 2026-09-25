# SSE ModForge

SSE ModForge is the canonical, independently evolving home for the user's Skyrim Special Edition / Anniversary Edition modding knowledge, deterministic Mod Factory tooling, schemas, adapters, tests, research, and ingestion state.

## Repository boundary

- **Canonical modding knowledge lives here.** New Skyrim/SSE modding ingestion must be written to this repository, not to Personal Agent OS.
- **Personal Agent OS remains the orchestrator.** It may discover, query, invoke, and reason over ModForge through stable integration contracts, but it must not maintain a second canonical copy of ModForge knowledge.
- **Lore is separate.** Elder Scrolls lore belongs in the dedicated lore repository/library; ModForge stores modding/implementation knowledge and may reference lore sources rather than absorbing the lore corpus.
- **Fail closed on routing.** If ModForge is unavailable, a modding ingestion request should queue/fail explicitly rather than silently fall back to Personal Agent OS.
- **Provider-neutral integration.** Agent OS should depend on declared ModForge capabilities/contracts, not internal file layout.

## Initial migration

The first migration preserves the proven Personal Agent OS Mod Factory layout where practical so existing schemas, tests, provenance links, and checkpoints survive intact. Subsequent refactors should be made inside ModForge with redirects/aliases when stable identifiers or paths change.

Canonical source after migration: `unwit1/sse-modforge`.

Legacy source during audited migration: `unwit1/personal-agent-os`.

See `MIGRATION.md` and the integration manifest for migration state and cutover rules.
