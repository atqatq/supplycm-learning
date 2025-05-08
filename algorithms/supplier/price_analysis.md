---
title: "Price Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of price_analysis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, price_analysis, supply chain, plain english, supplier & procurement"
---

# Price Analysis

> **Call it:** `from supplycm.supplier import price_analysis` · **Level:** Intermediate · **You need:** basic arithmetic only

Feed in a list of quotes or historical prices and get the key statistics in one call: average, spread, cheapest, priciest. Wide spreads across similar suppliers signal negotiation room or inconsistent specs; stable prices suggest a mature, competitive market.

**Think of it like this:** Scanning flight prices for the same route: the spread tells you whether 'today's deal' is actually a deal.

## When to reach for it

- Pre-negotiation homework before talking to suppliers
- Checking whether a price increase is market-wide or supplier-specific

## Try it with supplycm

```python
from supplycm.supplier import price_analysis

result = price_analysis([98.0, 105.0, 99.5, 120.0, 97.0])
print(result)
```

You should see something like:

```text
[97.0, 103.9, 99.5, 9.5158]
```

Average near 104 with one outlier at 120 - either that quote has extras baked in, or it is the one to negotiate down.

## Check yourself

1. What does a very wide price spread tell you?
2. All quotes move up 8% together. Supplier problem or market problem?
3. Why always ask for the outlier's breakdown?

<details>
<summary>Show answers</summary>

1. Quotes may not be like-for-like (specs, terms, volumes) or the market is inefficient - investigate before deciding.

2. Likely market - raw materials or exchange rates. Your negotiation lever changes accordingly.

3. It either hides a real cost difference you can learn from, or padding you can negotiate away.

</details>

## Try this now

Analyze 6 quotes for one part; write the two questions you would ask the highest bidder.

---
[← Purchase Order Compliance](purchase_order_compliance.md) · [Back to Supplier & Procurement library](README.md) · [Purchase Price Variance →](purchase_price_variance.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
