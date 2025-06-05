---
title: "Level Strategy | supplycm Algorithm Library"
description: "Plain-English explanation of production_level_strategy from the supplycm S&OP module, with a runnable Python example and self-check questions."
keywords: "supplycm, sop, production_level_strategy, supply chain, plain english, s&op"
---

# Level Strategy

> **Call it:** `from supplycm.sop import production_level_strategy` · **Level:** Beginner · **You need:** basic arithmetic only

The level strategy produces the same amount every period and lets inventory absorb the demand waves. The workforce stays calm and machines run steadily; the price is inventory build-ups ahead of peaks and draw-downs after them. Chase vs level is the classic S&OP trade-off.

**Think of it like this:** A steady river dammed into a reservoir: constant flow upstream, variable demand downstream.

## When to reach for it

- Skilled workforces and equipment that hate being switched on/off
- Products that can be built ahead and stored safely

## Try it with supplycm

```python
from supplycm.sop import production_level_strategy

result = production_level_strategy(demand=[100, 150, 80, 120], initial_inventory=0, safety_stock=0)
print(result)
```

You should see something like:

```text
[112.5, 112.5, 112.5, 112.5]
```

A constant production rate appears, with inventory climbing before the peak and draining after - stability bought with storage.

> **Watch out:** In practice most companies run a hybrid: partly level (core team), partly chase (temps and overtime on top).

## Check yourself

1. What does level strategy stabilize, and what swings instead?
2. Demand is seasonal and shelf life is 5 days. Level or chase?
3. How do you find the level rate?

<details>
<summary>Show answers</summary>

1. Output and staffing stay constant; inventory levels swing with demand.

2. Chase - building ahead is impossible with short shelf life.

3. A common start: average demand over the horizon, then adjust for ending-inventory targets and capacity limits.

</details>

## Try this now

For demand [60, 180, 100, 60], compute the level rate, then track inventory by hand month by month.

---
[← Chase Strategy](production_chase_strategy.md) · [Back to S&OP library](README.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
