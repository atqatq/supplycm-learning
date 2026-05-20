---
title: "Provenance Tracking | supplycm Algorithm Library"
description: "Plain-English explanation of provenance_tracking from the supplycm Traceability & Blockchain module, with a runnable Python example and self-check questions."
keywords: "supplycm, blockchain, provenance_tracking, supply chain, plain english, traceability & blockchain"
---

# Provenance Tracking

> **Call it:** `from supplycm.blockchain import provenance_tracking` · **Level:** Beginner · **You need:** basic arithmetic only

One product's complete life story, extracted from the stream of all supply chain events: harvested here, shipped there, stored there, sold there. Filter by product, sort by time - and 'where has this been?' becomes a lookup, not an investigation.

**Think of it like this:** A pet passport: every checkpoint stamped in order - one glance shows the full journey, stamps and all.

## When to reach for it

- Recalls: exactly which batches went where
- Authenticity and origin claims customers can actually verify

## Try it with supplycm

```python
from supplycm.blockchain import provenance_tracking

result = provenance_tracking(events=[{'product': 'A1', 'event': 'harvest', 'day': 1}, {'product': 'B2', 'event': 'harvest', 'day': 1}, {'product': 'A1', 'event': 'ship', 'day': 3}, {'product': 'A1', 'event': 'sale', 'day': 9}], product_id='A1')
print(result)
```

You should see something like:

```text
[{'product': 'A1', 'event': 'harvest', 'day': 1}, {'product': 'A1', 'event': 'ship', 'day': 3}, {'product': 'A1', 'event': 'sale', 'day': 9}]
```

A1's three events in chronological order - its whole biography, cleanly separated from B2's parallel life.

## Check yourself

1. Why is provenance critical during recalls?
2. What makes a provenance trail credible?
3. How does this connect to blockchain thinking?

<details>
<summary>Show answers</summary>

1. Scope: you recall the exact affected batches and destinations - not everything, not too little; precision saves money and trust.

2. Every event anchored at its time and place, ideally hash-chained or third-party witnessed - unanchored stories are just stories.

3. Blockchain is one way to make the trail tamper-evident; provenance is the QUESTION, chain structures are one ANSWER.

</details>

## Try this now

Log 6 events across 3 products; extract each product's story and check for the missing checkpoint that would worry an auditor.

---
[← Chain Verification](verify_chain.md) · [Back to Traceability & Blockchain library](README.md) · [Smart Contract Check →](smart_contract_check.md)
