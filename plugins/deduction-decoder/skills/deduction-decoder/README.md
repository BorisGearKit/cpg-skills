# Deduction Decoder

A Claude Code skill for CPG founders who open a remittance and find the check smaller than the
invoice, with no clear reason why. It classifies every deduction line (agreed trade/promo,
freight, compliance chargebacks, spoils/damage, or unexplained), rebuilds the gross-to-net
waterfall from your numbers, and drafts dispute packets for the lines worth disputing —
respecting the filing windows so nothing goes stale.

## Example

**Input** (pasted into the chat):

> "Northgate Provisions took $4,180 off our last remittance and I have no idea why. Gross
> invoiced was $31,400."

**What you get back:**

- Each deduction line named and classified — e.g. `$1,200 off-invoice promo (matches Feb trade
  calendar)`, `$640 late-ASN compliance chargeback`, `$2,340 unexplained short-pay, no backup
  attached`.
- A gross-to-net waterfall table: gross invoiced → trade/promo → freight → compliance →
  spoils/damage → unexplained → net sales, so margin gets computed on the number investors
  actually use.
- A dispute packet for the $2,340 unexplained line and the $640 chargeback (if it's your 3PL's
  contractual fault): reference number, what's claimed vs. what happened, backup to attach, and
  the ask — plus the filing window so it goes in on time.
- The top two root causes in your data, each with a one-line fix (e.g. "promo deductions with
  no calendar match → keep one trade calendar as source of truth").

## Install

```
/plugin marketplace add BorisGearKit/cpg-skills
/plugin install deduction-decoder@cpg-skills
```

## License

Free to use for your business, including commercially (PolyForm Shield 1.0.0). Not open source —
the license reserves building a competing product.
