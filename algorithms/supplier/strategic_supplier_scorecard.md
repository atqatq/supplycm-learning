---
title: "Strategic Supplier Scorecard | supplycm Algorithm Library"
description: "Plain-English explanation of strategic_supplier_scorecard from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, strategic_supplier_scorecard, supply chain, plain english, supplier & procurement"
---

# Strategic Supplier Scorecard

> **Call it:** `from supplycm.supplier import strategic_supplier_scorecard` · **Level:** Intermediate · **You need:** basic arithmetic only

The strategic version of a scorecard adds forward-looking KPIs - innovation, improvement, risk management - next to delivery and cost. Each KPI is weighted, and out come per-KPI contributions plus one overall score for the partnership review.

**Think of it like this:** Rating a star employee not just on output, but on mentoring, ideas, and reliability - because you are building a future together, not just buying today.

## When to reach for it

- Quarterly business reviews with strategic (Kraljic top-right) suppliers
- Joint improvement programs where innovation should be rewarded

## Try it with supplycm

```python
from supplycm.supplier import strategic_supplier_scorecard

result = strategic_supplier_scorecard(kpis={'quality': 95, 'delivery': 90, 'cost': 85, 'innovation': 80}, weights={'quality': 0.3, 'delivery': 0.3, 'cost': 0.2, 'innovation': 0.2})
print(result)
```

You should see something like:

```text
{'weighted_quality': 28.5, 'weighted_delivery': 27.0, 'weighted_cost': 17.0, 'weighted_innovation': 16.0, 'overall_score': 88.5}
```

Each weighted contribution plus an overall near 89 - innovation lags the pack, which becomes the agenda item for the next roadmap meeting.

## Check yourself

1. What KPIs belong on a STRATEGIC scorecard that a routine one skips?
2. Supplier scores 95 on quality, 60 on innovation. Consequence?
3. Why show weighted contributions per KPI?

<details>
<summary>Show answers</summary>

1. Innovation, continuous improvement, risk transparency, and joint-planning participation.

2. A development conversation with concrete expectations - strategic suppliers must bring ideas, not just parts.

3. So both sides see exactly which line moved the total - reviews become about specific gaps, not vibes.

</details>

## Try this now

Scorecard your most strategic supplier on 4 KPIs; write the single development goal for next quarter.

---
[← Data Envelopment Analysis (DEA)](data_envelopment_analysis.md) · [Back to Supplier & Procurement library](README.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
