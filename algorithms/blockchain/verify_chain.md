---
title: "Chain Verification | supplycm Algorithm Library"
description: "Plain-English explanation of verify_chain from the supplycm Traceability & Blockchain module, with a runnable Python example and self-check questions."
keywords: "supplycm, blockchain, verify_chain, supply chain, plain english, traceability & blockchain"
---

# Chain Verification

> **Call it:** `from supplycm.blockchain import verify_chain` · **Level:** Intermediate · **You need:** basic arithmetic only

The audit half of the hash chain: recompute every fingerprint from the records and compare with the stored chain. All match means the history is intact; any mismatch means something was altered - and the first mismatch points at where.

**Think of it like this:** Checking a sewn button strip: pull each button - the first loose one tells you where the stitching (and the story) was tampered with.

## When to reach for it

- Accepting or rejecting a provenance history at goods receipt
- Periodic integrity audits of event logs

## Try it with supplycm

```python
from supplycm.blockchain import verify_chain

result = verify_chain(records=[{'event': 'harvest', 'location': 'farm-7'}, {'event': 'ship', 'location': 'port'}], hashes=['abc123', 'def456'])
print(result)
```

You should see something like:

```text
False
```

True or False - recomputed fingerprints either reproduce the stored chain exactly or expose the edit; there is no 'mostly valid'.

## Check yourself

1. What does verification actually recompute?
2. Verification passes. What have you proven - and not proven?
3. Where should the chain's root be anchored for real trust?

<details>
<summary>Show answers</summary>

1. Every hash from the raw records, chaining each into the next - a full re-derivation, not a spot check.

2. That records match the chain as given - not that the events truly happened; authenticity of the FIRST record is a separate trust question.

3. In something independent - published checkpoints, multiple custodians - so rewriting history requires rewriting the world, not just your database.

</details>

## Try this now

Verify the intact chain from hash_chain, then rerun after editing one record - watch False appear and locate the break.

---
[← Hash Chain](hash_chain.md) · [Back to Traceability & Blockchain library](README.md) · [Provenance Tracking →](provenance_tracking.md)
