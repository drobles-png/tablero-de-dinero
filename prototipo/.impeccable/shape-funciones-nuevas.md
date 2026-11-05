# Plan v2: priority 1 features (scheduled payments, accounts, quick logging, pay days)

Planned with `/impeccable shape` on 2026-10-23. Waiting for the user's approval; no code yet. The build starts from the latest published version of the artifact (v7, black and white).

## Central idea
**"Te quedan $X · unos $Y por día hasta el cobro" = what I can really spend until the next pay day.**

- $X = balance of the spending accounts (cash and bank) − scheduled payments not yet paid that fall due before the next pay day (overdue ones included).
- Savings do not count.
- The four features exist to make that number true, and to make keeping it true cost almost nothing.

## Decisions already confirmed (round 1)
- Savings are kept apart from "te quedan". Moving money into savings lowers it.
- Scheduled payments are never logged automatically:
  - They wait in "Por pagar" with a **Pagar** button, and the amount can be adjusted.
  - Overdue payments show in red.
  - Paying logs the expense and moves the payment to its next date.
- Pay days: quincenal (two days, 15 and 30 by default) or mensual. **New in v2: "Fechas propias"**, a list of specific dates for irregular pay.

## Navigation (changes the v1 plan: no "Más" or "Ajustes" catch-all)
`Resumen · Movimientos · [+] · Cuentas · Plan`

- **Plan** gathers only what looks ahead: pay days and scheduled payments. Pro budgets and savings goals will live here later, under the same logic.
- **Categorías** moves inside **Movimientos**, as a `Lista | Categorías` switch. Categories classify movements, so they belong there.

## Screens
- **Band (Resumen):**
  - "Te quedan", with an eye button to hide the balance: amounts become "$•••" and the choice is remembered.
  - The per-day line.
  - "Apartado: $X para N pagos antes del cobro".
  - The Entró/Salió pills.
  - The rail with the real daily limit.
- **Resumen, "Por pagar antes del {día}":**
  - Each row shows name, date, amount and **Pagar**.
  - Overdue rows show "Vencido" in red.
  - When there are no payments, the empty state invites you to add the first one ("Arriendo, plan celular, suscripciones…"). It never shows a bare "Vacío".
- **Cuentas:**
  - Available total at the top.
  - Cash and bank accounts with their balances.
  - Savings in its own block called "Apartado".
  - **Transferir** button.
  - Tapping an account opens its movements.
  - Create, rename and delete accounts. Deleting an account that has movements asks where to move them.
  - The empty state explains why to separate accounts.
- **Plan:**
  - Pay days (quincenal, mensual or fechas propias).
  - Scheduled payments: create, edit and pause. Each one has name, amount, category, account, frequency (monthly, every quincena or once) and next date.
- **Logging sheet (2 taps):**
  - **Repetir:** at the top, chips with your last 3 distinct movements. **One tap saves directly**, with an undo toast. That is + → chip, 2 taps.
  - **Most-used category already selected:** the one you use most for that type in the last 60 days. That is + → type the amount → Guardar.
  - **Frequent amounts:** the 3 most-used amounts for the selected category appear as chips under the amount.
  - **Type:** `Gasto | Ingreso | Transferencia`. A transfer takes De and A accounts, has no category and counts neither as income nor as expense.
  - **Account:** remembers the last one used and is hidden if only one exists.
  - When editing: "Registrar otra vez hoy".
- **Lists:** transfers show with a ⇄ icon in ink, without green or red.

## Data
- The `tablero` document gets: `cuentas` [{id, nombre, tipo: efectivo|banco|ahorro, saldoInicial}], `pagos` [{id, nombre, monto, cat, cuenta, frecuencia: mensual|quincenal|unica, dia|fecha, proxima, pausado}] and `cobro` {modo: quincenal|mensual|fechas, dias | fechas}.
- Movements get `cuenta`. A transfer is `{tipo:"transferencia", monto, de, a, fecha, nota}`.
- Hide balance is a per-device preference stored in localStorage.
- Migration: create "Efectivo" and assign it to movements without an account. With no payments and no other accounts, "te quedan" stays the same as today.

## States
- 0 movements, 0 payments, 1 account.
- An overdue payment.
- Amount set aside greater than what is available, shown as "Estás en negativo por $X".
- A negative opening balance.
- A transfer to the same account (error).
- 200+ movements, $99,999.99 amounts and long names.

## Unchanged / out of scope
- **Unchanged:**
  - DESIGN.md's black and white: green only for money coming in, red only for alerts.
  - No colors on categories or accounts.
  - Archivo.
  - All existing motion and Deshacer.
- **Out of scope for this step:** payments and locks (the Pro tier), budgets, savings goals, export and sharing.

## Pending cleanup (step 3, after the build)
1. Remove the leftover category recolor code: COLORS, colorNombre, d.color, d.setcolor, S.colorDe, S.nuevoColor and the #8A9692 fallback.
2. Remove `--on-accent`.
3. Make "cuidado" (black, bold, ≥90%) look different from "te pasaste" (red, >100%).
4. Unify the pay day marker with its screen-reader text.
