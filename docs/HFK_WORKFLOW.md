# HFK Experiment System — Session Workflow

Version: 1.1 | Last patched: 2026-05-26 | See docs/HFK_CHANGELOG.md

---

## Session Start (every session, no exceptions)

```
1. Claude Code reads CLAUDE.md
2. Claude Code reads HFK_STATE.json — reports sprint + status
3. Claude Code reads HFK_HANDOFF.md — confirms context
4. Claude Code reads HFK_EXPERIMENT_LOG.md — reports untested count + Pending Tasks
5. Reports full state including Pending Tasks. Waits for user confirmation.
6. Does nothing else until user confirms.
```

---

## Standard Session Types

### Type A — Content Generation Session
User wants to produce the next post.

```
QUERY    → Claude reads experiment log, finds next untested priority combination
PROPOSE  → Claude presents the combination + rationale
CONFIRM  → User approves or redirects
GENERATE → Claude produces: caption + Canva brief + Recraft asset prompts
LOG      → Claude adds experiment to Pending Tasks as "content-ready"
CLOSE    → Write session log, update HFK_STATE.json
```

### Type B — Analytics Review Session
User pastes Facebook data from the past week.

```
INPUT    → User pastes reach/saves/shares/comments per post
UPDATE   → Claude updates HFK_EXPERIMENT_LOG.md with the data
           Claude updates experiment status to "complete"
ANALYZE  → Claude identifies patterns, updates winners/losers
RECOMMEND → Claude proposes next priority queue adjustments
CLOSE    → Write session log, update HFK_STATE.json and HFK_HANDOFF.md
```

### Type C — Strategy Session
User wants to review overall direction.

```
READ     → Claude reads full experiment log + handoff
SUMMARIZE → Present: what's working, what's not, what's untested
DECIDE   → User makes directional call
UPDATE   → Claude updates priority queue accordingly
CLOSE    → Write session log
```

### Type D — Pending Tasks Query
User asks: "What are the pending tasks?" or "What's the status?"

```
READ     → Claude reads Pending Tasks section of HFK_EXPERIMENT_LOG.md
REPORT   → Claude lists every in-flight experiment with its current status and action required
CONFIRM  → User provides any status updates (e.g. "Exp 01 was posted today")
UPDATE   → Claude updates statuses in HFK_EXPERIMENT_LOG.md accordingly
CLOSE    → Write session log if any statuses changed
```

### Type E — Docs Patch Session
User wants to update, improve, or version the documentation.

```
SCOPE    → User describes what to change and why
PLAN     → Claude lists which files will be patched and what changes
CONFIRM  → User approves
PATCH    → Claude edits relevant docs, increments version numbers
CHANGELOG → Claude adds entries to each patched doc's changelog + HFK_CHANGELOG.md
CLOSE    → Write session log noting patch number and scope
```

---

## Experiment Status Definitions

Every experiment in the Pending Tasks table carries one of these statuses:

| Status | Meaning | Action Required |
|--------|---------|-----------------|
| `queued` | In priority queue, content not yet generated | Run a Type A session to generate content |
| `content-ready` | Full content package generated, not yet built | Build in Canva + generate Recraft assets |
| `built` | Canva export done (JPG + PDF ready), not yet posted | Human operator posts to Facebook |
| `live` | Posted on Facebook, 48h analytics window open | Wait 48h, then pull metrics from Insights |
| `analytics-due` | 48h passed, analytics not yet logged | Run a Type B session to log data |
| `complete` | Analytics logged, experiment fully closed | No action — archived |
| `skipped` | Decided not to run this combination | No action — note reason in log |

---

## Session Close Protocol (every session, no exceptions)

Before ending any session, Claude Code must:

1. Write a session log to `docs/SESSION_LOG/YYYY-MM-DD-session-NN.md`
2. Update `HFK_STATE.json` (experiments_run, last_updated, next_action)
3. Update `docs/HFK_HANDOFF.md` Zone 1 if sprint or status changed

### Session Log Format

```markdown
# HFK Session Log — YYYY-MM-DD Session NN

## What Was Done
[bullet list — completed actions only]

## What Is In Progress
[pending items, or "Nothing."]

## Experiment Status
Experiments run: N
New this session: [list combinations tested]
Analytics updated: [yes/no — which posts]

## Next Action
[one clear sentence — what to do at start of next session]

## Open Decisions
[unresolved questions, or "None."]
```

---

## Content Generation Output Format

Every Type A session produces this package:

```
EXPERIMENT:     [Style]-[Content]-[Hook]-[CTA] (e.g. A-2-Y-Q)
GRADE TARGET:   [Grade level]
TOPIC:          [Specific topic]

CANVA BRIEF:
  Layout:       [which template variant to use]
  Accent color: [hex]
  Key visual:   [description]

RECRAFT PROMPTS:
  (Use the B&W line art template from docs/HFK_BRAND.md)
  Asset 1:      "[full prompt]" → exp[NN]-[object].svg
  Asset 2:      "[full prompt]" → exp[NN]-[object].svg

CAPTION:
  [Ready to copy-paste Facebook caption]

HASHTAGS:
  [12-15 relevant hashtags]

OPERATOR INSTRUCTIONS:
  [What the human needs to do to post — files, timing, DM response]

LOG ENTRY:
  Pending Tasks table row for HFK_EXPERIMENT_LOG.md
```

---

## Analytics Input Format

When pasting Facebook data, use this structure so Claude can parse it:

```
POST [N]:
  Date posted: YYYY-MM-DD
  Combination: [Style]-[Content]-[Hook]-[CTA]
  Topic: [topic]
  Grade: [grade]
  Reach: [number]
  Saves: [number]
  Shares: [number]
  Comments: [number]
  SEND comments: [number]
  Notes: [anything notable]
```

---

## Patch Versioning Convention

When any doc is patched:

1. Increment the version in the doc header: `Version: 1.0 → 1.1`
   - Minor bump (x.1): additions, clarifications, new sections
   - Major bump (2.0): structural changes, renamed sections, breaking changes
2. Add a row to the doc's own `## Changelog` section
3. Add a row to `docs/HFK_CHANGELOG.md` (central log)
4. Write a session log for the patch session

---

## Rules That Never Change

- Human reviews every post before it goes live
- No combination declared winner without 3+ appearances
- Analytics logged 48 hours after posting (not immediately)
- One experiment per day — do not post twice in one day
- Session log is written before every session close
- Saves and shares are the primary KPIs — reach and likes are secondary

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-26 | Initial workflow document |
| 1.1 | 2026-05-26 | Added Type D (Pending Tasks), Type E (Docs Patch); added Experiment Status Definitions table; added Patch Versioning Convention; updated Content Generation Output Format to reference B&W line art brand |
