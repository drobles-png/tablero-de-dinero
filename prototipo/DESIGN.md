---
name: Tablero de Dinero
description: A one-thumb money app that answers how much is left until the next quincena, and per day.
colors:
  ink: "#111111"
  surface: "#FFFFFF"
  surface-2: "#F2F2F2"
  muted: "#5E5E5E"
  line: "#E3E3E3"
  shell: "#111111"
  shell-2: "#2A2A2A"
  on-shell: "#FFFFFF"
  on-shell-muted: "#B5B5B5"
  income: "#1B7A3D"
  income-on-shell: "#6FD394"
  alert: "#C62828"
  alert-soft: "#FDECEA"
  on-alert: "#FFFFFF"
  alert-on-shell: "#FF8A80"
typography:
  display:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "clamp(44px, 14vw, 64px)"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "-0.02em"
    fontVariation: "'wdth' 118"
    fontFeature: "'tnum'"
  figure-input:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "44px"
    fontWeight: 800
    fontVariation: "'wdth' 118"
    fontFeature: "'tnum'"
  headline:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "28px"
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  title:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "18px"
    fontWeight: 700
  amount:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 700
    fontVariation: "'wdth' 110"
    fontFeature: "'tnum'"
  body:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.45
    fontFeature: "'tnum'"
  label:
    fontFamily: "Archivo, Segoe UI, system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 600
rounded:
  bar: "3px"
  tile: "10px"
  field: "11px"
  control: "12px"
  menu: "14px"
  dialog: "18px"
  sheet: "22px"
  pill: "999px"
spacing:
  hairline-gap: "3px"
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  section: "20px"
  band-bottom: "24px"
components:
  button-primary:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.surface}"
    rounded: "{rounded.control}"
    padding: "0 18px"
    height: "46px"
  button-ghost:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    padding: "0 18px"
    height: "46px"
  button-danger:
    backgroundColor: "{colors.alert}"
    textColor: "{colors.on-alert}"
    rounded: "{rounded.control}"
    padding: "0 18px"
    height: "46px"
  button-hold-delete:
    backgroundColor: "{colors.alert-soft}"
    textColor: "{colors.alert}"
    rounded: "{rounded.control}"
    padding: "0 16px"
    height: "46px"
  field:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    rounded: "{rounded.field}"
    padding: "10px 12px"
    height: "46px"
  chip-category:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "0 14px"
    height: "44px"
  chip-category-selected:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.surface}"
    rounded: "{rounded.pill}"
    padding: "0 14px"
    height: "44px"
  band-pill:
    backgroundColor: "{colors.shell-2}"
    textColor: "{colors.on-shell-muted}"
    rounded: "{rounded.pill}"
    padding: "7px 14px"
  initial-tile:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    rounded: "{rounded.tile}"
    size: "36px"
  initial-tile-income:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.income}"
    rounded: "{rounded.tile}"
    size: "36px"
  tab-active:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    height: "54px"
  add-button:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.surface}"
    rounded: "{rounded.pill}"
    size: "56px"
  toast:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.surface}"
    rounded: "{rounded.menu}"
    padding: "4px 16px"
    height: "48px"
---

# Design System: Tablero de Dinero

## Overview

**Creative North Star: "The Black Ledger Band"**

Tablero de Dinero is a black-and-white money tool. The user chose "the category standard" in black and white: the standing exit, the canon path of personal-finance apps, not a rolled concept. That choice was made in another session and replaced the earlier petrol direction that came out of the three-way debate; nothing from the petrol world (petrol band, maravilla accent, per-category colors) carries forward. The brand commitment the user asked for in so many words is the governing rule of this file: **"Interfaz en blanco y negro; verde solo para lo positivo, rojo solo para alertas".**

The screen has three bands. A black top band holds the answer: "Te quedan", the figure, the per-day line, the Entró/Salió pills and the quincena rail. Below it, a plain white page that starts flush under the band (no overlap, no rounded top corners) holds sections separated by hairlines. At the bottom, a white tab bar with a top border and a black + in the middle. Density is calm and phone-first, with a single 720px column on desktop.

Color is reserved for meaning. Everything structural is ink, white or grey; green appears only where money comes in, and red only where something is wrong (negative balance, overspending, deleting). Spending is ink, never red. Motion carries the craft that color no longer does: a drawer sheet you can drag down, a hold-to-delete fill, a clip-path tab indicator, a sliding segmented control, an undo toast, and the rail growing on first load.

**Key Characteristics:**
- Black top band, white page, white bottom bar; strict achromatic structure.
- Green only for income, red only for alerts; spending stays ink.
- Categories are told apart by their initial in a grey tile, not by color.
- Archivo throughout, widened (wdth 118, weight 800) for money figures; tabular numerals everywhere.
- Flat surfaces; shadow only on the floating + and the context menu.
- Motion is functional and fully covered by reduced-motion fallbacks.

## Colors

An achromatic system with exactly two semantic hues, each with a variant tuned for the black band.

### Primary
- **Ledger Ink** (`ink`): text, primary buttons, the + button, selected category chips, the toast, category spending bars, the expense line in the trend chart, text selection background, focus ring.

### Secondary
- **Income Green** (`income`): income amounts in the list, the initial letter on income tiles, bars under Ingresos, the income line and dots in the trend chart. Nothing else.
- **Band Green** (`income-on-shell`): the Entró amount inside the black band, where Income Green would lack contrast.

### Tertiary
- **Month meter ladder:** grey (`muted`) under 90%; at 90% or more it turns ink with the "Cuidado" text in 800 weight, never red; above 100% it turns Alert Red.
- **Overdue scheduled payments:** "Vencido" and its date in Alert Red; that is the only new use of red.
- **Alert Red** (`alert`): negative balance, overspending (the month meter only in its over state, above 100%, and its figure), the Salió pill when spending exceeds income, error text, the Eliminar menu item, the danger button and the hold-to-delete fill.
- **Alert Wash** (`alert-soft`): resting background of the hold-to-delete button, with Alert Red text.
- **Band Red** (`alert-on-shell`): the negative hero figure and over-budget pill amount inside the black band.
- **On Alert** (`on-alert`): text on solid Alert Red.

### Neutral
- **Band Black** (`shell`): the top band and the safe-area strip above it.
- **Band Graphite** (`shell-2`): pills inside the band and month-arrow hover.
- **On Band** (`on-shell`): figures and bold values on the band, the pay-day line, the daily-allowance line.
- **Band Grey** (`on-shell-muted`): band labels, brand name, rail bars (at reduced opacity), rail day numbers.
- **Paper** (`surface`): page, sheet, dialog, menu, bottom bar, segmented-control thumb.
- **Fog** (`surface-2`): fields, ghost buttons, initial tiles, track of meters and bars, the active tab background, hover rows.
- **Graphite Text** (`muted`): secondary text, inactive tabs, labels, table headers, chart axis text.
- **Hairline** (`line`): section dividers, field and chip borders, table rows, the bottom bar's top border, the sheet grabber.

**Dark mode** (via `prefers-color-scheme` or `data-theme="dark"`) keeps the same roles: page #0E0E0E, Fog #1B1B1B, ink #F2F2F2, muted #A3A3A3, hairline #2B2B2B, band #1C1C1C with graphite #333333, income #5CC98A, alert #FF7A6E with wash #3A1A18 and dark on-alert #1A0A08. The rail's "today" bar uses a white accent (#FFFFFF) in both modes. Values live in the sidecar.

### Named Rules
**The Two Hues Rule.** The interface is black and white. Green appears only for income, red only for alerts. No third hue, no decorative tint, no brand accent.

**The Spending Is Ink Rule.** An expense is never red. Red means a problem (negative, overspending) or a destructive act. Expense amounts, bars and the expense trend line are ink.

**The Initial, Not Color Rule.** Categories have no color in the interface. A category is marked by its uppercase initial in a 36px Fog tile; the letter turns Income Green for income categories. Do not reintroduce swatches, color pickers or colored dots.

## Typography

**Display Font:** Archivo (variable width and weight), with Segoe UI, system-ui fallback
**Body Font:** Archivo

**Character:** One family doing everything. Figures widen to 110-118% and go heavy so money reads as the loudest thing on the screen; words stay at normal width and medium weights.

### Hierarchy
- **Display** (800, clamp(44px, 14vw, 64px), wdth 118, line-height 1): the hero figure in the band ("Te quedan" amount or month balance).
- **Figure input** (800, 44px, wdth 118): the amount field in the sheet, with a 32px muted "$".
- **Headline** (700, 28px, line-height 1.1): the band title on Movimientos, Categorías and the empty state.
- **Title** (700, 18px; 19px in sheet and dialog headings): section headings on the page.
- **Amount** (700, 16px, wdth 110): movement amounts; category totals use 700 at wdth 110 at body size.
- **Body** (400, 15px, line-height 1.45): everything else; empty-state copy capped at 46ch.
- **Label** (600, 13px): field labels, day headers in the list, table headers, legend; tab labels are 600 at 12px. Sentence case, no tracking.

### Named Rules
**The Wide Money Rule.** Money figures are Archivo at wdth 110-118 and weight 700-800; prose never is.

**The Tabular Rule.** The body sets `tabular-nums`, so every amount aligns in columns and does not jitter while typing.

## Layout

A single column capped at 720px (`wrap-w`), centered, with 16px side gutters that grow to the safe-area inset. The black band runs edge to edge (10px top, 24px bottom padding) with a safe-area strip painted in band black above it. The page begins directly under the band, with no negative margin and no rounded top corners, and leaves 112px plus the bottom safe area for the tab bar.

Page sections stack with 20px block padding and a hairline between consecutive sections; inside, gaps step 8 / 10 / 12 / 14px. Section headers are 44px-tall rows with the heading left and a text link right.

The quincena rail is a grid of equal columns with 3px gaps: each day is a 64px bar area plus a 12px day number. The bottom bar is a 560px-max grid of two tabs, a 76px slot for the +, and Categorías centered in the remaining half, so the + sits at the exact center.

At 640px and up the sheet stops being a bottom drawer and becomes a centered 540px floating card 24px above the bottom edge.

Every interactive target is at least 44px.

## Elevation & Depth

Flat by default. Depth comes from the band/page contrast, Fog fills and hairlines, not from shadow. Only two elements cast a shadow, both because they float over content.

### Shadow Vocabulary
- **Floating action** (`box-shadow: 0 4px 14px rgba(0, 0, 0, .18)`): the black + in the bottom bar.
- **Popover** (`box-shadow: 0 10px 30px rgba(0, 0, 0, .16)`): the ⋯ context menu.

Overlays (sheet, dialog) sit on a scrim (rgba(0,0,0,.5); .65 in dark) instead of a shadow.

### Named Rules
**The Two Shadows Rule.** Only the + button and the context menu carry shadow, and both are soft and blurred. Cards, sections and the bottom bar stay flat; the bar separates with a hairline.

## Shapes

Gently rounded controls (12px) with a consistent family: tiles 10px, fields 11px, menus and toast 14px, dialog 18px, sheet 22px on its top corners (all corners on desktop). Pills and chips are fully round; the + is a circle. Rail bars have 3px tops and 1px bottoms. Meters and category bars are full-round 10px and 6px tracks. The pay-day marker in the rail is not a bar but a 2px dashed vertical line; the daily-allowance line is a 1px dashed horizontal rule at 70% opacity. Section edges are hairlines, never boxes: the page does not use cards.

## Components

### Buttons
Solid and quiet: black slabs, no gradients.
- **Shape:** gently rounded (12px), 46px tall, 18px side padding, weight 700.
- **Primary:** Ledger Ink background, Paper text.
- **Ghost:** Fog background, ink text.
- **Danger:** Alert Red with On Alert text, used in confirmation dialogs.
- **Press:** every button scales to .97 on press (140ms ease-out); disabled is 50% opacity.
- **Focus:** 2px ink outline, 2px offset (white outline on the band).
- **Text link:** ink, 600 weight, underlined 4px below with a muted underline.

### Hold to delete
A pale red button (Alert Wash fill, Alert Red text). Holding it sweeps a solid Alert Red layer across with `clip-path: inset()` over 1.2s linear; releasing early springs it back in 200ms. Completing it deletes, then the toast offers undo.

### Chips
- **Category picker (in the sheet):** 44px pills with a hairline border and no color mark. Selected: ink fill, ink border, Paper text.
- **Band pills:** Band Graphite pills holding "Entró" and "Salió" with the amount in bold. Entró's amount is Band Green; Salió's amount is On Band, or Band Red when spending exceeds income.

### Initial tile
The category mark: a 36px Fog square (10px radius) holding the category's uppercase initial at 700/14px in ink, or Income Green for income categories. Leads each movement row and each category row.

### Lists
- **Movement row:** 36px tile, name over muted note, amount right. 56px min height, 10px radius hit area; Fog on hover and press (press also scales to .985). Income amounts green, expenses ink.
- **Category row:** tile, name over muted count, ⋯ button right; 60px rows separated by hairlines.
- **Category bars:** name and total over a 6px Fog track; the fill is ink, or Income Green under Ingresos. Bars grow from the left on first load.

### Inputs / Fields
- **Style:** Fog fill, hairline border, 11px radius, 46px height, 16px text (avoids iOS zoom). Selects and dates carry a masked muted chevron or calendar icon at the right.
- **Focus:** 2px ink outline, border goes transparent.
- **Amount field:** borderless figure input over a 2px hairline underline that turns ink on focus.
- **Error:** Alert Red text at 14px below the form.

### Segmented control
A Fog track (12px radius, 4px padding) with a Paper thumb with hairline border (9px radius) that slides between options in 240ms ease-in-out. Inactive labels muted, active ink.

### Navigation
- **Bottom bar:** fixed, Paper with a hairline top border. Tabs are icon over 12px label, muted at rest.
- **Active tab:** a duplicate layer of the bar in active style (ink text on Fog) is clipped with `clip-path` to the current tab; switching tabs animates the clip in 220ms ease-in-out.
- **Add:** a 56px black circle with a white plus and the floating-action shadow; presses to .93.
- **Month switcher:** on the band, 44px chevron buttons around the month name; graphite hover.

### Signature: the quincena rail
One bar per day of the current pay cycle, ending on pay day. Past bars are Band Grey at 60% opacity, future days at 22%, today is a solid white bar with a bold white day number, and pay day is a full-height 2px dashed white line. When the daily allowance fits in the scale, a dashed white rule marks it. On first load the bars grow from the bottom, staggered 22ms per day. A caption below says what was spent this quincena.

### Sheet, dialog, menu, toast
- **Sheet:** bottom drawer, 22px top corners, slides up in 420ms on the drawer curve; drag the head down to dismiss. Focus is trapped and returns to the trigger.
- **Dialog:** centered 420px card, 18px radius, 22px padding, fades and settles from slight scale.
- **Context menu:** grows from its ⋯ trigger (origin top right, scale .96 to 1). Items: Renombrar, Eliminar (red).
- **Toast:** ink pill above the bar with an underlined "Deshacer"; pauses its timer on hover.

## Do's and Don'ts

### Do:
- **Do** keep every structural element in ink, Paper, Fog, Graphite Text or hairline; use green only for income and red only for alerts.
- **Do** mark categories with their initial in a Fog tile; turn the letter green for income.
- **Do** use the band-tuned variants (Band Green, Band Red) for color on the black band.
- **Do** set money in Archivo at wdth 110-118, weight 700-800, with tabular numerals.
- **Do** make primary actions ink with Paper text, and the selected chip ink-filled.
- **Do** give every animation a reduced-motion fallback (fade or none), as the build does.
- **Do** keep targets at 44px or more.

### Don't:
- **Don't** color an expense red; red is for negative, overspending and deleting.
- **Don't** show category colors anywhere in the interface: no swatches, dots, colored bars or "Cambiar color".
- **Don't** add a brand accent hue, tint the band, or reintroduce petrol or maravilla.
- **Don't** overlap the page onto the band or round the page's top corners.
- **Don't** add shadows to cards, sections or the bottom bar; only the + and the context menu float.
- **Don't** decorate with Ecuadorian folk imagery (flags, volcanoes, sucres); the local character lives in the quincena logic and the language.
