# AGENTS.md — RimWorld Mod Update (Target: 1.6.x + all DLC)

## Audience
Assume maintainer is a newcomer. Prefer explicit steps and checklists.

## Goals (in order)
G1) Audit the mod and produce a migration plan.
G2) Upgrade the BASE mod to RimWorld 1.6.x (all DLC) with minimal behavior change.
G3) Create a SEPARATE Combat Extended compatibility patch mod.
G4) Create a SEPARATE RimWar compatibility patch mod.

## Non-negotiables
- Do NOT rebalance gameplay or add features unless asked.
- Keep mod/package IDs stable for the base mod.
- Minimal diffs: no refactors/renames/reformatting unless required to fix errors.
- Separate PRs only. Never mix G2/G3/G4 in one PR.

## Required PR sequence
PR1: AUDIT (no functional changes)
Deliverables:
- Architecture map: folders, assemblies, Harmony patches, XML defs.
- “Breakage list” for RimWorld 1.6 (compile + XML + runtime).
- Migration checklist with estimated difficulty per item.

PR2: BASE MOD UPGRADE to 1.6.x
Deliverables:
- Fix compile/API breaks and XML issues.
- Behavior preserved unless 1.6 forces change.
- Change log: file-by-file bullet list explaining WHY each change happened.
- Test checklist + expected log output (what “good” looks like).

PR3: COMBAT EXTENDED PATCH MOD (separate mod)
Deliverables:
- New patch mod under /Patches/CombatExtended/
- Uses targeted XML PatchOperations; avoid overwriting entire defs.
- Clear dependency/load-order notes.
- Test checklist: base only vs base+CE.

PR4: RIMWAR PATCH MOD (separate mod)
Deliverables:
- New patch mod under /Patches/RimWar/
- Targeted patches only.
- Dependency/load-order notes.
- Test checklist: base only vs base+RimWar.

## If uncertain
- Stop and present 2–3 options with pros/cons instead of guessing.
- Prefer the smallest safe change.

## Output format for PR descriptions
- Summary (2–4 bullets)
- What changed (bullets, grouped by folder)
- Why (short)
- How to test (numbered steps)
- Known risks / follow-ups
