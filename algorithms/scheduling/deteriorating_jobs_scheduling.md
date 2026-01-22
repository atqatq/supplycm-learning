---
title: "Deteriorating Jobs Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of deteriorating_jobs_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, deteriorating_jobs_scheduling, supply chain, plain english, scheduling"
---

# Deteriorating Jobs Scheduling

> **Call it:** `from supplycm.scheduling import deteriorating_jobs_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Some jobs get HARDER the longer they wait: fresh food spoils, paperwork compounds, machines cool down. Processing times grow with waiting. This sequences deteriorating jobs optimally - and the surprise is that the rule stays clean: shortest BASE time first.

**Think of it like this:** Groceries after shopping: load the melting ice cream before the canned beans - waiting makes some jobs literally worse.

## When to reach for it

- Perishables, cooling processes, growing backlogs of urgency
- Any operation where delay has a compounding price

## Try it with supplycm

```python
from supplycm.scheduling import deteriorating_jobs_scheduling

result = deteriorating_jobs_scheduling(base_times=[2, 3, 1], deterioration_rates=[0.1, 0.2, 0.05])
print(result)
```

You should see something like:

```text
[1, 0, 2]
```

An order that front-loads wisely - with growing times, every delay multiplies, so the arithmetic punishes hesitation.

## Check yourself

1. How do deteriorating times change scheduling math?
2. Does SPT still work here?
3. What real systems quietly face deterioration?

<details>
<summary>Show answers</summary>

1. Completion of later jobs depends on ALL earlier delays - scheduling becomes about minimizing compounded growth.

2. Yes, remarkably - shortest base processing first remains optimal in classic models; the theorem survives deterioration.

3. Perishable supply chains, tax filing, maintenance backlogs - all priced by how long work sits.

</details>

## Try this now

Schedule [5, 1, 2] with rates [0.3, 0.1, 0.2] by hand two ways; compute total processing under each and compare.

---
[← No-Wait Scheduling](no_wait_scheduling.md) · [Back to Scheduling library](README.md) · [Learning Curve Scheduling →](learning_curve_scheduling.md)
