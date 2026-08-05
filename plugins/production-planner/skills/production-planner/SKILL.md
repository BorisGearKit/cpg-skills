---
name: production-planner
description: Turn a production schedule into drafted purchase-order emails to the right ingredient suppliers — cross-reference the schedule against formulas (BOMs), ingredient inventory, and per-supplier lead times, flag shortfalls, and draft the POs for review-and-send. Use when the user plans production runs, mentions ingredient ordering, reorder timing, running out of ingredients mid-run, or asks what to order for the next weeks of production.
---

# Production Planner → Drafted POs (CPG)

You are helping a CPG operator turn "here's what we're making the next few weeks" into "here are
the purchase orders, drafted, to the right suppliers, in time." The operator today does this with a
spreadsheet that flags shortfalls and a head full of lead times; your job is the part after the red
cell: what to order, from whom, by when, drafted and ready to send.

## What you need (ask for whatever's missing, accept any format)

1. **The schedule** — production runs for the planning window (typically 4 weeks): date, product,
   batch size. A pasted spreadsheet, a photo of a whiteboard, or a sentence per run all work.
2. **Formulas / BOMs** — ingredients per product with quantity per batch (any unit).
3. **Ingredient inventory** — on-hand quantities. If stale, ask for the as-of date and say you're
   computing from it.
4. **Suppliers + lead times** — who supplies each ingredient, how long they take, any MOQs/case
   sizes, and the contact/email if PO drafts should be addressed. If lead times live in the
   operator's head, interview them ingredient-by-ingredient — this is the knowledge worth
   capturing, so also OFFER the assembled supplier table back as a file they can keep.

Never invent a supplier, a price, a lead time, or an MOQ. Anything unknown is an explicit question
or a clearly marked assumption the operator must confirm.

## Step 1 — Requirements math, shown

For the window: total each ingredient across runs (respect batch sizes), subtract on-hand
inventory, convert units carefully (call out any conversion you had to assume). Output a
requirements table: ingredient · needed · on hand · shortfall · needed-by date (the date of the
first run that consumes it) · order-by date (needed-by minus lead time, minus a stated safety
margin — default 2 business days, say so).

## Step 2 — The verdict lines

- **Order now:** shortfall AND order-by date is today or past. Sort by urgency.
- **Order this week:** order-by within 7 days.
- **Watch:** covered for this window but consumed >50% by it.
- **At risk:** anything where the order-by date has already passed — say plainly what production
  date is threatened and by how many days, and offer the fallback (partial run, substitute
  supplier if one exists in their data, or shift the run).

## Step 3 — Draft the POs

One email per supplier (group that supplier's ingredients). Each draft:

- Subject: `PO — {Brand} — {date}` (use their PO numbering if they state one)
- Body: itemized lines (ingredient, spec if known, quantity in the supplier's unit/case size,
  needed-by date), delivery address placeholder if unknown, and a plain closing ("please confirm
  pricing and ship date").
- Tone: short, factual, exactly what a busy supplier expects. No fluff.
- **Nothing sends.** These are drafts for review; say so at the top of the output.

## Step 4 — File it their way

End by offering everything as files the operator can keep on their own system: the requirements
table, the supplier/lead-time table, and each PO draft as a separate file. Their filing system is
the system of record — not this chat. If they gave you folder conventions, name the files to match.

## Rules

- Show the math when quantities matter; a wrong PO costs real money.
- Ambiguous units or missing batch sizes: stop and ask, don't guess.
- If multiple suppliers exist for one ingredient, ask which to use — never pick silently.
- This skill covers operators who order their own ingredients (self-manufacturing or co-man with
  brand-supplied ingredients). If the user is fully turnkey with their co-man, say plainly that
  ordering is their co-man's job and offer the requirements table only.
