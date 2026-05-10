# Developer Onboarding — Training Deck (Editable Copy)

A 5-slide developer onboarding training deck in a red-and-white documentation aesthetic. Refactored to use a **shared stylesheet** plus a **reusable slide template** so the whole deck stays consistent and easy to update.

## File structure

```
developer-onboarding-copy.slides/
├── manifest.json              # Deck metadata, canvas size, slide order
├── README.md                  # This file
├── assets/
│   └── deck.css               # Shared design tokens, type scale, components
└── slides/
    ├── _template.html                      # Starter file — copy to add a new slide
    ├── cover.html                          # 01 — Title cover
    ├── goals-and-access.html               # 02 — Onboarding goals + required access
    ├── local-setup.html                    # 03 — 4-step setup workflow
    ├── verification-troubleshooting.html   # 04 — Verify + common issues table
    └── first-week-readiness.html           # 05 — Readiness checklist + next steps
```

## Canvas

- **Size:** 1920 × 1080 px (16:9)
- **Each slide** is a self-contained HTML document that links to one shared stylesheet (`../assets/deck.css`) and Google Fonts.

## Shared stylesheet — `assets/deck.css`

All recurring colors, typography, and components are defined once. Edit a token here and the whole deck updates.

### Design tokens (CSS custom properties)

| Token | Value | Usage |
|---|---|---|
| `--c-red` | `#C8102E` | Primary red — accent strips, step numbers, CTA cards |
| `--c-red-deep` | `#8B0A1F` | Section labels, dark red accents |
| `--c-red-wash` | `#FCEAEC` | Soft red — subtle card backgrounds |
| `--c-white` | `#FFFFFF` | Page background |
| `--c-ink` | `#1A1A1A` | Primary text |
| `--c-body` | `#4A4A4A` | Secondary text |
| `--c-mute` | `#8A8A8A` | Footer counter |
| `--c-rule` | `#E5E5E5` | Dividers, card borders |
| `--c-code-bg` | `#1A1A1A` | Terminal block background |
| `--c-code-text` | `#FCEAEC` | Terminal block text |
| `--f-sans` | Manrope | Headings + body |
| `--f-mono` | JetBrains Mono | Step numbers, labels, code |

### Typography helpers

`.kicker` · `.kicker-sm` · `.kicker-xs` — uppercase mono section labels  
`.title-xl` · `.title-lg` · `.title-md` · `.title-sm` · `.title-xs` — heading scale  
`.subtitle` · `.lead` — supporting paragraphs  
`.body-lg` · `.body-md` · `.body-sm` · `.body-xs` · `.body-tag` — body sizes  
`.step-num` — large mono step number (use `.step-num.on-red` on red cards)

### Component helpers

`.top-rule` — 8px red rule across the top of every interior slide  
`.footer-rule` + `.footer-counter` — bottom divider and slide counter pair  
`.title-rule` — short 80×3px red underline beneath section labels  
`.card-plain` — white card with subtle gray border  
`.card-wash` — soft red wash with red left bar  
`.card-red` — solid red CTA card  
`.code-block` + `.code-text` — terminal block with `.prompt` for the `$`  
`.on-red` / `.on-red-soft` — color helpers for content layered on red

## Reusable slide template

Use `slides/_template.html` as the starting point for any new slide:

1. Copy `_template.html` to a new descriptive name (e.g. `release-process.html`).
2. Update `<title>` and the `data-screen-label` on `.slide-container`.
3. Update the section label, slide title, and subtitle in the marked spots.
4. Replace the **CONTENT BLOCK** placeholder with your slide-specific data-objects.
5. Update the footer counter (e.g. `06 / 06`).
6. Add the new filename to the `playlist` in `manifest.json`.

The template ships with the standard top rule, section label, title, subtitle, and footer counter pre-wired and using the shared classes — you only have to fill in the middle.

## Slide structure conventions

Every slide follows this skeleton so it stays editable:

```html
<link rel="stylesheet" href="../assets/deck.css">

<div class="slide-container" data-screen-label="NN Section"
     style="position:relative; width:1920px; height:1080px; overflow:hidden; background:#FFFFFF;">
  <!-- shapes (z-index:1) -->
  <!-- textboxes (z-index:10) with position:absolute; left:Npx; top:Npx; -->
</div>
```

- **Position is inline** (authoritative `left`/`top`/`width`/`height`).
- **Look-and-feel is a class** (`.title-lg`, `.card-wash`, etc.) — this is what removes the duplication.
- Each visual block is a single `<div data-object="true">` so the structure stays predictable.

## How to edit

### Change a color across the whole deck
Edit the `--c-red`, `--c-red-deep`, or `--c-red-wash` value in `assets/deck.css` once — every slide picks it up.

### Change a font size or weight everywhere
Edit the relevant helper class (e.g. `.title-lg`) in `assets/deck.css`.

### Change copy on a single slide
Open the slide HTML and edit the text inside the textbox tags. Leave the surrounding inline `style="..."` (positions) and `class="..."` (look-and-feel) attributes alone.

### Add a checklist item
Find the readiness textbox in `first-week-readiness.html` and copy one `<div>☐ &nbsp;...</div>` line.

### Reorder slides
Edit the `playlist` array in `manifest.json` — do not rename the HTML files.

## Replacing the placeholders

Bracketed values to swap before presenting to a real team:

- `[Repository URL]` → your actual repo URL
- `[Repo Folder]` → cloned folder name
- `[ticket]` → your ticketing prefix (e.g. `JIRA-123`)
- `Team Lead`, `Engineering Manager`, `Developer Experience` → real role/contact names

## Version

- **v1.1 — Refactored.** Same content, structure, and red-and-white design as v1.0, with shared `deck.css` + `_template.html` for easier maintenance.
