# Design System Inspired by WISEITECH

> Category: Enterprise & Consulting
> Korean enterprise IT proposal template. Navy authority, blue gradients, document-dense formality.

WISEITECH takes the Korean SI (system-integration) proposal deck as its base, then sharpens it through navy-and-blue corporate authority, dashed-guide document density, and rigid hierarchical structure. It is a strong fit for B2B proposals, government tenders, audit reports, and any deliverable where formality, traceability, and information density beat marketing flair.

---

## 1. Visual Theme & Atmosphere

Formal, structured, document-dense — the aesthetic of a printed 제안서 (proposal). The page reads top-to-bottom like a technical document, not a marketing slide. Every content area is bounded by a thin dashed red guideline, every page is numbered by chapter (`I-2`, `II-5`, `III-7`), and a quiet sidebar runs a Roman-numeral chapter index down the right edge. Authority comes from saturation, not motion: a single deep navy band anchors every chapter cover, a brighter sky-blue ribbon anchors every content section, and a small red accent is held in reserve for warnings and key emphasis. Whitespace is generous around hero areas but tight inside content blocks — information density is a feature, not a bug. Negative space carries the chapter dividers; the body slides commit to packed, gridded layouts with multiple cards, callouts, and a summary table per page. Atmosphere is corporate-Korean, late-2010s SI consultancy: trustworthy, methodical, slightly clinical.

---

## 2. Color Palette & Roles

```css
/* Primary — Navy authority (chapter bands, headers, page furniture) */
--navy-900:        #003366;  /* deepest, chapter cover band */
--navy-800:        #00519A;  /* section header fill */
--navy-700:        #0568B0;  /* link / sub-bar fill */
--navy-600:        #006699;  /* alt-tone navy */

/* Secondary — Sky accent (KEY pills, ribbons, highlighted cards) */
--sky-500:         #0070C0;  /* solid sky accent */
--sky-400:         #61AEDD;  /* primary highlight ribbon */
--sky-300:         #A9D3ED;  /* sub-bar 2nd row */
--sky-200:         #C8E3F4;  /* hover / chip fill */
--sky-100:         #DCEDF8;  /* table zebra, soft surface */
--sky-050:         #B8CBF2;  /* lavender-blue chip */
--sky-steel:       #7A9FCB;  /* muted steel-blue tag */

/* Accent — Red emphasis (warnings, "긴급", dashed guides, key terms) */
--red-700:         #C00000;  /* core emphasis red, "강조" text */
--red-600:         #CC0000;  /* alt warning fill */
--red-500:         #FF3300;  /* hottest call-out, "긴급장애발생" */

/* Neutrals — Document grays */
--ink-900:         #111111;  /* near-black, headings */
--ink-800:         #292929;  /* default body text */
--ink-700:         #4D4D4D;  /* secondary text */
--ink-500:         #777777;  /* tertiary / footnote */
--ink-400:         #969696;  /* divider / disabled */
--rule-300:        #DDDDDD;  /* horizontal rule, table border */
--surface-200:     #EAEAEA;  /* sidebar tab inactive */
--surface-100:     #F0F0F0;  /* card / row fill */
--surface-050:     #F8F8F8;  /* alt row, info panel */
--bg:              #FFFFFF;  /* page canvas */

/* Functional roles */
--bg-page:         var(--bg);
--bg-chapter:      var(--navy-900);
--bg-section-bar:  var(--sky-400);
--bg-sub-bar:      var(--sky-100);
--text-default:    var(--ink-800);
--text-muted:      var(--ink-500);
--text-emphasis:   var(--red-700);
--text-on-navy:    #FFFFFF;
--border-card:     var(--rule-300);
--border-guide:    var(--red-700);   /* the dashed content-frame */
--accent-key:      var(--sky-500);   /* KEY pill, bullet check */
```

Dominance rule: **navy + white must occupy ~60% of any page's visual weight, sky-blue ~25%, gray ~10%, red ≤5%**. Red is a spice, never a base.

---

## 3. Typography Rules

**Korean stack (primary):** `"KoPub돋움체 Bold", "KoPub돋움체 Medium", "KoPub돋움체 Light", "산돌고딕B", "맑은 고딕", "Malgun Gothic", "굴림", sans-serif`
**Latin stack (numerals, labels, "CHAPTER", "Strategy"):** `"Futura Md BT", "Futura", "Helvetica Neue", Arial, sans-serif`
**Fallback display (titles only):** Arial Black where KoPub Bold is unavailable.

KoPub돋움체 is the Korean Publishers Society's free Gothic family — pick it (or 본고딕 / Noto Sans KR) if licensing matters. Never substitute a serif; this aesthetic refuses serifs entirely outside the decorative "전략" brushstroke headers.

| Token | Size | Weight | Family | Use |
|-------|------|--------|--------|-----|
| `display-xxl` | 62pt | Bold | Futura Md BT | Chapter Roman numeral (Ⅰ Ⅱ Ⅲ) on cover slides |
| `display-xl` | 44pt | Bold | KoPub Bold | Chapter cover title |
| `title-lg` | 30pt | Bold | KoPub Bold | Slide title in the navy band |
| `title-md` | 22pt | Bold | KoPub Bold | "가. 제목을 입력하세요" sub-section title |
| `subhead` | 18pt | Medium | KoPub Medium | "1. 제목" numbered list head; KEY pill body |
| `body` | 11pt | Light | KoPub Light | Default paragraph & table body |
| `body-sm` | 10pt | Light | KoPub Light | Footnote, secondary cell |
| `caption` | 9pt | Light | KoPub Light | Page number, "※ 내용을 입력하세요" footnote |
| `tag` | 11pt | Medium | KoPub Medium | Chip / pill text ("텍스트", "메인칼라") |
| `latin-label` | 11pt | Bold | Futura Md BT | "CHAPTER", "Strategy", "KEY Point" sidebar labels |

Body line-height: **1.45** for Korean (Hangul needs more leading than Latin). Title line-height: **1.2**. Letter-spacing: leave at `0` — Korean type breaks visually with tight tracking. Numbered lists (`1.` `2.` `가.` `나.`) use a 0.75em indent after the marker.

---

## 4. Component Stylings

### Slide title band (every content slide)
- Sidebar tab: rectangle, 100×64px, `--surface-200` fill, contains the chapter Roman numeral as `display-xxl` clipped + a stack of small navy squares (one filled per chapter passed).
- Main bar: full-width to the right of the tab, 64px tall, white background, bottom border `2px solid --navy-700`.
- Title text: `title-lg`, `--ink-900`, left-aligned, 24px from the tab edge.

### Section header — "중간바" (mid-bar)
- Pill: pill-radius (32px), height 32px, fill `--sky-400`, white text, `subhead` size.
- Left affix: a 28px navy square with white "KEY" text in Futura — sits half-overlapping the pill's left edge.
- Used once per content section to introduce the main point.

### Sub-section bar — "소제목바"
- Solid bar, 24px tall, fill `--sky-100`, left-aligned text in `--navy-800`, `subhead` weight.
- Tiny 4px navy triangle on the left edge (the "▶" arrow tip).

### KEY callout block
- Rounded rectangle, radius 8px, fill `--surface-050`, 1px `--rule-300` border.
- Left strip 6px wide, fill `--sky-500`, full-height.
- Header row: `subhead`, navy. Body rows: `body`, gray. Italic decorative quotes (`66` / `99`) flank the header in muted gray.

### Buttons & tags (rendered as proposal chips, not interactive)
- Solid chip: fill `--navy-800`, white text, radius 4px, padding 6/14, `tag` size.
- Outline chip: fill white, 1px `--navy-800` border, text `--navy-800`, same radius/padding.
- Soft chip: fill `--sky-200`, text `--navy-900`, no border.
- Red emphasis chip ("긴급장애발생", "제안+", "SAMPLE"): fill `--red-700`, white text, radius 4px, often with a small white "+" or notch ornament. Use sparingly.

### Cards
- Default card: fill `--surface-050`, 1px `--rule-300` border, radius 6px, internal padding 16px, no shadow.
- Highlight card: fill white, 2px `--sky-400` left border, no other border.
- Stat / icon row: 32px navy filled circle + bold navy label + 11pt gray description, three-column grid.

### Tables (the signature element)
- Header row: fill `--navy-800`, white text, `subhead` weight, KoPub Bold.
- Body rows: white / `--sky-100` zebra. 1px `--rule-300` cell borders.
- Cell padding: 10px vertical, 14px horizontal.
- First-column emphasis cells: fill `--surface-100`, bold ink-900.
- Footnote row at bottom in `body-sm`, `--ink-500`, prefixed with `※`.

### Page furniture
- Top-right: three small navy circles containing white IT icons (monitor, magnifier, server) — the WISEITECH mark group.
- Top-right text: `caption`, "사업명을 입력하세요" placeholder, right-aligned, `--ink-500`.
- Right edge: vertical chapter index `I II III IV V VI VII`, current chapter in `--sky-400` and 2x size, others in `--ink-400`.
- Bottom-right: `WISEITECH` logo lockup.
- Bottom-center: page number "I-2" style — Roman chapter + dash + page index, `caption`, `--ink-700`.
- Content frame: 1px dashed `--red-700`, inset 24px from page edges, surrounding all body content.

### Navigation (TOC) on chapter covers
- Dark navy band (`--navy-900`) covering the middle horizontal third of the slide.
- White "Chapter" label + huge Futura Roman numeral (Ⅰ–Ⅶ) flush left at 62pt, white.
- Numbered list `1. 제목을 입력하세요` × 4, 22pt, `--ink-800`, in the lower-right white area.
- Left third is a flat `--surface-100` panel — the "binder spine" reference.

---

## 5. Layout Principles

- **Page:** 4:3 PowerPoint canvas (25.4cm × 19.05cm / 960×720px). Print-derived; do not redesign for 16:9 unless explicitly asked.
- **Margins:** 1.5cm outer, with the dashed red content frame inset another 0.4cm.
- **Grid:** 12-column logical grid; in practice deck uses two macro zones — a 64px-tall title band on top, then a single content well below. Inside the well, free-form modules align to a 4-column sub-grid.
- **Spacing scale:** `4 / 8 / 12 / 16 / 24 / 32 / 48` px. Use 8/16 inside cards, 24 between cards, 32 between sections, 48 above the section bar.
- **Whitespace philosophy:** maximalist *inside* content slides (use every cm), minimalist on chapter covers (let one navy band carry the whole page). Never center body content; only titles and chapter Roman numerals are centered.
- **Page numbering:** every content slide carries chapter Roman + page index. Chapter covers carry only the section name, no page number.
- **Alignment:** left-align everything Korean; left-align numbers in tables (Korean convention often differs from Western right-align for numerics — follow the template).
- **Cap rule:** maximum one KEY block, one section bar, two sub-section bars per slide. Beyond that, split the slide.

---

## 6. Depth & Elevation

This system is **flat by default — no drop shadows, no glows, no gradients on UI surfaces**. Depth is signaled through:

| Layer | Technique |
|-------|-----------|
| Page (z=0) | White canvas. |
| Frame (z=1) | 1px dashed red content guide. |
| Surface (z=2) | `--surface-050` / `--surface-100` fills, no border or 1px `--rule-300`. |
| Header band (z=3) | Solid navy or sky color block — color is the elevation. |
| KEY pill (z=4) | Pill overlapping the section bar; the overlap itself is the visual lift. |
| Chapter cover (z=∞) | Edge-to-edge `--navy-900` band crossing the page horizontally. |

The only acceptable gradient is a **subtle navy → sky-blue linear-gradient (135°) on the KEY pill and chapter title band**, and only at 90 → 100% opacity. Never apply gradients to text, body cards, or backgrounds. Diagonal "speed lines" (three thin parallel white strokes at 30°) may decorate the right edge of the chapter band as a single ornament — do not repeat it elsewhere.

Borders carry hierarchy: 2px navy bottom-border under titles, 1px gray cell borders in tables, 1px dashed red around the whole content area. That dashed red border is the deck's signature — do not remove it.

---

## 7. Do's and Don'ts

**Do:**
- Keep the dashed red content frame on every content slide; it is the visual signature.
- Use the chapter Roman numeral + page number footer on every content slide.
- Let navy dominate; sky-blue accent; red for warnings and key emphasis only.
- Stack two parallel bars (`중간바` then `소제목바`) to introduce nested topics.
- Pair every numeric chip / stat with a Futura Latin label and a KoPub Korean caption underneath.
- Anchor each slide to one summary table at the bottom — it doubles as the "이행 결과" record.
- Keep KoPub for Korean, Futura for Latin. Mixing inside a single sentence is expected.

**Don't:**
- ❌ Don't switch to 16:9 or pad-edge layouts unless the user explicitly asks.
- ❌ Don't add drop shadows, glows, or "glassmorphism" — this is a printed-document aesthetic.
- ❌ Don't introduce pastels, mint, lavender, or any palette outside navy/sky/red/gray.
- ❌ Don't use serifs anywhere. No exceptions.
- ❌ Don't center body text or numbered lists — only titles and chapter numerals are centered.
- ❌ Don't pile more than one KEY pill per slide; it loses meaning fast.
- ❌ Don't replace the red dashed frame with a solid border — the dashed pattern is intentional document furniture.
- ❌ Don't use red for anything other than emphasis, warning, or the content frame; never as a fill for a major surface.
- ❌ Don't tighten Korean letter-spacing — Hangul fractures visually below 0.
- ❌ Don't drop the WISEITECH-style "three navy icon circles + project-name placeholder" header — that block is the slide's identity.

---

## 8. Responsive Behavior

This is a **fixed-canvas print-oriented system** (4:3 PowerPoint, 960×720px). It does not natively reflow. When porting to web:

| Breakpoint | Strategy |
|------------|----------|
| ≥1280px (desktop) | Render the slide at 960×720 inside a `--surface-100` mat, 1:1 to the original. |
| 1024–1279px | Scale the entire slide proportionally; do not reflow. |
| 768–1023px (tablet) | Drop the right-edge Roman chapter index; expose it as a top breadcrumb. Keep the dashed frame, scale type 90%. |
| 480–767px (mobile) | Break the content well into a vertical stack: title → section bar → KEY block → cards (one per row) → table (scroll-x). Drop the sidebar tab; collapse the chapter-band cover into a single full-bleed navy hero. |
| <480px | As mobile; force the dashed red frame to 12px inset; force the table to horizontal-scroll instead of wrapping cells. |

Touch targets: any chip used interactively (web port) must be enlarged to ≥40×40px hit area while keeping the visual chip at its print size. Do not enlarge the rendered chips themselves — that breaks the document feel.

The chapter cover slide is the only piece that **must reflow** on mobile: the Roman numeral becomes a top-left corner mark, the navy band becomes a full-height left strip, and the 4-item TOC becomes the body.

---

## 9. Agent Prompt Guide

### Quick color reference
```
Navy authority:    #003366  /  #00519A  /  #0568B0
Sky accent:        #61AEDD  /  #0070C0  /  #C8E3F4
Red emphasis:      #C00000  (use only for warnings & key terms)
Text default:      #292929
Body surface:      #F8F8F8 / #F0F0F0
Page:              #FFFFFF
```

### Ready-to-use prompts

**For a new content slide:**
> "Generate a Korean enterprise proposal slide in the WISEITECH style. Use the dashed red content frame, navy title band with the chapter Roman numeral in the left sidebar tab, the three-navy-circle icon group + project name top-right, a sky-blue 중간바 section bar with a navy KEY pill overlapping its left edge, a sub 소제목바 underneath, and a footer with `[Chapter]-[Page]` style numbering and a WISEITECH-style logo lockup bottom-right. Type: KoPub돋움체 for Korean, Futura Md BT for Latin labels. No shadows, no gradients (except the KEY pill), no serifs."

**For a chapter cover:**
> "Generate a Korean proposal chapter divider. Layout: left third is a flat light-gray panel; middle horizontal band is solid `#003366` navy carrying white text — the word 'Chapter' in Futura small-caps and a 62pt Futura Roman numeral (Ⅰ through Ⅶ). Right edge has three thin white diagonal speed lines at 30°. Below the navy band, four numbered Korean section titles (`1. 제목을 입력하세요` × 4) in 22pt KoPub Medium ink-800. No dashed frame on chapter covers. No page number."

**For a data table:**
> "Render a WISEITECH-style proposal table. Header row: navy `#00519A` fill, white KoPub Bold text. Body rows: alternating white and `#DCEDF8`. 1px `#DDDDDD` cell borders. First column emphasized with `#F0F0F0` fill and KoPub Bold. Add a footnote row beneath, prefixed `※`, in 9pt KoPub Light gray `#777777`. Numbers left-aligned (Korean convention in this template)."

### Rejection clause
If the user asks for "warmer" colors, gradients, glassmorphism, 16:9 widescreen, sans-serif substitution with Latin-only fonts (e.g., Inter alone), drop shadows, or pastel palettes — refuse and propose the closest in-system alternative. This system is intentionally severe; softening it breaks the proposal-document genre it was built for. Confirm with the user before deviating from the navy / sky / red / gray quartet or removing the dashed red content frame.
