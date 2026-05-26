# HFK Changelog

Central log of all documentation patches across the system.
One row per patch. Each patched doc also has its own local Changelog section.

---

| Patch | Date | Doc | Version | What Changed |
|-------|------|-----|---------|--------------|
| 001 | 2026-05-26 | All docs | — | Initial repo creation (Session 01) |
| 002 | 2026-05-26 | All docs | — | Repo restructured to match CLAUDE.md paths (Session 02) |
| 003 | 2026-05-26 | HFK_BRAND.md | 1.0 → 1.1 | Recraft style changed from colored flat vector to B&W line art; prompt template added; file naming convention added |
| 003 | 2026-05-26 | HFK_EXPERIMENT_LOG.md | 1.0 → 1.1 | Added Pending Tasks section with status tracking |
| 003 | 2026-05-26 | HFK_WORKFLOW.md | 1.0 → 1.1 | Added Type D (Pending Tasks query), Type E (Docs Patch); added Experiment Status Definitions; added Patch Versioning Convention |
| 003 | 2026-05-26 | CLAUDE.md | 1.0 → 1.1 | Added Pending Tasks to startup protocol and report format |
| 003 | 2026-05-26 | HFK_CHANGELOG.md | — | Created this file |
| 004 | 2026-05-26 | .gitignore | — | Added assets/ exclusion |
| 004 | 2026-05-26 | CLAUDE.md | 1.1 → 1.2 | Added Git Convention section (one commit per file, assets/ excluded) |
| 005 | 2026-05-26 | CLAUDE.md | 1.2 → 1.3 | Git Convention updated: never run git via tools, always output single copy-paste block |
| 006 | 2026-05-26 | HFK_MILESTONES.md | — → 1.0 | New doc: M1–M5 milestone gates with unlock conditions and progress tracker |
| 006 | 2026-05-26 | HFK_FUTURE.md | — → 1.0 | New doc: ideation dump with Design/Content/Workflow/Distribution/Brand categories |
| 006 | 2026-05-26 | CLAUDE.md | 1.3 → 1.4 | Added Strategy work to File Read Priority |
| 006 | 2026-05-26 | HFK_WORKFLOW.md | 1.1 → 1.2 | Type C updated to read Milestones + Future docs |

---

## How Patches Work

- A **patch** is any intentional change to docs outside of normal session updates
- Normal session updates (adding experiment rows, updating analytics) are NOT patches
- Patches get a number (001, 002...) and touch one or more docs in the same session
- Every patched doc gets a version bump and a local Changelog row
- Every patch gets a row here regardless of how small

## What Is NOT a Patch

- Adding a new experiment row to Pending Tasks → normal session update
- Logging analytics → normal session update
- Writing a session log → normal session update
- Updating HFK_STATE.json next_action → normal session update
