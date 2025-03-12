---
title: "Stockout Demand Loss | supplycm Algorithm Library"
description: "Plain-English explanation of stockout_demand_loss from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, stockout_demand_loss, supply chain, plain english, demand planning"
---

# Stockout Demand Loss

> **Call it:** `from supplycm.demand import stockout_demand_loss` · **Level:** Intermediate · **You need:** basic arithmetic only

When shelves go empty, some customers wait, some buy a substitute, and some leave forever. This estimates the demand you lose during a stockout, given how long it lasted and what share of customers accept substitutes. It turns 'we were out' into a number for the P&L.

**Think of it like this:** A restaurant with no tables: some guests wait at the bar, some order a different dish, some walk to the place next door.

## When to reach for it

- Quantifying the service-level cost of past stockouts
- Arguing for safety stock increases with real lost-sales numbers

## Try it with supplycm

```python
from supplycm.demand import stockout_demand_loss

result = stockout_demand_loss(stockout_qty=50, stockout_duration=4, substitution_rate=0.6)
print(result)
```

You should see something like:

```text
20.0
```

With 60% of customers accepting a substitute, the truly lost demand is the remaining 40% share of what went unserved - the rest was saved by alternatives.

## Check yourself

1. What is substitution rate?
2. Why do repeated stockouts cost more than the math shows?
3. Which products deserve the strictest stockout protection?

<details>
<summary>Show answers</summary>

1. The share of customers who accept an alternative (another brand, another store, another day) instead of walking away.

2. Loyalty erodes - customers who hit empty shelves twice quietly switch for good.

3. High-margin traffic drivers where customers will not substitute - the reason for milk at the back of the supermarket.

</details>

## Try this now

A toy store stocks out 3 days before the holidays, missing ~40 sales/day with 50% substitution. Estimate lost demand and lost profit at $5 margin.

---
[← Cannibalization Effect](cannibalization_effect.md) · [Back to Demand Planning library](README.md) · [Demand Sensing →](demand_sensing.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
