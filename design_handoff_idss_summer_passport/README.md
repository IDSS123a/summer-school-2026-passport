# Handoff: IDSS Summer School Passport 2026

## Overview

A **14-page printable A5 booklet** designed as a child-friendly "passport" for participants of the IDSS Sarajevo Summer School 2026 (August 3–14, 2026). Each child receives a physical printed booklet on Day 1 and uses it throughout the two-week programme as a travel journal — filling in their name, drawing self-portraits, ticking off daily missions, drawing "stamps" per destination, and reflecting at the end.

The booklet is:
- **Print-first**: the primary deliverable is a print-ready PDF; screen viewing is secondary.
- **Bilingual context, English content**: the school is Internationale Deutsche Schule Sarajevo, but this booklet is fully in English.
- **Brand-locked** to the school's two protected colors: sky blue `#08ABE6` and ochre `#FFCB29`.

## About the Design Files

The files in this bundle are **design references created in HTML** — a print-ready A5 prototype showing the intended look, layout, typography, and content of the finished booklet. **They are not production code to ship as-is.**

The task is to **recreate this design in the target production environment.** For this deliverable, the most likely production paths are:

1. **Print pipeline (highest priority)**: reproduce the layout as a print-ready PDF using a designer's tool of choice (Adobe InDesign, Affinity Publisher, Figma → PDF export, or a headless-browser HTML → PDF pipeline such as Puppeteer / WeasyPrint / Prince). The included HTML can be used directly with a headless browser to produce a production PDF — `@page { size: A5 portrait; margin: 0 }` and `page-break-after: always` are already wired.
2. **Web preview (secondary)**: if the school wants an online preview version (e.g. on the IDSS website), rebuild inside the school's existing web stack using its established component patterns.

If there is no existing environment yet, the pragmatic choice for this project is HTML → PDF via **Puppeteer** or **WeasyPrint**, because the source is already valid print-ready HTML.

## Fidelity

**High-fidelity (hifi).** The HTML mockup is pixel-precise for print at A5:
- Final colors (exact hex values, see Design Tokens)
- Final typography (Google Fonts: Bricolage Grotesque, Nunito, Caveat, JetBrains Mono)
- Final copy (all 14 pages of English text)
- Final layout at A5 portrait (148 mm × 210 mm) with print-safe margins

Recreate pixel-perfectly. Do not substitute fonts or colors without approval from the school.

---

## Pages / Views

The booklet has **14 pages** in a fixed sequence. Every day-page follows a shared template (see "Day-page template" below). Page-specific content follows.

### Page 1 — Cover

- **Purpose**: front cover; identifies the traveller and validity window.
- **Layout**: full-bleed vertical split — top ~55% sky blue `#08ABE6`, bottom ~45% ochre `#FFCB29`, softened with two radial highlights (light blue top, warm cream bottom). A dashed white passport border sits 6 mm inside the trim.
- **Components** (top → bottom):
  1. **Top-left IDSS logo card** — white rounded-corner (2 mm) card, 3 mm × 4 mm padding, drop shadow, `idss-logo.png` at 12 mm tall.
  2. **Top-right circular stamp** — 22 mm diameter, 1.5 px white border, rotated +6°, text "SARAJEVO · BiH · 2026" in JetBrains Mono 6.5 pt / letter-spacing 0.15em.
  3. **Eyebrow** — "INTERNATIONALE DEUTSCHE SCHULE · SARAJEVO", JetBrains Mono 8 pt, letter-spacing 0.35em, white 90%.
  4. **Summer School logo card** — 78 mm wide white rounded card (3 mm radius, 10 mm drop shadow) containing `summer-school-logo.png`.
  5. **Title block** — "PASSPORT" in Bricolage Grotesque 800, 32 pt, white with a soft 0/3/12 shadow; below it "MY BIG LITTLE JOURNEY" 12 pt 600, letter-spacing 0.2em, ink navy.
  6. **Fields card** — white 94%-opacity rounded card, 5 mm × 6 mm padding, 2 mm radius, 2-column grid:
     - Full row: "FULL NAME OF TRAVELLER" (dotted underline, Caveat 16 pt fill).
     - Col 1: "PASSPORT N°" static value `SS-2026-______` in JetBrains Mono 12 pt.
     - Col 2: "VALID" static value `03.08 — 14.08.2026` in Bricolage Grotesque 700 11 pt.
  7. **Foot line** — "SARAJEVO · BOSNIA AND HERZEGOVINA", JetBrains Mono 7 pt, letter-spacing 0.28em, centred.

### Page 2 — Traveller Identification

- **Purpose**: personal identity page + code of conduct.
- **Layout**: cream `#FFFDF6` background, dashed navy border 6 mm inside, 12 mm side padding.
- **Components**:
  1. **Page label** top-left: "PAGE 01 · TRAVELLER IDENTIFICATION", JetBrains Mono 7.5 pt, letter-spacing 0.25em, ink-soft.
  2. **Title row**: `<h2>` "I am the traveller" Bricolage 20 pt + ochre pill "SS · 2026" JetBrains Mono 8 pt.
  3. **ID grid** (42 mm | 1fr):
     - **Portrait box**: 42 × 52 mm, dashed navy border, 2 mm radius, striped background (45° repeat with sky-tint stripes), centred hint text "draw your self-portrait here ✏︎" in Caveat 15 pt ink-soft.
     - **Field rows** (× 4): each has a mono uppercase label (7.5 pt, letter-spacing 0.2em) + 7 mm dotted underline for handwriting:
       - "FIRST & LAST NAME"
       - "DATE OF BIRTH"
       - "MY GROUP"
       - "NICKNAME (OPTIONAL)"
  4. **Rules card**: sky-soft `#d6f0fb` background, 4 px sky-blue left border, 2 mm radius, 5 mm × 6 mm padding.
     - Title "Traveller's Code of Conduct" 12 pt in sky-deep.
     - Ordered list (1–4), each item prefixed with a 5.5 mm ochre circle containing the number in Bricolage 800 9 pt:
       1. I listen to my guides and educators.
       2. I take good care of my belongings.
       3. I respect my friends on the journey.
       4. I explore bravely and I ask questions!
  5. **Foot row**: two mono uppercase strings — "ISSUED BY · IDSS SARAJEVO" (left) and "DATE OF ISSUE · 03.08.2026" (right).
  6. **Page number** bottom-right: "02 / 14", JetBrains Mono 8 pt, letter-spacing 0.15em.

### Pages 3–12 — Day pages (shared template)

Every day-page uses the same template. See **"Day-page template"** below for structure. Page-specific content:

| Page | Day | Location code | Title | Subtitle (Caveat) | Header style |
|------|-----|---------------|-------|-------------------|--------------|
| 3 | 01 | `SJJ · OLD BAZAAR` | Baščaršija | "Exploring Sarajevo" | Sky blue |
| 4 | 02 | `ZOO · BAMBI` | Zoo Bambi | "My safari day" | Sky blue |
| 5 | 03 | `TRB · MOUNTAIN` | Trebević | "Adventure in the clouds" | Sky blue |
| 6 | 04 | `VSK · PYRAMID` | Pyramid of the Sun | "On the trail of an ancient secret" | Sky blue |
| 7 | 05 | `IDSS · STUDIO` | Creative Day | "The day of imagination" | **Ochre** (rhythm break) |
| 8 | 06 | `SJJ · HISTORY` | Old Town II | "Sarajevo through history" | Sky blue |
| 9 | 07 | `VSK · FACTORY` | Vispak, Visoko | "From grain to table" | Sky blue |
| 10 | 08 | `SJJ · ILLUSIONS` | Museum of Illusions | "Nothing is what it seems" | Sky blue |
| 11 | 09 | `KNJ · BUNKER` | Konjic | "The secret under the ground" | Sky blue |
| 12 | 10 | `JVD · FINALE` | Javorov Do | "Final adventure & BBQ" | **Ochre** (rhythm break) |

For per-page checklist and prompt text, see the source HTML — each day-page has exactly:
- **4 mission checklist items** (English, imperative "I …")
- **1 prompt box** with a Caveat handwritten question + 3 dotted writing lines
- **1 stamp slot** with a hint text describing what to draw

**Special case — Page 4 (Day 02, Zoo Bambi)**: replaces the two-column "prompt + stamp slot" with a **3×2 Animal Bingo grid**. Each cell (aspect-ratio 1:1) contains a 12 mm ochre-soft circle with a stroke SVG icon and a Bricolage 9 pt label. Cells (in order):
1. Lion (lion-face SVG)
2. Something that swims (water waves)
3. Biggest bird (bird silhouette)
4. Stripes or spots (horizontal bands)
5. Sleeping animal (curled-up)
6. **Free space** — sky-blue background, white text, star icon.

### Page 13 — My Summer School Memories

- **Purpose**: end-of-programme reflection + director's signature seal.
- **Layout**: cream background, dashed border, 12 mm padding.
- **Components**:
  1. Section header "Summer School 2026" (see section-header pattern) + `<h2>` "My Summer School memories" (Bricolage 22 pt) + Caveat subtitle "the best bits of my journey ✦" 18 pt ochre-deep.
  2. **2×2 memory-card grid**, 5 mm gap:
     - Top-left "Best day" — white bg, sky-blue border.
     - Top-right "Best new friend" — ochre-soft bg, ochre-deep border/label.
     - Bottom-left "What I learned most" — ochre-soft bg, ochre-deep border/label.
     - Bottom-right "Funniest moment" — white bg, sky-blue border.
     - Each card: 42 mm min-height, 1.5 px border, 2 mm radius, Bricolage 10 pt label, ruled writing area (repeating horizontal lines every 6 mm at 18% opacity).
  3. **Signature row** at bottom:
     - Left: Caveat 20 pt "Davor Mulalić" on a 1.5 px navy underline, plus role "PROGRAMME DIRECTOR · IDSS SARAJEVO" in mono 7.5 pt below.
     - Right: **circular red seal** — 30 mm diameter, 2 px `#c94a3a` border and text, rotated −8°, 85% opacity, containing "IDSS / SUMMER / SCHOOL / · 2026 · / SARAJEVO" in JetBrains Mono 6.5 pt (bottom line 5 pt / 500 weight).

### Page 14 — Back Cover

- **Purpose**: farewell + brand sign-off.
- **Layout**: full-bleed vertical split — top ~60% ochre `#FFCB29`, bottom ~40% sky blue `#08ABE6`, hard transition at ~62% with a 10% blend zone. Dashed navy border inside.
- **Components** (top → bottom, centred):
  1. Kicker "END OF THE JOURNEY", JetBrains Mono 8 pt, letter-spacing 0.35em, ink navy.
  2. `<h1>` "Thank you / for travelling / with us." — Bricolage 800, 34 pt, line-height 0.95, ink navy, `text-wrap: balance`.
  3. Body paragraph (max-width 105 mm, `text-wrap: pretty`, 12 pt / line-height 1.5):
     > For two whole weeks you played, discovered and made new friends. Keep this passport as a souvenir of your first big little journey — and see you on the next adventure.
  4. **Tagline** on the ochre/sky transition band: "Play · Discover · Make friends." — Caveat 20 pt, white, centred.
  5. **Foot lockup**: "IDSS · SUMMER SCHOOL · SARAJEVO · 2026" — JetBrains Mono 7.5 pt, letter-spacing 0.28em, white, centred.

---

## Day-page template

All 10 day-pages use this structure:

### 1. Header band (top of page)

- **Height**: intrinsic (padded 8 mm top / 12 mm sides / 6 mm bottom).
- **Background**: sky blue `#08ABE6` (or ochre `#FFCB29` on Days 05 & 10 for rhythm).
- **Bottom edge**: a scalloped tear-off effect — a horizontal repeating pattern of 2.5 mm sky-blue half-circles centred on `y=0`, tiled every 8 mm, positioned 4 mm below the band. This creates the look of a perforated passport strip.
- **Top row (flex space-between)**:
  - Left: "DAY · NN" in JetBrains Mono 9 pt, letter-spacing 0.3em, 85% white.
  - Right: **ochre code chip** — background `#FFCB29`, ink text, 1 mm × 3 mm padding, 1 mm radius, JetBrains Mono 700 8 pt, letter-spacing 0.18em.
- **Title**: Bricolage 800, 22 pt, line-height 1.02, white (or navy on ochre variant).
- **Subtitle**: Caveat 17 pt, ochre-soft `#fff3c9` (or sky-deep `#0784b3` on ochre variant), 1 mm top margin.
- **Date row** (4 mm top margin, flex, baseline-aligned):
  - "DATE" label + 40 mm dotted underline
  - "WEATHER" label + 22 mm dotted underline

### 2. Body (below header)

- Padding 10 mm top / 12 mm sides / 12 mm bottom.
- Flex column, 6 mm gap.

#### Mission section
- Section header: uppercase sky-deep Bricolage 11 pt, letter-spacing 0.12em, preceded by a 6 mm × 3 px ochre bar.
- Header text: "My mission today" (Days 03–06, 08–11), or **"My workshops today"** (Day 05), or **"Animal bingo · tick when you see it"** (Day 04 second section).
- 4 tasks stacked vertically. Each task:
  - 6 × 6 mm white checkbox, 1.8 px navy border, 1 mm radius.
  - Task text: Nunito 600, 10.5 pt, line-height 1.35.
  - Checked state: `.box.filled` shows a sky-deep `✓` centred (Bricolage 800, 5 mm).

#### Prompt + stamp row (all days except Day 04)
- 2-column grid: `1fr | 42mm`, 6 mm gap.
- **Prompt box** (left):
  - 1.4 px navy-soft border, 2 mm radius, white background, 4 mm × 5 mm padding.
  - Section header (small, no leading bar).
  - Caveat 14 pt question, then 3 dotted-line lines (7 mm height each).
- **Stamp slot** (right):
  - 42 mm square, 1.8 px dashed sky-blue border, 2 mm radius.
  - Diagonal pinstripe background (repeating -45° stripes, 4 mm on / 0.5 mm sky-tint).
  - Label "DAY NN · STAMP" in JetBrains Mono 7 pt, letter-spacing 0.24em, sky-deep.
  - Caveat 13 pt hint below.
  - Days 05 & 10: border and label switch to ochre-deep `#e0a800` for continuity with the ochre header.

### 3. Page number (bottom-right)
- Absolute-positioned, "NN / 14", JetBrains Mono 8 pt, letter-spacing 0.15em, ink-soft.

---

## Interactions & Behavior

This is a **print artefact**, not a screen application. The only interactive affordance in the HTML mockup is:

- **"Print / Save as PDF" button** — a floating "no-print" pill above the pages that calls `window.print()`. It is hidden via `@media print` and must not appear in production output.

There are **no** hover states, no animations, no JavaScript state, no data fetching, no responsive breakpoints (the artefact is fixed A5 portrait).

If a web preview version is later commissioned, the interaction spec would be limited to: (a) scroll through pages, (b) call `print()`, (c) optionally allow filling name/date/group fields as HTML `<input>`s that persist to localStorage. This is **out of scope** for the current handoff.

## State Management

None. The booklet is stateless. The only "state" is the child's handwritten input on paper.

---

## Design Tokens

### Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--sky` | `#08ABE6` | Primary brand blue — day-page header, borders, section-header text (deep), rules card left border |
| `--sky-deep` | `#0784b3` | Emphasised sky (section headers, stamp labels, subtitles on ochre) |
| `--sky-soft` | `#d6f0fb` | Rules card background |
| `--ochre` | `#FFCB29` | Primary brand yellow — code chips, ochre header days, ordered-list badges, accent bars |
| `--ochre-deep` | `#e0a800` | Emphasised ochre (memory card border, stamp label on ochre days, subtitle) |
| `--ochre-soft` | `#fff3c9` | Bingo icon circle background, memory card fill, subtitle on sky days |
| `--ink` | `#14344a` | Primary text — deep navy, warmer than pure black |
| `--ink-soft` | `#4b6a80` | Secondary text — page labels, hints |
| `--paper` | `#FFFDF6` | Page background — warm cream (passport paper feel) |
| `--paper-2` | `#f6f0dc` | (Reserved, currently unused) |
| `--rule` | `rgba(20,52,74,0.28)` | Dotted underlines, prompt-box borders |
| `--stamp-red` | `#c94a3a` | Director's seal on Page 13 only |

**Brand lock**: `#08ABE6` and `#FFCB29` are the school's protected colors and **must not be substituted**. All other tokens are derived and may be tuned if print proofing requires it.

### Typography

Loaded from Google Fonts:

```
https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,700;12..96,800&family=Nunito:wght@400;600;700;800&family=Caveat:wght@500;700&family=JetBrains+Mono:wght@500;700&display=swap
```

| Role | Family | Weights | Where |
|------|--------|---------|-------|
| Display / titles | **Bricolage Grotesque** | 700, 800 | `<h1>`, `<h2>`, day titles, section headers |
| Body | **Nunito** | 400, 600, 700, 800 | Body text, checklist items, rules |
| Handwritten | **Caveat** | 500, 700 | Field fill hints, prompt questions, subtitles, tagline, signature |
| Mono / stamps | **JetBrains Mono** | 500, 700 | Passport numbers, dates, codes, page labels, page numbers, seal |

**Type scale** (used):

- 34 pt / 32 pt — cover & back-cover titles
- 22 pt — day titles, memories `<h2>`
- 20 pt — ID `<h2>`, signature
- 18 pt / 17 pt — Caveat subtitles
- 16 pt — cover Caveat fill
- 14 pt / 13 pt — prompt questions, stamp hints
- 12 pt — rules card title, section headers, back-cover body, static values
- 11 pt — section headers
- 10.5 pt / 10 pt — checklist text, rules list, memory card label
- 9 pt — bingo cell label, list-badge number, day tag
- 8 pt — code chip, page number, kicker
- 7.5 pt / 7 pt — page label, foot mono, seal
- 6.5 pt — cover circular stamp, seal main
- 5 pt — seal footer

### Spacing (mm-based print scale)

Print scale uses **millimetres** throughout for print predictability. Common values:

- 1 mm — micro gaps (badge number spacing)
- 2 mm — component radii, small paddings
- 3 mm — icon-to-label spacing, small gaps
- 4 mm — medium gaps, prompt-box padding
- 5 mm — grid gaps (memory cards)
- 6 mm — section vertical rhythm, page-body row gap, section-h-to-content
- 8 mm — checkbox side, section major gaps
- 10 mm — body top padding
- 12 mm — page side gutters, side padding
- 14 mm — page top padding (ID + reflect)

### Border radius

- 1 mm — code chips
- 2 mm — most cards, boxes, memory cards, stamp slots
- 3 mm — cover logo card, doc border
- 50% — circles (stamp, seal, ordered-list badges, bingo icons)
- 999px — top-of-page "Print" button (screen only)

### Shadows

- Cover logo card: `0 4px 10px -4px rgba(0,0,0,.3)`
- Cover Summer School logo card: `0 10px 25px -12px rgba(0,0,0,.35)`
- Cover title text shadow: `0 3px 12px rgba(0,0,0,.15)`
- Screen-only page shadow: `0 20px 40px -20px rgba(0,0,0,.35), 0 8px 16px -12px rgba(0,0,0,.2)` — **must be removed in print output**.

### Print setup

```css
@page { size: A5 portrait; margin: 0; }
.page { width: 148mm; height: 210mm; page-break-after: always; }
```

Every `.page` element is 148 × 210 mm exactly and forces a page break after. No bleed is set — if a commercial printer is used, extend the ochre/sky backgrounds by 3 mm on all sides and add crop marks.

---

## Assets

Two brand logo files ship in `assets/`:

| File | Source | Size | Notes |
|------|--------|------|-------|
| `assets/idss-logo.png` | Provided by the school | 1024 × 311, 68 KB, RGBA (transparent) | Used on cover top-left, on a white card |
| `assets/summer-school-logo.png` | Provided by the school | 774 × 581, 585 KB, RGBA (opaque bg) | Used centred on cover, on a white card. This file has a light gradient background baked in — if a transparent version is available, it should replace this file for a cleaner cover treatment |

No SVG illustrations or photographs are used. All page ornaments (stamp circles, seal, bingo icons) are inline SVG or CSS.

---

## Files

- `IDSS Summer School Passport 2026.html` — the complete 14-page A5 mockup. Self-contained: all CSS is inline in `<style>`, only external dependencies are Google Fonts and the two logo files in `assets/`.
- `assets/idss-logo.png` — school logo.
- `assets/summer-school-logo.png` — Summer School 2026 logo.

To produce the production PDF quickly:

```bash
# Puppeteer example
node -e "const p=require('puppeteer');(async()=>{const b=await p.launch();const g=await b.newPage();await g.goto('file://'+__dirname+'/IDSS Summer School Passport 2026.html',{waitUntil:'networkidle0'});await g.pdf({path:'passport.pdf',format:'A5',printBackground:true,margin:{top:0,bottom:0,left:0,right:0}});await b.close();})()"
```

Or open the HTML in Chrome → Print → "Save as PDF" → A5, no margins, background graphics enabled.
