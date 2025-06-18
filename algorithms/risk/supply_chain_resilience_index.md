---
title: "Supply Chain Resilience Index | supplycm Algorithm Library"
description: "Plain-English explanation of supply_chain_resilience_index from the supplycm Risk module, with a runnable Python example and self-check questions."
keywords: "supplycm, risk, supply_chain_resilience_index, supply chain, plain english, risk"
---

# Supply Chain Resilience Index

> **Call it:** `from supplycm.risk import supply_chain_resilience_index` · **Level:** Intermediate · **You need:** basic arithmetic only

This scores how well your supply chain absorbs shocks: feed in measures like backup suppliers, inventory cover, flexibility, and visibility, each weighted by importance. Out comes one 0-100 index you can track over time or compare across sites. It turns a fuzzy worry into a managed number.

**Think of it like this:** A credit score, but for toughness: one number that lenders (here: disruptions) will test sooner or later.

## When to reach for it

- Board-level reporting: is our resilience improving year over year?
- Comparing plants, regions, or product lines on shock-readiness

## Try it with supplycm

```python
from supplycm.risk import supply_chain_resilience_index

result = supply_chain_resilience_index(metrics={'redundancy': 70, 'visibility': 55, 'flexibility': 60, 'financial_strength': 80}, weights={'redundancy': 0.3, 'visibility': 0.2, 'flexibility': 0.3, 'financial_strength': 0.2})
print(result)
```

You should see something like:

```text
66.0
```

About 65 out of 100 - decent, with visibility the weakest pillar; improving it lifts the whole index at the lowest cost.

## Check yourself

1. What makes a resilience score better than gut feeling?
2. One supplier provides 60% of your critical parts. Which metric suffers?
3. Scores: Plant A 74, Plant B 52. What next?

<details>
<summary>Show answers</summary>

1. It is comparable over time and across units, and the weights force leadership to agree on what resilience means.

2. Redundancy - single-source concentration drags the index down hard.

3. Inspect B's pillar scores - fix the weakest pillar first, then re-score to confirm the gain.

</details>

## Try this now

Score two sites you know with four pillars of your choice; identify the single cheapest improvement for the weaker one.

---
[Back to Risk library](README.md)

*New to this topic? Start with the core lesson first: [01_what_is_supply_chain.md](../../modules/01_what_is_supply_chain.md).*
