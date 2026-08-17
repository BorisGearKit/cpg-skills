---
name: business-profile
description: The memory layer for the ShelfKit CPG skill pack — saves what any skill learns about the user's business (suppliers, formulas, lead times, MOQs, calendar, channels) into plain files the user owns, and feeds those facts back to every skill so the user never explains their business twice. Use at the end of any ShelfKit skill run that learned durable business facts, when the user says "remember this" / "save this" / "why are you asking again", or when setting up or updating the profile.
---

# Business Profile

The single most common pain of CPG operators using Claude: they are on version 8 of the same chat,
re-teaching it their vendors and lead times every time. This skill ends that. It turns what skills
learn while working into a small set of readable files the OPERATOR owns, and it is the reason the
second run takes 30 seconds instead of 20 minutes.

Two hard principles:

1. **The files belong to the operator.** Plain markdown, readable line by line, in THEIR storage.
   Never suggest uploading them anywhere. Never store anything the operator wouldn't show an
   employee on day one.
2. **Ask before saving, show what you'll save.** Memory written silently is surveillance. Memory
   offered explicitly is a feature.

## The file layout

```
business-profile/
  business.md      # who: brand, products at a glance, stage, the one-line context
  suppliers.md     # per supplier: contact, what they supply, lead time, MOQ/case size, terms
  products.md      # per product: formula/BOM, batch math, packaging
  calendar.md      # run cadence, seasonal spikes, retailer reset dates, standing deadlines
  channels.md      # retailers/distributors, per-channel quirks (forms, deductions, portals)
  preferences.md   # how they like POs worded, units, sign-off name, tone
```

Every fact carries its date: `lead time: 21 days (as of 2026-08-17)`. Facts age; dated facts can be
challenged, undated facts get silently trusted and go stale.

**Never store:** passwords, API keys, bank/payment details, employee personal data, or anything the
user marks confidential in passing. If a formula is sensitive, store the batch MATH shape and let
the quantities live in the user's own linked file if they prefer — offer that choice.

## Where the files live — detect the environment

- **Claude Code / filesystem access:** write real files to `business-profile/` in the working
  folder (or the user's chosen path). Suggest git if they use it: "this folder is worth
  version-controlling."
- **Claude Cowork:** write the files into the workspace folder.
- **Claude.ai chat (no filesystem):** produce each file as a downloadable artifact, then show the
  one-time setup: "Add these to your Project's knowledge (Project → knowledge → add), and every
  chat in the project reads them automatically. Re-download and replace when we update them."

## The save moment — the script

At the end of any skill run that learned durable facts, count what was learned and offer it back,
concretely. The shape (adapt the numbers, keep the structure):

> I learned 11 things about your business today:
> · 4 suppliers with contacts · 3 lead times · 2 formulas · your MOQ floors · your 4-week cadence
>
> Save these to your Business Profile so every skill knows them and your next run takes 30 seconds?
> I'll show you exactly what I'm writing.

If yes: write the files, then show a compact diff-style summary of what was added where. If no:
drop it without argument, and don't re-offer in the same session.

## Reading the profile — for every ShelfKit skill

Any skill, at start:

1. Look for `business-profile/` (files, workspace, or project knowledge).
2. Load only the files relevant to the job (production-planner: suppliers, products, calendar).
3. **Open by showing what you already know**, with dates: "Working from your profile: Meridian
   Mills, 21-day lead time as of Aug 12 — still right?" One-line confirmation beats re-asking, but
   never silently trust a fact older than ~60 days for anything money-adjacent.
4. New or corrected facts learned during the run go through the save moment at the end — additive,
   dated, corrections overwrite with a `(was: …)` note.

## Updates and conflicts

- Additive by default. A correction replaces the fact and keeps the old value inline:
  `lead time: 14 days (as of 2026-08-17, was 21)`.
- If two sources disagree (user says 14, file says 21), ask — never pick silently.
- The user can say "forget X" — delete it fully, confirm what was removed.

## What this skill never does

- Never sends profile data anywhere, never suggests a cloud sync it can't verify, never phones home.
- Never blocks a job on profile setup. The profile is a byproduct of work, not a prerequisite.
- Never oversells: if the user asks what the profile is for, the answer is one line — "so you never
  explain your business twice" — not an architecture lecture.
