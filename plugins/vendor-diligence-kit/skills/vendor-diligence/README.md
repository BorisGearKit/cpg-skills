# Vendor Diligence Kit

A Claude Code skill for vetting an operational vendor — co-manufacturer, 3PL, freight broker, or
packaging printer — before you sign. Paste in a quote, proposal, or the vendor's website, and it
extracts the facts stated (and flags what a serious vendor would have stated and didn't), scores
red flags specific to the vendor type, and gives you the questions and reference-check script that
actually differentiate one vendor from another.

## Example

**Input** (pasted quote):

> "Driftwood Copack Solutions — MOQ 15,000 units, $0.62/unit at that tier, drops to $0.48 at
> 50,000. SQF certification in progress. Lead time 6 weeks. We own the tooling."

**What you get back:**

- Extracted facts quoted back with their source line, plus what's missing: no scrap/overrun
  policy stated, no named QA contact, no reference customers offered.
- Red flags scored and cited: "certification in progress" (not current), pricing that only works
  at a volume tier you're not ordering yet, tooling owned by them with no buyout terms, lead time
  not specified as from-PO vs. from-materials-in-house vs. from-artwork-approval.
- 8–10 tailored differentiating questions, e.g. "What's your minimum viable first run, not your
  rate-card MOQ?" and "Which two customers left you in the past year, and why?"
- A verbatim reference-check call script for two vendor-supplied references plus one you find
  yourself.
- A comparison sheet if you're evaluating more than one vendor: cost per unit at stated MOQ, true
  lead time, certifications verified vs. claimed, formula/tooling ownership, red-flag count — plus
  the single biggest open risk per vendor.

## Install

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install vendor-diligence-kit@cpg-skills
```

## License

Free to use for your business, including commercially (PolyForm Shield 1.0.0). Not open source —
the license reserves building a competing product.
