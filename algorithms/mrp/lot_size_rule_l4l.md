---
title: "Lot-for-Lot (L4L) | supplycm Algorithm Library"
description: "Plain-English explanation of lot_size_rule_l4l from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, lot_size_rule_l4l, supply chain, plain english, mrp & production planning"
---

# Lot-for-Lot (L4L)

> **Call it:** `from supplycm.mrp import lot_size_rule_l4l` · **Level:** Beginner · **You need:** basic arithmetic only

Lot-for-lot orders exactly the net requirement, period by period - no more, no less. Nothing sits in inventory waiting; the cost is a setup (or order) in every period with demand. It is the perfect rule for cheap-to-change processes and expensive-to-hold items.

**Think of it like this:** Cooking exactly tonight's dinner portion every evening - zero leftovers, but you cook all seven days.

## When to reach for it

- High holding cost or perishable items
- Make-to-order and cheap setups (setup cost near zero)

## Try it with supplycm

```python
from supplycm.mrp import lot_size_rule_l4l

result = lot_size_rule_l4l(net_requirements=[10, 0, 30, 20])
print(result)
```

You should see something like:

```text
[10, 0, 30, 20]
```

Orders of 10, 0, 30, 20 - demand periods get exactly their need; quiet periods order nothing.

## Check yourself

1. What does L4L minimize, and what does it ignore?
2. When is L4L clearly the right rule?
3. How does L4L differ from EOQ?

<details>
<summary>Show answers</summary>

1. It minimizes inventory but ignores setup cost - order every period with demand, however small.

2. When holding costs dwarf setup costs - perishables, custom items, cheap changeovers.

3. EOQ fixes one quantity for efficiency; L4L flexes with demand to eliminate holding.

</details>

## Try this now

Compute total cost of L4L vs a fixed lot of 30 for [10, 0, 30, 20] with setup 100 and holding 1/unit/period.

---
[← Capable-to-Promise (CTP)](capable_to_promise.md) · [Back to MRP & Production Planning library](README.md) · [Fixed Order Quantity (FOQ) →](lot_size_rule_foq.md)
