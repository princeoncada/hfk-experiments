# HFK Experiment Log

Version: 1.1 | Last patched: 2026-05-26 | See docs/HFK_CHANGELOG.md

Source of truth for all content experiments.
Claude Code reads this every session to know what has and hasn't been tested.

Last updated: 2026-05-26

---

## Variable Matrix

Every post is a combination of one value from each variable.
Claude Code tracks which combinations have been tested.

```
STYLE       A: Cartoon-only (no character)
            B: Storybook (illustrated scene)
            C: Worksheet-focused (clean, functional)
            D: Montessori-inspired (minimal, earthy)

CONTENT     1: Math worksheet
            2: Reading / Phonics worksheet
            3: Science worksheet
            4: Bible / Values worksheet
            5: Parent tip (no worksheet)

HOOK        X: Question hook ("Can your child do this?")
            Y: Free printable hook ("Free worksheet inside!")
            Z: Challenge hook ("Try this with your child today")
            W: Fun fact hook ("Did you know...")

CTA         P: Save for later
            Q: Comment SEND for PDF
            R: Share with a homeschool parent
            S: Follow for daily worksheets
```

Example combination: **A-2-Y-Q**
= Cartoon style + Reading worksheet + Free printable hook + Comment SEND CTA

---

## Pending Tasks

Claude Code reads and updates this every session. Status definitions in docs/HFK_WORKFLOW.md.

| # | Experiment | Topic | Grade | Status | Action Required | Owner |
|---|------------|-------|-------|--------|-----------------|-------|
| 1 | A-2-Y-Q | Short Vowel A — CVC Words | G1 | `built` | Post to Facebook | Mother |
| 2 | C-1-Y-P | Addition within 10 | G1 | `content-ready` | Build in Canva, then post | User |
| 3 | B-4-X-Q | Fruits of the Spirit | K-G2 | `content-ready` | Generate Recraft assets, build in Canva, then post | User |

*Update statuses here as experiments move through the pipeline.*
*Remove rows only when status = `complete` or `skipped` — move them to Tested Combinations.*

---

## Tested Combinations

| # | Date | Style | Content | Hook | CTA | Grade | Topic | Reach | Saves | Shares | Comments | Notes |
|---|------|-------|---------|------|-----|-------|-------|-------|-------|--------|----------|-------|
| 1 | —    | A     | 2       | Y    | Q   | G1    | Short Vowel A — CVC Words | — | — | — | — | pending |
| 2 | —    | C     | 1       | Y    | P   | G1    | Addition within 10 | — | — | — | — | pending |
| 3 | —    | B     | 4       | X    | Q   | K-G2  | Fruits of the Spirit | — | — | — | — | pending |

*Fill in Reach, Saves, Shares, Comments 48 hours after posting.*

---

## Priority Queue — Next to Test

Claude Code maintains this list based on what's been tested and what shows early signal.

1. ~~**A-2-Y-Q**~~ — content ready, pending post
2. ~~**C-1-Y-P**~~ — content ready, pending post
3. ~~**B-4-X-Q**~~ — content ready, pending post
4. **A-1-Z-R** (Cartoon + Math + Challenge + Share) — Test share-driven CTA
5. **C-2-X-P** (Worksheet + Reading + Question + Save) — Test question hook with functional style
4. **A-1-Z-R** (Cartoon + Math + Challenge + Share) — Test share-driven CTA
5. **C-2-X-P** (Worksheet + Reading + Question + Save) — Test question hook with functional style

*Claude Code updates this list after every 5 experiments based on early signals.*

---

## Winners (confirmed after 3+ appearances)

None yet.

---

## Losers (confirmed underperformers)

None yet.

---

## Pattern Observations

(Claude Code adds observations here weekly based on analytics data.)

*No data yet — observations will appear after Sprint 1.*

---

## Combination Coverage Map

Tested combinations are marked ✓. Priority next tests marked →.
All others are untested.

```
         Hook X    Hook Y    Hook Z    Hook W
         ────────────────────────────────────
Style A  Content 1: [ ] [ ] [ ] [ ]
         Content 2: [ ] [⏳] [ ] [ ]
         Content 3: [ ] [ ] [ ] [ ]
         Content 4: [ ] [ ] [ ] [ ]
         Content 5: [ ] [ ] [ ] [ ]

Style B  Content 1: [ ] [ ] [ ] [ ]
         Content 2: [ ] [ ] [ ] [ ]
         Content 3: [ ] [ ] [ ] [ ]
         Content 4: [⏳] [ ] [ ] [ ]
         Content 5: [ ] [ ] [ ] [ ]

Style C  Content 1: [ ] [⏳] [ ] [ ]
         Content 2: [ ] [ ] [ ] [ ]
         Content 3: [ ] [ ] [ ] [ ]
         Content 4: [ ] [ ] [ ] [ ]
         Content 5: [ ] [ ] [ ] [ ]

Style D  Content 1: [ ] [ ] [ ] [ ]
         Content 2: [ ] [ ] [ ] [ ]
         Content 3: [ ] [ ] [ ] [ ]
         Content 4: [ ] [ ] [ ] [ ]
         Content 5: [ ] [ ] [ ] [ ]
```

*CTA is tracked in the experiments table, not the coverage map (too many dimensions).*

---

## Analytics Key

```
Strong signal:   Saves 20+  OR  Shares 10+  OR  SEND comments 5+
Weak signal:     Saves 5-19 OR  Shares 3-9  OR  SEND comments 1-4
No signal:       Saves 0-4  AND Shares 0-2  AND SEND comments 0
```

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-26 | Initial experiment log created |
| 1.1 | 2026-05-26 | Added Pending Tasks section with status tracking; added version header |
