# AGENTS.md — Combat Extended Patch Mod Only

Scope: This folder is ONLY for the Combat Extended compatibility patch mod.

Rules:
- Do NOT edit the base mod from here.
- Prefer XML PatchOperations (surgical edits).
- Avoid overwriting entire ThingDefs/WeaponDefs unless unavoidable.
- Document:
  - dependencies
  - load order
  - which defs are patched and why

Deliverables:
- About/ metadata for this patch mod (name, author, packageId, supported versions).
- Patches/ XML files that only apply when CE is active (as appropriate).
- A short TEST.md with steps and expected outcomes/log checks.
