# Production Planner

A Claude Code skill that turns a production schedule into drafted purchase orders. Give it your
run schedule, your formulas (BOMs), current ingredient inventory, and supplier lead times, and it
cross-references all four to flag shortfalls, compute order-by dates, and draft one PO email per
supplier — ready for you to review and send, nothing goes out on its own.

## Example

**Input** (pasted or attached):

> Schedule: 4 weeks of runs for Meridian Snacks — 2,000 units of Sea Salt Chips on 9/1, 3,000
> units of Sea Salt Chips on 9/15, 1,500 units of Spicy Chips on 9/22.
> Formula: Sea Salt Chips = 40g potato flake, 1.2g sea salt, 8g sunflower oil per unit.
> On hand: 60kg potato flake, 400g sea salt, 20kg sunflower oil.
> Suppliers: Cascade Milling (potato flake, 14-day lead time), Basin Salt Co. (sea salt, 7-day
> lead time), Ridgeline Oils (sunflower oil, 21-day lead time).

**What you get back:**

- A requirements table: ingredient, needed, on hand, shortfall, needed-by date, order-by date
  (needed-by minus lead time minus a stated safety margin).
- Verdict lines — e.g. "Order now: sunflower oil, order-by was 8/25 — already past, production on
  9/1 is at risk by 3 days" — sorted by urgency, with a fallback offered for anything at risk.
- A drafted PO email to each supplier: itemized lines, quantities in the supplier's unit, needed-by
  dates, and a plain closing asking for confirmed pricing and ship date.
- The requirements table, the supplier/lead-time table, and each PO draft, offered back as files
  you keep in your own system.

## Install

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install production-planner@cpg-skills
```

## License

Free to use for your business, including commercially (PolyForm Shield 1.0.0). Not open source —
the license reserves building a competing product.
