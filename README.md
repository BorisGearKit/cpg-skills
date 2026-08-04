# CPG Skills — a Claude Code plugin marketplace for CPG operators

Working skills for running a CPG brand, by [ShelfKit](https://shelfkit.ai). Install once, then your
Claude knows how to vet a co-man and decode a deduction report.

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install vendor-diligence-kit@cpg-skills
/plugin install deduction-decoder@cpg-skills
```

| Skill | What it does |
|---|---|
| `vendor-diligence-kit` | Paste a co-man/3PL quote or site → red flags, the questions that differentiate vendors, a reference-check call script, and a comparison sheet. |
| `deduction-decoder` | Paste a remittance or deduction report → every line named, the gross-to-net waterfall rebuilt, disputes drafted with the windows that matter. |

These are knowledge skills — they run entirely in your Claude, on your plan. The engines behind
ShelfKit (planning solver, watchers that work while you sleep) are the paid layer:
[shelfkit.ai](https://shelfkit.ai).

More skills coming: cert-readiness roadmap, reorder math, thread untangler. PRs and requests welcome.
