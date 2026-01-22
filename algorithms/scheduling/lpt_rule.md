---
title: "LPT (Longest Processing Time) | supplycm Algorithm Library"
description: "Plain-English explanation of lpt_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, lpt_rule, supply chain, plain english, scheduling"
---

# LPT (Longest Processing Time)

> **Call it:** `from supplycm.scheduling import lpt_rule` · **Level:** Beginner · **You need:** basic arithmetic only

Assigning jobs to several machines? Start the BIG jobs first. LPT's logic: heavy jobs are inflexible - place them early so small jobs can pour into whatever gaps remain. It is the standard, proven-good heuristic for spreading work across parallel machines.

**Think of it like this:** Packing a moving truck: furniture first, socks last - big rigid items need the floor space; small ones fill any void.

## When to reach for it

- Distributing jobs across identical machines or workers
- Cloud task assignment and shift planning

## Try it with supplycm

```python
from supplycm.scheduling import lpt_rule

result = lpt_rule(processing_times=[8, 3, 5, 2, 7], num_machines=2)
print(result)
```

You should see something like:

```text
[[0, 1, 3], [4, 2]]
```

Machines as lists - 8 and 7 lead on separate machines; small jobs top up the lighter side, evening the loads.

## Check yourself

1. Why do big jobs go first on parallel machines?
2. How good is LPT's guarantee?
3. What would beat LPT here?

<details>
<summary>Show answers</summary>

1. They can't be split - placing them early lets many small jobs fill the residual gaps on the other machines.

2. Within about 4/3 of optimal makespan on identical machines - excellent for a one-line rule.

3. Exact methods for small instances, or multifit-style binary search on the capacity - often for marginal gains.

</details>

## Try this now

Balance [10, 9, 8, 7, 6, 5] on 3 machines by LPT; compute each machine's load and spot the imbalance.

---
[← Line Balancing](line_balancing.md) · [Back to Scheduling library](README.md) · [List Scheduling →](list_scheduling.md)
