# Business Profile

A Claude Code skill that is the memory layer for the ShelfKit CPG skill pack. It saves what any
other skill learns about your business — suppliers, formulas, lead times, MOQs, calendar,
channel quirks — into plain markdown files you own, and feeds those facts back to every skill so
you never re-teach Claude your vendors and lead times on every run. It asks before saving and
shows you exactly what it's writing; nothing is stored silently.

## Example

**Input**: after a Production Planner run for Driftwood Foods that surfaced new supplier and
lead-time facts, the skill offers:

> "I learned 11 things about your business today: 4 suppliers with contacts, 3 lead times, 2
> formulas, your MOQ floors, your 4-week cadence. Save these to your Business Profile so every
> skill knows them and your next run takes 30 seconds? I'll show you exactly what I'm writing."

**What you get back:**

- A `business-profile/` folder with dated files: `business.md`, `suppliers.md`, `products.md`,
  `calendar.md`, `channels.md`, `preferences.md` — every fact carries an as-of date, e.g. "lead
  time: 21 days (as of 2026-08-17)".
- On the next skill run, an opening line instead of a re-interview: "Working from your profile:
  Meridian Mills, 21-day lead time as of Aug 12 — still right?"
- A self-contained `profile.html` view of the whole profile, regenerated on every save, for
  scanning without opening a folder of markdown files.
- Corrections tracked inline, e.g. "lead time: 14 days (as of 2026-08-17, was 21)" — never
  overwritten silently.

## Install

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install shelfkit-start@cpg-skills
```

## License

Free to use for your business, including commercially (PolyForm Shield 1.0.0). Not open source —
the license reserves building a competing product.
