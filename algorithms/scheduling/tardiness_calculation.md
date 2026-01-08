---
title: "Tardiness Calculation | supplycm Algorithm Library"
description: "Plain-English explanation of tardiness_calculation from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, tardiness_calculation, supply chain, plain english, scheduling"
---

# Tardiness Calculation

> **Call it:** `from supplycm.scheduling import tardiness_calculation` · **Level:** Beginner · **You need:** basic arithmetic only

How late was each job, in total? Tardiness counts only the OVERDUE part: a job finishing 3 days late adds 3; early or on-time adds 0. This scores any sequence's total tardiness - the number every scheduling argument ultimately comes down to.

**Think of it like this:** Library fines: you only pay for days past due - returning early earns nothing but owes nothing.

## When to reach for it

- Scoring any proposed sequence before committing
- Reporting schedule quality in penalty terms

## Try it with supplycm

```python
from supplycm.scheduling import tardiness_calculation

result = tardiness_calculation(sequence=[0, 1, 2], processing_times=[4, 2, 8], due_dates=[5, 6, 8])
print(result)
```

You should see something like:

```text
6.0
```

Total tardiness for this order - swap two jobs, recompute, and you have the whole game of sequencing in one number.

## Check yourself

1. What counts as zero tardiness?
2. Why is total tardiness hard to optimize?
3. What's the difference between tardiness and lateness?

<details>
<summary>Show answers</summary>

1. Any job finishing at or before its due date - earliness is free, lateness is priced.

2. It's stubbornly non-linear - small order changes can swing totals wildly; that's why heuristics and rules exist.

3. Lateness can be negative (early); tardiness floors at zero - tardiness is what customers and penalties actually feel.

</details>

## Try this now

Compute tardiness for two different orders of the same jobs; crown the winner and explain the swap that mattered.

---
[← Moore-Hodgson Algorithm](moore_hodgson.md) · [Back to Scheduling library](README.md) · [Total Completion Time →](total_completion_time.md)
