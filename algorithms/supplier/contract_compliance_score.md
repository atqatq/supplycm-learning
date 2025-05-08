---
title: "Contract Compliance Score | supplycm Algorithm Library"
description: "Plain-English explanation of contract_compliance_score from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, contract_compliance_score, supply chain, plain english, supplier & procurement"
---

# Contract Compliance Score

> **Call it:** `from supplycm.supplier import contract_compliance_score` · **Level:** Intermediate · **You need:** basic arithmetic only

Checks the box list inside a contract - insurance certificates, SLA reports, audits, training - and scores the share actually in place. It converts 'I think they are fine' into a percentage the audit committee can track.

**Think of it like this:** A pre-flight checklist: each item is binary, and the score tells you whether takeoff is responsible.

## When to reach for it

- Supplier onboarding and annual contract reviews
- Preparing for customer or regulator audits

## Try it with supplycm

```python
from supplycm.supplier import contract_compliance_score

result = contract_compliance_score(terms={'insurance': True, 'sla_reporting': True, 'audit_rights': False, 'backup_plan': False})
print(result)
```

You should see something like:

```text
0.5
```

50% of terms verified - the two false boxes are exactly where risk hides; each has an owner and a due date now.

## Check yourself

1. Why reduce a contract to checkboxes?
2. Which terms usually fail first?
3. Score improved 60% to 95% - done?

<details>
<summary>Show answers</summary>

1. Because unverified clauses are wishes; a score forces someone to evidence each one.

2. The boring ones: current insurance certificates, tested contingency plans, up-to-date compliance reports.

3. No - compliance drifts; set a review cadence or it slides back within two quarters.

</details>

## Try this now

List 6 contract terms for a critical supplier, score one honestly, and assign owners to every false box.

---
[← Competitive Bidding](competitive_bidding.md) · [Back to Supplier & Procurement library](README.md) · [Supplier Audit Score →](supplier_audit_score.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
