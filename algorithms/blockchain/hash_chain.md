---
title: "Hash Chain | supplycm Algorithm Library"
description: "Plain-English explanation of hash_chain from the supplycm Traceability & Blockchain module, with a runnable Python example and self-check questions."
keywords: "supplycm, blockchain, hash_chain, supply chain, plain english, traceability & blockchain"
---

# Hash Chain

> **Call it:** `from supplycm.blockchain import hash_chain` · **Level:** Intermediate · **You need:** basic arithmetic only

A chain of digital fingerprints: each event's fingerprint includes the PREVIOUS event's fingerprint, so every record is welded to the one before. Change any record - even silently, even years later - and every fingerprint after it stops matching. Tampering becomes visible.

**Think of it like this:** A numbered wax-seal chain on shipping documents: each seal covers the previous seal - forging page 3 means every later seal must be perfectly forged too.

## When to reach for it

- Making event logs tamper-evident (provenance, custody chains)
- Any audit trail where silent edits must be impossible to hide

## Try it with supplycm

```python
from supplycm.blockchain import hash_chain

result = hash_chain(records=[{'event': 'harvest', 'location': 'farm-7'}, {'event': 'ship', 'location': 'port'}, {'event': 'receive', 'location': 'warehouse-2'}])
print(result)
```

You should see something like:

```text
['4f608f12c5621b6bd3ec61af6fb915734daf0495bf06d03e06495b601cf2928e', 'a6bd81bbd9676aad874204a4e099d1a587caaaadc08320ca2d49ef4bfecfb02e', 'f13a0c969359ca80b632d6f9bab34d1e2dd6098f6b85e4e2f559f236181b122c']
```

A list of fingerprints - each one computed from its record PLUS the previous fingerprint; the chain is only as trustworthy as its start.

## Check yourself

1. Why does including the previous hash make tampering visible?
2. What is a 'fingerprint' (hash) here?
3. What does a hash chain NOT protect?

<details>
<summary>Show answers</summary>

1. Editing record 2 changes its hash, which no longer matches what record 3 embedded - the break cascades to the end.

2. A short digital summary of the data - change one letter in the data and the fingerprint changes completely.

3. The first record and the system writing it - trust still anchors at the origin and at who controls the keys.

</details>

## Try this now

Build a 4-event chain, then silently change one event's location; re-hash and pinpoint where verification snaps.

---
[Back to Traceability & Blockchain library](README.md) · [Chain Verification →](verify_chain.md)
