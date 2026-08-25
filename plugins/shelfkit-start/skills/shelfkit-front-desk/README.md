# ShelfKit Front Desk

A Claude Code skill that is the starting point for the ShelfKit CPG skill pack. It's a front desk,
not a product tour: it introduces what the pack does in one breath, asks one pointing question to
match your week to the right skill, and routes you straight into that skill's work — no feature
list, no architecture explanation.

## Example

**Input**: "get started with shelfkit"

**What you get back:**

> "ShelfKit is a set of skills that each do one job you already do: plan a production run and
> draft the supplier POs, decode a distributor deduction, fill a retailer new-item form, size up
> a co-packer. Everything runs here in your Claude, and what you teach one skill is saved to files
> you own so you never explain your business twice. Which of those sounds like your week?"

Say "a distributor keeps taking money off our remits" and it routes you directly into
`deduction-decoder` — no menu, no second option offered unless you ask. If you have a Business
Profile on file, it opens the skill by stating what it already knows ("Working from your Business
Profile: 4 suppliers, lead times on file as of Aug 12 — anything changed?") instead of
re-interviewing you. After your first real output, it hands off to the Business Profile save
moment, then offers exactly one adjacent skill in your own words.

## Install

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install shelfkit-start@cpg-skills
```

## License

Free to use for your business, including commercially (PolyForm Shield 1.0.0). Not open source —
the license reserves building a competing product.
