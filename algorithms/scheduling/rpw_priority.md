---
title: "RPW Priority (Ranked Positional Weight) | supplycm Algorithm Library"
description: "Plain-English explanation of rpw_priority from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, rpw_priority, supply chain, plain english, scheduling"
---

# RPW Priority (Ranked Positional Weight)

> **Call it:** `from supplycm.scheduling import rpw_priority` · **Level:** Advanced · **You need:** basic arithmetic only

For line balancing and complex networks: a task's priority = its own time PLUS the total time of everything that must follow it. Tasks carrying heavy downstream chains go first. It is EDD-style urgency computed from the network itself.

**Think of it like this:** Airport boarding: passengers with tight connections (heavy downstream) board before leisure travelers - the weight of what follows decides.

## When to reach for it

- Assembly line balancing task ordering
- Project dispatching when downstream chains matter

## Try it with supplycm

```python
from supplycm.scheduling import rpw_priority

result = rpw_priority(task_times=[3, 2, 4, 1], successors=[[1, 2], [], [3], []])
print(result)
```

You should see something like:

```text
[0, 2, 1, 3]
```

Tasks ranked by positional weight - task 0 tops the list because everything else dangles beneath it.

## Check yourself

1. What does 'positional weight' capture?
2. When does RPW shine over simple time rules?
3. How does RPW relate to critical path?

<details>
<summary>Show answers</summary>

1. The full downstream burden - a task is as heavy as itself plus its entire future chain.

2. Networked tasks - it respects structure that 'longest task first' ignores entirely.

3. It's a cousin: both price downstream consequences, but RPW produces a dispatch order, not a path.

</details>

## Try this now

Compute weights by hand for the example; verify the total-following chain of the top task beats the runner-up's.

---
[← PERT Expected Duration](pert_expected_duration.md) · [Back to Scheduling library](README.md) · [Line Balancing →](line_balancing.md)
