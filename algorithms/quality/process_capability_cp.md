---
title: "Process Capability (Cp) | supplycm Algorithm Library"
description: "Plain-English explanation of process_capability_cp from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, process_capability_cp, supply chain, plain english, quality"
---

# Process Capability (Cp)

> **Call it:** `from supplycm.quality import process_capability_cp` · **Level:** Intermediate · **You need:** basic arithmetic only

Cp asks: IF this process were centered, would its natural spread fit inside the spec limits? It compares the spec width to six standard deviations of the process. Cp of 2 means the spread is half the tolerance - lots of room. Below 1 means the process cannot fit, no matter the centering.

**Think of it like this:** Parking a car: Cp measures whether the car is narrow enough for the space at all - not whether you parked it centered.

## When to reach for it

- Quickly judging whether a process CAN meet specs in principle
- Comparing potential across machines doing the same job

## Try it with supplycm

```python
from supplycm.quality import process_capability_cp

result = process_capability_cp(upper_spec=10.2, lower_spec=9.8, std_dev=0.05)
print(result)
```

You should see something like:

```text
1.3333
```

About 1.33 - the process spread fits with some margin, but there is not much slack for drift.

## Check yourself

1. What does Cp ignore that Cpk checks?
2. Cp = 0.8. Can better centering save this process?
3. Spec width 0.4, std 0.1. Cp?

<details>
<summary>Show answers</summary>

1. Centering - Cp assumes perfect centering; Cpk penalizes off-center processes.

2. No - the spread itself is too wide; you must reduce variation, not move the average.

3. 0.4 / 0.6 = about 0.67 - hopeless without cutting variation.

</details>

## Try this now

Compute Cp for spec 10.0 +/- 0.15 with std 0.04, then with std 0.06 - interpret both in one line each.

---
[← Sigma Level](sigma_level.md) · [Back to Quality library](README.md) · [Process Capability (Cpk) →](process_capability_cpk.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
