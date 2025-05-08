---
title: "Supplier Audit Score | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_audit_score from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_audit_score, supply chain, plain english, supplier & procurement"
---

# Supplier Audit Score

> **Call it:** `from supplycm.supplier import supplier_audit_score` · **Level:** Intermediate · **You need:** basic arithmetic only

Turns audit findings into section scores: for each area (quality, safety, environment...) you record findings against a maximum, and out come percentage scores per section. It shows exactly where a supplier is strong and where the corrective-action plan should point.

**Think of it like this:** A school report card per subject - not one vague 'B-, could do better', but 'math 90%, gym 55%'.

## When to reach for it

- After on-site supplier audits
- Tracking corrective actions between audit rounds

## Try it with supplycm

```python
from supplycm.supplier import supplier_audit_score

result = supplier_audit_score(findings={'quality': [1, 2], 'safety': [0], 'environment': [2, 3]}, max_scores={'quality': 10, 'safety': 5, 'environment': 10})
print(result)
```

You should see something like:

```text
{'quality': 0.15, 'safety': 0.0, 'environment': 0.25}
```

Safety is spotless; environment sits at half marks - that section heads the corrective action plan with a deadline.

## Check yourself

1. Why score sections separately instead of one total?
2. What is the follow-up ritual after a low section score?
3. Findings doubled at the same supplier year over year. Interpretations?

<details>
<summary>Show answers</summary>

1. Improvement needs a target - 'environment 50%' directs effort, 'overall 78%' does not.

2. Corrective actions with owners and dates, then a re-check - the next audit verifies closure, not intentions.

3. Worse performance OR better detection - compare against process changes before concluding either.

</details>

## Try this now

Score an invented audit across 4 sections; write the two corrective actions you would demand first.

---
[← Contract Compliance Score](contract_compliance_score.md) · [Back to Supplier & Procurement library](README.md) · [Composite Supplier Rating →](supplier_rating.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
