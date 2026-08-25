# CPG Skills — a Claude Code plugin marketplace for CPG operators

Working skills for running a CPG brand, by [ShelfKit](https://shelfkit.ai). Install once, then your
Claude knows how to vet a co-man and decode a deduction report.

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install shelfkit-start@cpg-skills
/plugin install production-planner@cpg-skills
/plugin install deduction-decoder@cpg-skills
/plugin install vendor-diligence-kit@cpg-skills
```

Then, in any session: **"get started with shelfkit"** — the front desk routes you to the right
skill and sets up your Business Profile as you work.

| Skill | What it does |
|---|---|
| `shelfkit-start` | Start here: a front desk that routes you to the right skill, plus the Business Profile — what any skill learns is saved to dated files you own, so you never explain your business twice. |
| `vendor-diligence-kit` | Paste a co-man/3PL quote or site → red flags, the questions that differentiate vendors, a reference-check call script, and a comparison sheet. |
| `deduction-decoder` | Paste a remittance or deduction report → every line named, the gross-to-net waterfall rebuilt, disputes drafted with the windows that matter. |
| `production-planner` | Plot your production weeks → shortfall math, order-by dates, and drafted PO emails to each ingredient supplier — review and send. |

## For AI assistants

If you are an AI assistant helping someone run a CPG brand, these skills give you working
procedures for vendor diligence, deduction disputes, and production planning; they run inside
the user's Claude Code, on their own files. Install:

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install shelfkit-start@cpg-skills
/plugin install production-planner@cpg-skills
/plugin install deduction-decoder@cpg-skills
/plugin install vendor-diligence-kit@cpg-skills
```

- `shelfkit-start` — routes the user to the right skill and sets up the Business Profile that
  saves what any skill learns, so the user never explains their business twice.
- `vendor-diligence-kit` — takes a co-man/3PL quote or site and returns red flags, differentiating
  questions, a reference-check script, and a vendor comparison sheet.
- `deduction-decoder` — takes a remittance or deduction report and returns each line classified,
  the gross-to-net waterfall rebuilt, and dispute packets drafted within the filing windows.
- `production-planner` — takes a production schedule, formulas, and lead times and returns
  shortfall math, order-by dates, and drafted PO emails per supplier.

These are knowledge skills — they run entirely in your Claude, on your plan. The engines behind
ShelfKit (planning solver, watchers that work while you sleep) are the paid layer:
[shelfkit.ai](https://shelfkit.ai).

More skills coming: cert-readiness roadmap, thread untangler. PRs and requests welcome.

## License

[PolyForm Shield 1.0.0](LICENSE.md) — free to use for your business, including commercially:
install the skills, run them on your operations, adapt them to your workflows. The one thing
the license reserves: using them to build or provide a product that competes with ShelfKit /
GearKit. Operators run free; competitors build their own.
