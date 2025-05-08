---
title: "Purchase Order Compliance | supplycm Algorithm Library"
description: "Plain-English explanation of purchase_order_compliance from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, purchase_order_compliance, supply chain, plain english, supplier & procurement"
---

# Purchase Order Compliance

> **Call it:** `from supplycm.supplier import purchase_order_compliance` · **Level:** Intermediate · **You need:** basic arithmetic only

Measures how well suppliers follow what was actually ordered: right quantities, right items, right timing. Feed order lines and receipts; get back a compliance percentage. Low compliance means your planners spend their days fixing paperwork instead of improving supply.

**Think of it like this:** Restaurant orders: you ordered no onions twice, got onions anyway - the kitchen 'did its own thing' and you ate the cost.

## When to reach for it

- Tracking disciplined execution by suppliers (and by your own buyers)
- Root-causing expediting and invoice-matching pain

## Try it with supplycm

```python
from supplycm.supplier import purchase_order_compliance

result = purchase_order_compliance(orders=[(100, 100), (100, 90), (200, 200), (150, 120)], contracts=[(100, 100), (100, 100), (200, 200), (150, 150)])
print(result)
```

You should see something like:

```text
0.5
```

Half the lines deviated from the order - a compliance score near 50% means chaos upstream is now your planning problem.

## Check yourself

1. What does a compliance score actually measure?
2. Why do substitutions and short-ships hurt planning?
3. Compliance is 99% but service is terrible. How?

<details>
<summary>Show answers</summary>

1. The share of orders executed as written - quantities, items, and dates matching the PO.

2. Each one silently invalidates an assumption in MRP and schedules - plans rot line by line.

3. You may be ordering the wrong things perfectly - compliance measures execution, not strategy.

</details>

## Try this now

Grade 8 order lines against their contracts; identify the two worst deviations and their downstream effects.

---
[← Lead Time: Quoted vs Actual](lead_time_quoted_vs_actual.md) · [Back to Supplier & Procurement library](README.md) · [Price Analysis →](price_analysis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
