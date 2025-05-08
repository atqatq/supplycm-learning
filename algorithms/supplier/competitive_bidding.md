---
title: "Competitive Bidding | supplycm Algorithm Library"
description: "Plain-English explanation of competitive_bidding from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, competitive_bidding, supply chain, plain english, supplier & procurement"
---

# Competitive Bidding

> **Call it:** `from supplycm.supplier import competitive_bidding` · **Level:** Intermediate · **You need:** basic arithmetic only

Scores sealed bids by blending price and quality with chosen weights, then names the winner. It keeps a tender honest: the weights are published up front, and the arithmetic - not relationships - picks the supplier.

**Think of it like this:** A spelling bee judged on accuracy and speed with the scoring rubric read aloud before round one.

## When to reach for it

- One-off purchases where several credible suppliers compete
- Commodity categories where price should weigh heavily

## Try it with supplycm

```python
from supplycm.supplier import competitive_bidding

result = competitive_bidding(bids=[('Alpha', 100.0, 80.0), ('Beta', 110.0, 95.0), ('Gamma', 95.0, 60.0)], price_weight=0.7, quality_weight=0.3)
print(result)
```

You should see something like:

```text
['Alpha', 0.9176]
```

The winner depends on the weights - Gamma's low price cannot rescue a poor quality score at this 70/30 split.

## Check yourself

1. What happens if you shift to 50/50 weights?
2. When is competitive bidding the wrong tool?
3. How do you stop bidders gaming quality scores?

<details>
<summary>Show answers</summary>

1. Quality matters more - here Beta's case strengthens; publish weights BEFORE bids to keep the process fair.

2. Strategic partnerships and complex specs - there, negotiation and total-cost analysis beat one-round bidding.

3. Score quality on evidence (audits, samples, track record), not self-declared claims.

</details>

## Try this now

Re-run the example at weights 0.5/0.5 and 0.9/0.1; explain how the podium changes and what that implies for spec design.

---
[← Negotiation Zone (ZOPA)](negotiation_zone.md) · [Back to Supplier & Procurement library](README.md) · [Contract Compliance Score →](contract_compliance_score.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
