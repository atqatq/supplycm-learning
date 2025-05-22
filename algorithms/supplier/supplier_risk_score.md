---
title: "Supplier Risk Score | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_risk_score from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_risk_score, supply chain, plain english, supplier & procurement"
---

# Supplier Risk Score

> **Call it:** `from supplycm.supplier import supplier_risk_score` · **Level:** Intermediate · **You need:** basic arithmetic only

Blends risk factors - financial health, country risk, single-source dependency, quality history - with weights into one 0-100 score. High scorers get mitigation: second sources, buffer stock, or tighter contracts, decided by the number, not by mood.

**Think of it like this:** A weather forecast for supplier failure: not a guarantee, but you take an umbrella when it says 80%.

## When to reach for it

- Quarterly risk reviews of the critical supplier base
- Deciding which suppliers need contingency plans this year

## Try it with supplycm

```python
from supplycm.supplier import supplier_risk_score

result = supplier_risk_score(risk_factors={'financial': 60, 'country': 40, 'concentration': 80, 'quality_history': 30}, weights={'financial': 0.3, 'country': 0.2, 'concentration': 0.3, 'quality_history': 0.2})
print(result)
```

You should see something like:

```text
56.0
```

Roughly 55 - middling overall but concentration at 80 is the red flag; a second source attacks the heaviest weighted risk.

## Check yourself

1. Which risk factor is usually weighted heaviest and why?
2. Risk score rises 20 points in one quarter. Response?
3. Why score ALL critical suppliers, not just the scary ones?

<details>
<summary>Show answers</summary>

1. Often financial or concentration - a bankrupt or irreplaceable supplier can stop your line entirely.

2. Investigate the driver immediately - score jumps usually mean something real changed.

3. Because risk migrates quietly - the boring supplier of last year may be the crisis of this one.

</details>

## Try this now

Score your most critical (real or imagined) supplier on 4 factors; name the one mitigation that lowers the weighted score most.

---
[← Composite Supplier Rating](supplier_rating.md) · [Back to Supplier & Procurement library](README.md) · [Preferred Supplier Index →](preferred_supplier_index.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
