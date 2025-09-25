---
title: "Obsolescence Cost | supplycm Algorithm Library"
description: "Plain-English explanation of obsolescence_cost from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, obsolescence_cost, supply chain, plain english, inventory"
---

# Obsolescence Cost

> **Call it:** `from supplycm.inventory import obsolescence_cost` · **Level:** Intermediate · **You need:** basic arithmetic only

Values the yearly decay of inventory that will never sell at full price: inventory value x obsolescence rate x time held. Technology, fashion, and food all pay this tax - the question is whether you compute it or just discover it at write-off time.

**Think of it like this:** A new phone losing value monthly on a spreadsheet you refuse to open - the loss happens either way; the sheet just makes it honest.

## When to reach for it

- Including obsolescence in carrying cost and buying decisions
- Building the business case for smaller, faster replenishment cycles

## Try it with supplycm

```python
from supplycm.inventory import obsolescence_cost

result = obsolescence_cost(inventory_value=80000, obsolescence_rate=0.15, time_held=2)
print(result)
```

You should see something like:

```text
24000.0
```

24,000 of expected value decay over two years - real money that never appears on any invoice until it is too late.

## Check yourself

1. Which product families carry the highest obsolescence rates?
2. Obsolescence vs shrinkage - difference?
3. How does faster replenishment fight obsolescence?

<details>
<summary>Show answers</summary>

1. Electronics, fashion, perishables - anything where 'this year's version' has an expiry date.

2. Obsolescence is value decay of stock you still have; shrinkage is stock physically vanishing (theft, damage).

3. Smaller, fresher holdings mean less stock exposed to 'out of fashion' moments - speed is armor.

</details>

## Try this now

Estimate annual obsolescence cost for a fashion category at 20% rate and 120k average stock - then price the benefit of halving time held.

---
[← Slow-Moving Item Detection](slow_moving_detection.md) · [Back to Inventory library](README.md) · [FIFO Valuation →](fifo_valuation.md)
