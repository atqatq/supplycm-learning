---
title: "Smart Contract Check | supplycm Algorithm Library"
description: "Plain-English explanation of smart_contract_check from the supplycm Traceability & Blockchain module, with a runnable Python example and self-check questions."
keywords: "supplycm, blockchain, smart_contract_check, supply chain, plain english, traceability & blockchain"
---

# Smart Contract Check

> **Call it:** `from supplycm.blockchain import smart_contract_check` · **Level:** Intermediate · **You need:** basic arithmetic only

Rules that enforce themselves: temperature below 8, delivery before Friday, quantity within tolerance - this validates any transaction against the rule list and returns pass or explicit violations. No meeting, no discretion: the contract is the code.

**Think of it like this:** A vending machine's logic: the right coins, the slot turns - no negotiation, no exceptions, every transaction judged identically.

## When to reach for it

- Cold-chain SLAs (temperature thresholds auto-checked)
- Automated payment releases and compliance gates

## Try it with supplycm

```python
from supplycm.blockchain import smart_contract_check

result = smart_contract_check(transaction={'product': 'vaccine-B', 'temp': 6.5, 'day': 4}, rules=[{'field': 'temp', 'operator': '<', 'value': 8.0}, {'field': 'day', 'operator': '<=', 'value': 5}])
print(result)
```

You should see something like:

```text
{'valid': True, 'violations': []}
```

Valid: True with an empty violations list - every rule evaluated mechanically; flip one number and the violation names itself.

## Check yourself

1. What makes a contract 'smart'?
2. What's the danger of overly strict automated rules?
3. Who must trust what here?

<details>
<summary>Show answers</summary>

1. Self-execution: rules evaluate automatically on data, and consequences (release, reject, alert) follow without human mediation.

2. Rigidity - real life has edge cases; good smart contracts pair hard rules with a documented exception path.

3. Both sides trust the rule code and the data feed - which is why sensor integrity and rule transparency come before automation.

</details>

## Try this now

Write 3 rules for a frozen-goods delivery, then feed two transactions - one pass, one fail - and read the violations aloud.

---
[← Provenance Tracking](provenance_tracking.md) · [Back to Traceability & Blockchain library](README.md)
