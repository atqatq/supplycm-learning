---
title: "Stockout Cost | supplycm Algorithm Library"
description: "Plain-English explanation of stockout_cost from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, stockout_cost, supply chain, plain english, inventory"
---

# Stockout Cost

> **Call it:** `from supplycm.inventory import stockout_cost` · **Level:** Beginner · **You need:** basic arithmetic only

Puts a price on empty shelves: expected shortage units times the penalty per unit - lost margin, expediting, or goodwill. Until this number exists, safety stock debates are vibes; after it exists, they are arithmetic.

**Think of it like this:** An empty restaurant table at 8pm Saturday: the cost isn't the empty chair, it's the dinner that never got ordered.

## When to reach for it

- Justifying safety stock investments with numbers
- Balancing holding cost against service in policy design

## Try it with supplycm

```python
from supplycm.inventory import stockout_cost

result = stockout_cost(expected_shortage=25, shortage_penalty=12)
print(result)
```

You should see something like:

```text
300
```

300 at risk per period - now compare it with the holding cost of the safety stock that would prevent it.

## Check yourself

1. What belongs in the penalty per unit?
2. Stockout cost 300 vs safety stock holding 150 - decision?
3. Why do firms systematically understate stockout cost?

<details>
<summary>Show answers</summary>

1. Lost margin is the floor; add expediting, substitution at lower price, and long-run loyalty damage.

2. The buffer pays for itself - unless the shortage estimate is inflated; check both numbers honestly.

3. It never appears as a line item - it hides inside 'sales below plan'; naming it changes decisions.

</details>

## Try this now

Price a one-day stockout of your favorite product: units missed x margin + one rush order - and compare with a year of safety stock.

---
[← Expected On-Hand Inventory](expected_on_hand.md) · [Back to Inventory library](README.md) · [ABC Analysis →](abc_analysis.md)
