---
title: "Process Capability (Cpk) | supplycm Algorithm Library"
description: "Plain-English explanation of process_capability_cpk from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, process_capability_cpk, supply chain, plain english, quality"
---

# Process Capability (Cpk)

> **Call it:** `from supplycm.quality import process_capability_cpk` · **Level:** Intermediate · **You need:** basic arithmetic only

Cpk is Cp's honest sibling: it also checks where the process is actually centered. Off-center processes get penalized because the side nearest the limit has less room. Cpk of at least 1.33 is a common customer requirement for suppliers.

**Think of it like this:** Parking WITH position: a narrow car parked hugging the line still clips the neighbor - position matters, not just size.

## When to reach for it

- Supplier qualification and audits
- Any time Cp looks fine but defects still happen (a centering problem)

## Try it with supplycm

```python
from supplycm.quality import process_capability_cpk

result = process_capability_cpk(upper_spec=10.2, lower_spec=9.8, mean=10.1, std_dev=0.05)
print(result)
```

You should see something like:

```text
0.6667
```

Cpk drops to about 0.67 - the process runs high in its spec window, so the upper side is running out of room even though Cp said 1.33.

## Check yourself

1. When is Cpk equal to Cp?
2. Cp 2.0 but Cpk 0.9 - what's wrong?
3. Customer demands Cpk 1.33. You measure 1.1. Options?

<details>
<summary>Show answers</summary>

1. When the process mean sits exactly in the middle of the spec limits.

2. The process is badly off-center; recentring alone could restore much of the potential.

3. Cut variation, recentre the mean, or negotiate specs - in that order of preference.

</details>

## Try this now

For specs 5.0-5.4 with mean 5.28 and std 0.05, compute Cp and Cpk; explain the gap between them.

---
[← Process Capability (Cp)](process_capability_cp.md) · [Back to Quality library](README.md) · [X-Bar Control Chart →](x_bar_chart.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
