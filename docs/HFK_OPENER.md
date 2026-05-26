# HFK Session Opener

Version: 1.1 | Last patched: 2026-05-26 | See docs/HFK_CHANGELOG.md

---

## In Claude Code (normal use)

**You don't need this file.** CLAUDE.md is automatically loaded into every
Claude Code session opened in this directory. The startup protocol fires on
your first message regardless of what you say.

Just open a new chathead and say anything — "hi", "let's go", "new session."
Claude will run the startup protocol first, every time, no exceptions.

---

## Outside Claude Code (fallback only)

If you're ever in a context where CLAUDE.md is not auto-loaded
(e.g. claude.ai, a fresh API call, a different tool), paste this:

--- START ---

You are continuing the HFK (Homeschooling for Kiddos) content experiment system.
The repo is at: C:\Users\princ\Desktop\hfk-experiments

Follow the startup protocol in CLAUDE.md exactly:
1. Read CLAUDE.md
2. Read HFK_STATE.json
3. Read docs/HFK_HANDOFF.md
4. Read docs/HFK_EXPERIMENT_LOG.md
5. Read docs/HFK_DASHBOARD.md
6. Report full state including ALERTS and PENDING TASKS
7. Wait for confirmation before doing anything else.

--- END ---

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-26 | Initial opener — manual prompt for session start |
| 1.1 | 2026-05-26 | Rewritten: clarified Claude Code auto-loads CLAUDE.md; fallback-only use case; updated file list to match current protocol |
