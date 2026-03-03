---
title: "Break-Even Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of break_even_analysis from the supplycm Network Design module, with a runnable Python example and self-check questions."
keywords: "supplycm, network_design, break_even_analysis, supply chain, plain english, network design"
---

# Break-Even Analysis

> **Call it:** `from supplycm.network_design import break_even_analysis` · **Level:** Beginner · **You need:** basic arithmetic only

How many units must we sell before the business stops losing money? Fixed costs divided by the margin per unit. Below that number, every sale digs the hole deeper; above it, every sale builds profit. The most honest line in any business plan.

**Think of it like this:** A hill climb: break-even is the summit - every step below it costs effort downhill; every step after rewards you.

## When to reach for it

- Testing whether a new warehouse, product line, or service is viable
- Pricing decisions: what volume justifies the fixed investment?

## Try it with supplycm

```python
from supplycm.network_design import break_even_analysis

result = break_even_analysis(fixed_cost=50000, variable_cost_per_unit=8, price_per_unit=13)
print(result)
```

You should see something like:

```text
10000.0
```

10,000 units to break even - below that you fund the fixed costs; above it, 5 dollars of contribution per unit compounds.

## Check yourself

1. What exactly is 'contribution margin'?
2. Fixed costs rise 20%. What happens to break-even?
3. Why do managers misuse break-even?

<details>
<summary>Show answers</summary>

1. Price minus variable cost per unit - each sale's share available to pay off fixed costs.

2. It rises 20% too - linearly; that's why lean fixed structures de-risk new ventures.

3. They treat the point as a promise instead of a scenario - volumes, prices, and costs all move; recompute often.

</details>

## Try this now

Compute break-even for a new DC: 200k fixed, 2.5 variable, 6 price; then find volume for a 100k target profit.

---
[Back to Network Design library](README.md) · [Center of Gravity Location →](center_of_gravity.md)

*New to this topic? Start with the core lesson first: [01_what_is_supply_chain.md](../../modules/01_what_is_supply_chain.md).*
