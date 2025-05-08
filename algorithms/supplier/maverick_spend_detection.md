---
title: "Maverick Spend Detection | supplycm Algorithm Library"
description: "Plain-English explanation of maverick_spend_detection from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, maverick_spend_detection, supply chain, plain english, supplier & procurement"
---

# Maverick Spend Detection

> **Call it:** `from supplycm.supplier import maverick_spend_detection` · **Level:** Intermediate · **You need:** basic arithmetic only

Maverick spend is buying outside agreed contracts and preferred suppliers - quick, well-meaning, and expensive. This flags transactions made with non-preferred suppliers and totals the money involved. You get a list and a number to manage down.

**Think of it like this:** Employees buying groceries at the corner shop while the company has a supermarket deal - convenient for them, costly for everyone.

## When to reach for it

- Procurement compliance programs
- Quantifying savings from enforcing catalog buying

## Try it with supplycm

```python
from supplycm.supplier import maverick_spend_detection

result = maverick_spend_detection(transactions=[('X', 'PreferredA', 500.0), ('Y', 'RoadsideB', 900.0), ('Z', 'PreferredA', 300.0), ('W', 'RoadsideB', 1200.0)], preferred_suppliers={'PreferredA'})
print(result)
```

You should see something like:

```text
[['Y', 900.0], ['W', 1200.0]]
```

Two off-contract transactions totaling 2,100 are flagged - now the conversation is about a number, not a suspicion.

## Check yourself

1. Why does maverick spend happen even with good contracts?
2. Is all non-contract buying bad?
3. What is the healthiest fix?

<details>
<summary>Show answers</summary>

1. Urgency, ignorance of contracts, or friction in the official process - fix the process, not just the people.

2. Occasionally it finds better deals - investigate outliers instead of blanket-punishing.

3. Make the compliant path the easiest path: catalogs, one-click approvals, and clear guidance.

</details>

## Try this now

Scan 12 transactions for off-contract buys; estimate annualized savings if 80% shifted to preferred terms at 12% better prices.

---
[← Spend Analysis](spend_analysis.md) · [Back to Supplier & Procurement library](README.md) · [Supplier Consolidation →](supplier_consolidation.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
