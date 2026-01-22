---
title: "List Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of list_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, list_scheduling, supply chain, plain english, scheduling"
---

# List Scheduling

> **Call it:** `from supplycm.scheduling import list_scheduling` · **Level:** Intermediate · **You need:** basic arithmetic only

The general-purpose parallel dispatcher: keep a list of jobs, assign each next job to whichever machine frees up first. Whatever order your list uses (SPT, LPT, priorities), the 'next free machine' mechanic does the spreading. Simple, robust, everywhere.

**Think of it like this:** A bank with several tellers: each finished teller calls 'next!' - the queue order is your policy, the calling is automatic.

## When to reach for it

- Any parallel-machine dispatching with a chosen priority order
- The base algorithm behind most practical shop-floor dispatchers

## Try it with supplycm

```python
from supplycm.scheduling import list_scheduling

result = list_scheduling(processing_times=[8, 3, 5, 2, 7], num_machines=2)
print(result)
```

You should see something like:

```text
[[0, 3], [1, 2, 4]]
```

Machine assignments in list order - each job landed on the earliest-available machine; trace which machine freed up when.

## Check yourself

1. What makes list scheduling so widely used?
2. Does the list order matter?
3. When does list scheduling struggle?

<details>
<summary>Show answers</summary>

1. It accepts ANY priority order and never needs lookahead - perfect for dynamic, changing shops.

2. Enormously - the same mechanic with LPT vs SPT can double the makespan; the policy is the schedule.

3. When jobs need specific machines or setups - pure 'next free' logic ignores those realities unless extended.

</details>

## Try this now

Run it with LPT order vs input order; compare both machines' finishing times and explain the divergence.

---
[← LPT (Longest Processing Time)](lpt_rule.md) · [Back to Scheduling library](README.md) · [SRPT (Shortest Remaining Processing Time) →](srpt_rule.md)
