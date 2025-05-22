---
title: "Should-Cost Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of should_cost_analysis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, should_cost_analysis, supply chain, plain english, supplier & procurement"
---

# Should-Cost Analysis

> **Call it:** `from supplycm.supplier import should_cost_analysis` · **Level:** Intermediate · **You need:** basic arithmetic only

Before negotiating, build the price from scratch: materials, labor hours x rate, overhead, and a fair profit margin. The result is what the product SHOULD cost - your evidence-based anchor. Walking into a negotiation with a should-cost model changes the conversation from opinions to numbers.

**Think of it like this:** Appraising a cake by its ingredients and oven time, so a bakery cannot claim saffron is in every slice.

## When to reach for it

- Negotiating big-ticket custom parts with transparent BOMs
- Testing whether a quote is padded before signing

## Try it with supplycm

```python
from supplycm.supplier import should_cost_analysis

result = should_cost_analysis(material_costs={'steel': 42.0, 'paint': 8.0}, labor_hours=2.5, labor_rate=30.0, overhead_rate=20.0, profit_margin=0.1)
print(result)
```

You should see something like:

```text
1787.5
```

A should-cost near 150 - if the quote says 210, you now know exactly where to probe: which cost line differs from your model?

## Check yourself

1. What inputs build a should-cost model?
2. The supplier says 'our overhead is higher'. Response?
3. When is should-cost a waste of time?

<details>
<summary>Show answers</summary>

1. Material quantities and prices, labor hours and rates, overhead allocation, and a fair margin.

2. Ask to see the drivers - volume, utilization, process. Should-cost is a conversation starter, not an ultimatum.

3. On small spends or true commodities with transparent markets - the model costs more than the savings.

</details>

## Try this now

Should-cost a simple bracket: $18 material, 0.5 labor hours at $28, 15% overhead on labor, 8% margin. Compare to a $40 quote.

---
[← Total Cost of Ownership (TCO)](total_cost_of_ownership.md) · [Back to Supplier & Procurement library](README.md) · [AHP Supplier Selection →](ahp_supplier_selection.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
