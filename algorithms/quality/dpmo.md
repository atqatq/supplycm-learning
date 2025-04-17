---
title: "DPMO (Defects Per Million Opportunities) | supplycm Algorithm Library"
description: "Plain-English explanation of dpmo from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, dpmo, supply chain, plain english, quality"
---

# DPMO (Defects Per Million Opportunities)

> **Call it:** `from supplycm.quality import dpmo` · **Level:** Beginner · **You need:** basic arithmetic only

DPMO scales your defect count to 'how many mistakes would we make per million chances?'. You count defects, units made, and chances for a mistake per unit. It lets a tiny sample speak in millions - the standard Six Sigma scoreboard.

**Think of it like this:** A batting average scaled to a full career: few at-bats today, but the number tells the long-run story.

## When to reach for it

- Reporting process quality in one comparable number across lines/plants
- Tracking improvement over time on the same process

## Try it with supplycm

```python
from supplycm.quality import dpmo

result = dpmo(defects=7, units=400, opportunities_per_unit=5)
print(result)
```

You should see something like:

```text
3500.0
```

3,500 DPMO - on a million chances this process would produce about 3,500 defects, roughly a 99.65% chance of getting each chance right.

## Check yourself

1. What counts as an 'opportunity'?
2. Why multiply to a million?
3. 10 defects, 200 units, 1 opportunity each. DPMO?

<details>
<summary>Show answers</summary>

1. Any spot where a mistake could happen - a form field, a solder joint, a picking slot.

2. Real samples are small; scaling makes tiny defect rates comparable and discussable.

3. 50,000 - a 5% defect rate expressed per million.

</details>

## Try this now

A warehouse mis-picks 12 of 3,000 lines; each line has 3 chances to err. Compute DPMO and compare it to a 4-sigma target.

---
[Back to Quality library](README.md) · [Sigma Level →](sigma_level.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
