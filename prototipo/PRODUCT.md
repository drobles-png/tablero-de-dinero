# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Delegated: a single self-contained HTML file published as a claude.ai artifact (no build step). Storage is the artifact `db` capability, private per user under `data/users/<id>/`, with a localStorage fallback when the page opens outside claude.ai. The artifact CSP allows scripts only from cdnjs/jsdelivr/unpkg and fonts only from Google Fonts.

## Users

Today one person, the owner, in Ecuador. The goal is to validate the prototype with real users and later sell it. They log their own income and spending from their phone, often in short moments between other things, and check the state of their money during the pay cycle. They also open it from a computer.

## Product Purpose

Bring all income and spending into one place. Each movement goes into a category the user defines, separately for income and for spending. The app answers "how much do I have left until my next pay?" and shows where the money went. It succeeds when logging a movement takes a few seconds and the dashboard answers that question at a glance.

## Positioning

- What users value most is knowing how much they can really spend. PocketGuard's "Leftover" proves it. Our "te quedan $X por día hasta el cobro" is the advantage over the competition and stays at the center: it is what I can really spend until the next pay, once scheduled payments are discounted and savings are left out.
- These apps are abandoned because logging by hand turns into a chore. Ecuador has no open banking connection, so manual logging is unavoidable and has to be very fast (2 taps).
- Reference: Sumlio (multiple accounts, hideable balance, categories with totals, scheduled payments, budgets, export). Not to copy from it: a "Más" tab where everything gets dumped, multicolor icons and charts, and empty screens that only say "Vacío".

It is built around the Ecuadorian pay rhythm. The user is paid by quincena (the 15th and the 30th), so the main reading is the money left until the next pay day and per day, not just the monthly balance.

## Operating Context

- Mostly one-handed phone use, plus occasional desktop use.
- Currency: US dollars, written in US style ($1,234.50), as Ecuadorian banks and receipts do.
- Interface language: Spanish (Ecuador), addressing the user as "tú".

## Capabilities and Constraints

- Log an income or an expense: amount, category, date and an optional note.
- Edit and delete movements.
- Create, rename and delete categories, separately for income and for spending. Categories have no color in the interface.
- Dashboard for the selected month.
- Movement list with filters.
- Navigate between months.
- Destructive actions use a hold-to-delete gesture.
- Undecided: budgets per category, recurring movements, export.

## Brand Commitments

- Name: "Tablero de Dinero".
- Spending is normal. Red never means "you spent"; it means a problem (overspending, a negative balance) or deleting.
- The Ecuadorian character lives in the logic (quincena) and in the language, never in folk decoration such as flags, volcanoes or sucres.
- The interface is black and white. Green only for what is positive (income) and red only for alerts. This was asked for explicitly by the user (2026-10-23), choosing the category standard.

## Business Model

Planned freemium. The prices are a hypothesis to validate. **The prototype builds no payment and no lock: everything is available so it can be validated with users.**

- **Free:**
  - Te quedan por día and the quincena rail.
  - Unlimited logging.
  - Custom pay days.
  - Hide balance.
  - 2 accounts.
  - Up to 3 scheduled payments.
  - Unlimited categories.
  - Statistics for the month and for 6 months.
- **Pro, $2.99/month or $24.99/year:**
  - Unlimited accounts and scheduled payments.
  - Budgets per category with alerts at 90% and 100%.
  - Savings goals.
  - Full history and yearly statistics.
  - Export to Excel/CSV.
  - Sharing with a partner or family.

## Project Structure

- `tablero-de-dinero/prototipo/` holds the prototype: the artifact `index.html`, PRODUCT.md, DESIGN.md and `.impeccable/`.
- Later, `backend/` and `frontend/` will go in `tablero-de-dinero/` for the version to be sold, built with /constructor-web-bakano. Prototype work never touches those folders.

## Evidence on Hand

There are no real data in the code. The user's records live in the artifact's private db, and the page must never ship invented records as if they were the user's.

## Product Principles

1. Logging is the main act. It must be quick and done with one thumb.
2. Answer the real question first: how much is left, and per day, until the next pay.
3. Color carries meaning, never alarm for normal spending.
4. Every destructive action can be undone or redirected, and never leaves data orphaned.

## Accessibility & Inclusion

- WCAG AA contrast.
- Touch targets of at least 44px.
- The sheet works with the keyboard and a screen reader: focus is trapped inside and returns to the trigger.
- Every gesture-only action has an equivalent alternative.
- Respect `prefers-reduced-motion`.
