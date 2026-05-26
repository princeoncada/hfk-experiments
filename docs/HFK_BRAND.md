# HFK Brand Reference

Version: 1.1 | Last patched: 2026-05-26 | See docs/HFK_CHANGELOG.md

Design decisions locked in after Experiment 01. Apply to every worksheet.

---

## Colors

| Role | Hex |
|------|-----|
| Primary accent | `#FFCC00` (yellow) |
| Background | `#FFFFFF` (white) |
| Body text | `#000000` (black) |
| Trace / ghost text | `#CCCCCC` (light gray) |
| Footer text | `#888888` (mid gray) |

---

## Typography

| Element | Font | Size | Style |
|---------|------|------|-------|
| Page title | Baloo 2 | 48 | Bold |
| Page subtitle | Baloo 2 | 20 | Regular |
| Activity headings | KG Primary Penmanship | 22 | All caps |
| Trace activity text | KG Primary Penmanship Lined | — | Color #CCCCCC |
| Vowel bank (a e i o u) | KG Primary Penmanship | 24 | Regular |
| Fill-in content | KG Primary Penmanship | 32 | Regular |
| Footer | KG Primary Penmanship | 24 | Regular |

---

## Layout (A4 Portrait)

- Top strip: ~25% of page height, filled `#FFCC00`
- Worksheet assets displayed in a row inside the yellow strip
- Yellow border frame around full page (thin, inset)
- Footer centered at bottom: `© Homeschooling for Kiddos`
- 3 activity sections stacked below the strip

---

## Recraft Asset Style

**Target look:** Black-and-white children's printable line art.
Hand-drawn pencil/ink style — no color, no fills, no shadows.
Assets are black outlines on transparent background only.
Color on the worksheet comes from Canva layout (yellow strip, etc.), not from assets.

**Recraft settings:**
- Style: `Vector illustration → Line art` (or closest equivalent to pencil/ink outline)
- Do NOT change style between assets — set it once, generate all assets back to back
- After the first asset you're happy with: click **"Use as style reference"** → save as `HFK-worksheet-lineart` → apply to all remaining generations

**Prompt template — use this structure for every asset:**

```
Create a black-and-white children's printable worksheet asset of [ASSET NAME].

Style requirements:
- hand-drawn pencil/ink worksheet line art
- thick clean black outline
- transparent background
- no color
- no gray background
- no shadows
- no text
- no extra decorations
- simple rounded playful shapes
- centered full object
- not cropped
- consistent with a kindergarten phonics worksheet style
```

**Example (cat):**

```
Create a black-and-white children's printable worksheet asset of a sitting cat.

Style requirements:
- hand-drawn pencil/ink worksheet line art
- thick clean black outline
- transparent background
- no color
- no gray background
- no shadows
- no text
- no extra decorations
- simple rounded playful shapes
- centered full object
- not cropped
- consistent with a kindergarten phonics worksheet style
```

**Naming convention for saved files:**
`[experiment-id]-[object].svg` — e.g. `exp01-cat.svg`, `exp01-hat.svg`

---

## Word Sets by Worksheet

| Worksheet | Words used | Fill-in words |
|-----------|-----------|---------------|
| Short Vowel A — CVC (Exp 01) | cat, hat, van, bat | c_t, h_t, v_n, b_t, m_n + 1 more |

*Add a row here every time a new worksheet is finalized.*

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-26 | Initial brand reference created |
| 1.1 | 2026-05-26 | Recraft style changed from colored flat vector to B&W line art; prompt template added; file naming convention added |
