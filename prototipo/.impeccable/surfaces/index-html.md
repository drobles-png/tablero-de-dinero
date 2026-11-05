---
version: 1
slug: "index-html"
primary_target: "index.html"
related_targets: []
---

# Surface: Tablero de Dinero (index.html)

Mode: Operate. A phone app for logging and checking personal finances, one-handed.
Job: log a movement in seconds; see how much is left until the next pay day.
Constraints:
- A single-file claude.ai artifact.
- Archivo from Google Fonts.
- A private db per user.
- Keep the existing motion: the drawer, hold to delete and the clip-path tabs.

## Direction contract

THESIS: The app answers "how much is left until the 15th or the 30th" and does not show a monthly balance dressed as a fintech card. It never uses red for normal spending.

OWN-WORLD:
- Black and white, the category standard, as the user chose on 2026-10-23. It replaces the earlier petrol and maravilla world.
- A black band holds the answer.
- The white page sits below the band, sections are separated by 1px hairlines, and the bottom bar is white with a top border.
- Black primaries, including the round + button.
- Green only for income and positive figures; red only for alerts and deleting.
- Categories have no color in the interface. Each is shown as a grey tile with its initial.
- Archivo throughout, with the wide 800 cut reserved for figures.

STORY: Open the app and in one glance you know how much is left and per day. You see how this quincena is going day by day against your daily limit. Log with the thumb in the middle of the bottom bar. Delete with undo.

FIRST VIEWPORT:
- The black band holds the brand and a month selector with 44px arrows.
- Then "Te quedan $X" in wide Archivo at about 56px, and "unos $Y por día hasta el 30".
- Then the Entró/Salió pills, with Entró in green.
- Then the quincena rail: grey bars, today in white, the pay day as a dotted line, and the daily limit as a dashed line when it falls within the scale.
- Below that, the white page with the month meter and the trend.
- The black + sits in the center of the bottom bar.

FORM: The category standard ("canon"), taken by the user in place of the petrol direction that came out of the three-way debate. There was no roll, so there is no seed key. Signature move: the quincena rail, whose bars grow on the first load.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance
