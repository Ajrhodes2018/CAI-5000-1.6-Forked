# AGENTS.md — RimWorld Base Mod Update (Target: 1.6.x + all DLC)

## Audience
Maintainer is a newcomer. Use explicit steps, checklists, and verification criteria.

## Goal
Upgrade THIS base mod to RimWorld 1.6.x (all DLC) with minimal behavior change.

## Non-negotiables
- Minimal diffs: no refactors/renames/reformatting unless required to fix errors.
- Do NOT rebalance gameplay or add features unless explicitly asked.
- Keep existing mod/package IDs stable unless 1.6 forces a change (if forced: STOP and explain).

## Stop-and-ask rule (mandatory)
If you cannot justify a change with at least ONE of:
- successful build output, OR
- RimWorld log evidence / reproducible error, OR
- authoritative documentation,
THEN STOP and present 2–3 options with pros/cons and ask for the minimum missing info.
Do not guess.

## Required PR sequence
PR1: AUDIT + BUILD MODEL DETECTION (no functional changes)
Deliverables:
- docs/AUDIT.md:
  - repo map (folders, assemblies, Harmony patches, XML defs)
  - build model: .sln/.csproj vs DLL-only, and exact build steps if determinable
  - RimWorld 1.6 breakpoints list (compile + XML + runtime)
  - migration checklist (blocking/risky/easy)
- No gameplay/logic changes in PR1.

PR2: BASE MOD UPGRADE to 1.6.x
Deliverables:
- Fix compile/API breaks and XML issues; preserve behavior unless forced.
- docs/CHANGELOG_PR2.md: file-by-file “what changed + why”.
- docs/TEST_BASE.md: numbered test steps + “good” criteria + acceptable warnings.
- If build can run in the environment: run it and record command + result.
  If it cannot: STOP and provide a local build checklist.

## PR description format
- Summary (2–4 bullets)
- What changed (grouped by folder)
- Why (short)
- How to test (numbered)
- Known risks / follow-ups
