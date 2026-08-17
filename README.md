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

These are knowledge skills — they run entirely in your Claude, on your plan. The engines behind
ShelfKit (planning solver, watchers that work while you sleep) are the paid layer:
[shelfkit.ai](https://shelfkit.ai).

More skills coming: cert-readiness roadmap, thread untangler. PRs and requests welcome.

## License

[PolyForm Shield 1.0.0](LICENSE.md) — free to use for your business, including commercially:
install the skills, run them on your operations, adapt them to your workflows. The one thing
the license reserves: using them to build or provide a product that competes with ShelfKit /
GearKit. Operators run free; competitors build their own.
