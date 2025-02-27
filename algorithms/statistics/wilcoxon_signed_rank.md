---
title: "Wilcoxon Signed-Rank | supplycm Algorithm Library"
description: "Plain-English explanation of wilcoxon_signed_rank from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, wilcoxon_signed_rank, supply chain, plain english, statistics & accuracy"
---

# Wilcoxon Signed-Rank

> **Call it:** `from supplycm.statistics import wilcoxon_signed_rank` · **Level:** Advanced · **You need:** basic arithmetic only

Tests paired before/after differences: rank the sizes of the changes and see whether positive or negative changes dominate. It answers 'did the change really move things, in either direction?' without assuming bell curves - great for before/after process studies.

**Think of it like this:** Judging a diet by each person's personal before/after change, not by comparing different people.

## When to reach for it

- Evaluating a process change with matched before/after data
- Small-sample improvement projects where t-tests are risky

## Try it with supplycm

```python
from supplycm.statistics import wilcoxon_signed_rank

result = wilcoxon_signed_rank([-3, 5, -2, 8, -1, 6, 2, -4])
print(result)
```

You should see something like:

```text
23.5
```

A positive-leaning statistic - the improvements outweigh the regressions, hinting the change helped overall.

## Check yourself

1. What makes a test 'paired'?
2. A change of -1 vs -10: same rank weight?
3. You changed the packing process in 8 stores (paired data). W+ is strongly positive. Conclusion?

<details>
<summary>Show answers</summary>

1. Each observation has a natural partner: same store before/after, same machine old/new.

2. No - ranks use the SIZE of changes: bigger absolute changes rank higher.

3. The change tended to improve the measured outcome - consider a rollout.

</details>

## Try this now

Invent paired defect counts for 10 lines before/after a fix; run the test and give a go/no-go recommendation.

---
[← Mann-Whitney U](mann_whitney_u.md) · [Back to Statistics & Accuracy library](README.md)
