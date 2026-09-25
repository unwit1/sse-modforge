# Migration from Personal Agent OS

Status: **in progress**

## Scope

Move the canonical Skyrim/SSE **modding** corpus from `unwit1/personal-agent-os` into this repository:

- `knowledge/libraries/skyrim-modding/**`
- `schemas/skyrim-*.schema.json`
- `tools/skyrim_mod_factory/**`
- Skyrim-specific Knowledge Engine helper tools
- ModForge-specific CI workflows
- source/provenance manifests, adapters, registries, tests, and progress checkpoints

Elder Scrolls lore is explicitly out of scope and remains in its dedicated lore library/repository.

## Cutover invariants

1. Copy and verify before deleting any legacy source.
2. Preserve file bytes and provenance during the initial transfer unless a correctness fix is independently justified.
3. Audit references before removing legacy paths.
4. Personal Agent OS keeps only an integration/redirect layer after cutover.
5. New Skyrim/SSE modding ingestion targets this repository only.
6. A failed/unavailable ModForge destination must not fall back to a local Agent OS modding knowledge path.
7. Existing stable IDs remain stable. Path changes require aliases/redirect metadata.
8. Do not mark migration complete until source and destination manifests reconcile.

## Integration direction

`Personal Agent OS -> ModForge capability/knowledge contract`

ModForge may expose knowledge, validation, planning, generation, testing, and diagnostic capabilities to Agent OS. It should not require Agent OS internals to operate its core modding pipeline.

## Migration phases

- **M0:** initialize target and define ownership boundary.
- **M1:** byte-preserving copy of canonical modding corpus and executable tooling.
- **M2:** destination inventory/hash audit and dependency/reference audit.
- **M3:** add Agent OS integration manifest and ingestion routing.
- **M4:** replace legacy source corpus with redirects/locators after audit passes.
- **M5:** independently validate ModForge CI/tooling and close migration.
