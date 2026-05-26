# HFK Experiments

Content experiment system for **Homeschooling for Kiddos (HFK)** — a Filipino homeschool Facebook page.

This repo tracks structured content experiments to find which post formats, styles, and hooks consistently drive saves and shares on Facebook.

---

## What This Is

Every post on the HFK page is a controlled experiment — a specific combination of visual style, content type, hook, and CTA. This repo records what was tested, what the results were, and what to do next.

This is **not a software project**. There is no code. It is a content operations system run through Claude Code.

---

## Folder Structure

```
hfk-experiments/
├── CLAUDE.md                        ← Claude Code session rules (read first every session)
├── HFK_STATE.json                   ← Current sprint, experiment count, next action
└── docs/
    ├── HFK_HANDOFF.md               ← Sprint-to-sprint context and decisions
    ├── HFK_EXPERIMENT_LOG.md        ← Source of truth: all experiments, statuses, analytics
    ├── HFK_ANALYTICS.md             ← Paste raw Facebook data here
    ├── HFK_BRAND.md                 ← Typography, colors, Recraft prompt templates
    ├── HFK_WORKFLOW.md              ← Session types, status definitions, protocols
    ├── HFK_OPENER.md                ← Copy-paste prompt for starting new Claude sessions
    ├── HFK_CHANGELOG.md             ← All doc patches, versioned
    └── SESSION_LOG/
        └── YYYY-MM-DD-session-NN.md ← One file per session, append-only
```

---

## Experiment Variable Matrix

Every post is one combination of:

| Variable | Options |
|----------|---------|
| **Style** | A: Cartoon-only · B: Storybook · C: Worksheet-focused · D: Montessori |
| **Content** | 1: Math · 2: Reading/Phonics · 3: Science · 4: Bible/Values · 5: Parent tip |
| **Hook** | X: Question · Y: Free printable · Z: Challenge · W: Fun fact |
| **CTA** | P: Save · Q: Comment SEND · R: Share · S: Follow |

Example: **A-2-Y-Q** = Cartoon + Reading + Free printable hook + Comment SEND

---

## Primary KPIs

**Saves and Shares** — not reach or likes.
Analytics logged 48 hours after each post. Strong signal: 20+ saves OR 10+ shares.

---

## How to Work With This Repo

Open a Claude Code session in this directory. Claude reads `CLAUDE.md` automatically and follows the session start protocol. Say what you need:

- `"Generate content for the next experiment"` → Type A session
- `"Analytics review — here's the data: ..."` → Type B session
- `"What are the pending tasks?"` → Type D session
- `"I want to update the docs to include..."` → Type E session

See `docs/HFK_WORKFLOW.md` for the full list of session types and how each works.
