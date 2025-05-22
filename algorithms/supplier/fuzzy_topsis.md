---
title: "Fuzzy TOPSIS | supplycm Algorithm Library"
description: "Plain-English explanation of fuzzy_topsis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, fuzzy_topsis, supply chain, plain english, supplier & procurement"
---

# Fuzzy TOPSIS

> **Call it:** `from supplycm.supplier import fuzzy_topsis` · **Level:** Advanced · **You need:** basic arithmetic only

Fuzzy TOPSIS lets judges answer in ranges - 'quality is about 7 to 9, probably 8' - instead of pretending one decimal is truth. The math (triangular fuzzy numbers) works through the same TOPSIS logic and returns the ranking. Use it when human judgment, not hard data, drives the scores.

**Think of it like this:** Instead of guessing your commute takes exactly 34 minutes, you say '30 to 40, usually 35' - and the planner respects the uncertainty.

## When to reach for it

- Panel evaluations with linguistic judgments (low/medium/high)
- Early-stage decisions where precision is fake but ranking matters

## Try it with supplycm

```python
from supplycm.supplier import fuzzy_topsis

result = fuzzy_topsis(fuzzy_decision=[[(7, 8, 9), (100, 120, 140)], [(6, 7, 8), (90, 100, 110)]], weights=[(0.5, 0.6, 0.7), (0.3, 0.4, 0.5)])
print(result)
```

You should see something like:

```text
[0, 1]
```

Indices ranked best first - the method respected each judge's uncertainty instead of forcing fake precision on day one.

## Check yourself

1. What is a triangular fuzzy number?
2. When is fuzzy scoring worth the extra effort?
3. Fuzzy TOPSIS and classic TOPSIS disagree. Why?

<details>
<summary>Show answers</summary>

1. A best-estimate range (low, most-likely, high) - honesty about imprecision, written as three numbers.

2. When inputs are judgments from people - the ranges carry real information that single numbers destroy.

3. Different treatment of uncertainty - if the fuzzy winner sits inside your ranges' noise, the difference may not be meaningful.

</details>

## Try this now

Score 3 suppliers with linguistic ranges for quality and delivery; run fuzzy TOPSIS and compare with your gut ranking.

---
[← TOPSIS](topsis.md) · [Back to Supplier & Procurement library](README.md) · [PROMETHEE →](promethee.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
