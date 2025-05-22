---
title: "ELECTRE | supplycm Algorithm Library"
description: "Plain-English explanation of electre from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, electre, supply chain, plain english, supplier & procurement"
---

# ELECTRE

> **Call it:** `from supplycm.supplier import electre` · **Level:** Advanced · **You need:** basic arithmetic only

ELECTRE builds 'outranking' statements: alternative i beats j when enough weighted criteria agree (concordance) AND no single criterion screams against it (discordance). Output is a list of i-beats-j pairs - a map of who genuinely dominates whom, including 'neither' results.

**Think of it like this:** A boxing judge requiring both majority rounds won AND no knockout against - dominance must be broad, not a one-punch fluke.

## When to reach for it

- Screening alternatives where one catastrophic weakness must veto
- Shortlisting: find which options truly dominate before fine ranking

## Try it with supplycm

```python
from supplycm.supplier import electre

result = electre(decision_matrix=[[8, 2], [6, 7], [9, 1]], weights=[0.5, 0.5], concordance_threshold=0.7, discordance_threshold=0.3)
print(result)
```

You should see something like:

```text
[]
```

The returned pairs show who outranks whom - alternatives absent from all pairs are neither dominant nor dominated and need a closer look.

## Check yourself

1. What role does the discordance threshold play?
2. ELECTRE returns no relation between A and B. Meaning?
3. Concordance 0.7 means what?

<details>
<summary>Show answers</summary>

1. It is the veto: one criterion being bad enough can block an outranking no matter how well the rest score.

2. Incomparability - the evidence does not crown either; decide with other information.

3. At least 70% of criterion weight must support 'i at least as good as j' before i can outrank it.

</details>

## Try this now

Build a 4x3 matrix where one option is excellent except for a catastrophic delivery score; show ELECTRE's veto in action.

---
[← PROMETHEE](promethee.md) · [Back to Supplier & Procurement library](README.md) · [Data Envelopment Analysis (DEA) →](data_envelopment_analysis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
