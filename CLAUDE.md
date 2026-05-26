# HFK Experiment System — Claude Code Session Rules

Version: 1.1 | Last patched: 2026-05-26 | See docs/HFK_CHANGELOG.md

---

## Session Start Protocol (every session, no exceptions)

1. Read `HFK_STATE.json` — report sprint, week, experiments run, next action
2. Read `docs/HFK_HANDOFF.md` — confirm current experiment context
3. Read `docs/HFK_EXPERIMENT_LOG.md` — report:
   - How many combinations are untested
   - Current Pending Tasks (status of all in-flight experiments)
4. Report full state. Wait for user confirmation before doing anything else.

Do NOT read analytics or session logs at startup unless the user asks.

### Startup Report Format

```
Sprint [N] — [week_label]
Experiments run: [N] of 30

PENDING TASKS:
  Exp [N] ([code]) — [topic] — [status] — [action required]
  ...

Next action: [next_action from HFK_STATE.json]

Waiting for your go-ahead.
```

---

## What This System Is

HFK (Homeschooling for Kiddos) is a Filipino homeschool Facebook page.
The goal is to run content experiments, track Facebook performance,
and find what consistently gets saves and shares — then double down.

This is a CONTENT EXPERIMENTATION system, not a software project.
There is no code, no build step, no validation pipeline.

---

## What Claude Code Does Here

- Reads experiment log and proposes the next highest-value untested combination
- Generates worksheet content, Facebook captions, and Recraft asset prompts
- Reports Pending Tasks status at every session start
- Writes session logs after every session
- Updates HFK_STATE.json after every session
- Updates HFK_HANDOFF.md when sprint state changes
- Updates HFK_EXPERIMENT_LOG.md when experiments are completed or analytics are added

---

## What Claude Code Never Does

- Never posts to Facebook (human operator only)
- Never marks an experiment as "winner" without user confirmation
- Never changes the experiment variable matrix without user direction
- Never skips writing a session log before closing

---

## Protected Paths

- `docs/SESSION_LOG/` — append only, never edit past logs
- `HFK_STATE.json` — update after sessions only, never mid-session
- `docs/HFK_EXPERIMENT_LOG.md` — source of truth for all experiment data

---

## File Read Priority

```
Startup:        CLAUDE.md → HFK_STATE.json → HFK_HANDOFF.md → HFK_EXPERIMENT_LOG.md
Content work:   HFK_EXPERIMENT_LOG.md → docs/HFK_ANALYTICS.md → docs/HFK_BRAND.md
Strategy work:  HFK_EXPERIMENT_LOG.md → docs/HFK_MILESTONES.md → docs/HFK_FUTURE.md
Patch work:     Relevant doc → docs/HFK_CHANGELOG.md
Session close:  Write SESSION_LOG → update HFK_STATE.json → update HFK_HANDOFF.md
```

---

## Git Convention

- **One commit per file** — never use `git add .` or `git add -A`
- Stage and commit each file individually with a clear one-line message
- `assets/` folder is excluded from git — Recraft SVGs stay local only
- Commit message format: `[filename]: [what it is or what changed]`
- **Never run git commands via Claude Code tools** — always output a single
  copy-paste PowerShell code block for the user to run in their own terminal.
  This avoids permission prompts. Include `git push` in the same block when applicable.

Example output format:
```powershell
cd "C:\Users\princ\Desktop\hfk-experiments"
git add .gitignore
git commit -m ".gitignore: exclude assets/, binary exports, OS files"
git add CLAUDE.md
git commit -m "CLAUDE.md: session rules, startup protocol, git convention"
git add README.md
git commit -m "README.md: project overview, folder structure, session types"
git push -u origin master
```

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-26 | Initial session rules |
| 1.1 | 2026-05-26 | Added Pending Tasks to startup protocol and report format; updated file read priority |
| 1.2 | 2026-05-26 | Added Git Convention section |
| 1.3 | 2026-05-26 | Git Convention: never run git via tools — output single copy-paste block instead |
| 1.4 | 2026-05-26 | Added Strategy work to File Read Priority (Milestones + Future) |
