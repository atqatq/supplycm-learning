---
title: "Spare Parts: VED Classification | supplycm Algorithm Library"
description: "Plain-English explanation of spare_parts_ved from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, spare_parts_ved, supply chain, plain english, inventory"
---

# Spare Parts: VED Classification

> **Call it:** `from supplycm.inventory import spare_parts_ved` · **Level:** Intermediate · **You need:** basic arithmetic only

VED ranks spares by CRITICALITY: Vital (the line stops without it), Essential (degradation, big pain), Desirable (nice to have). Criticality - not price, not movement - decides policy: Vital parts get redundancy and strict control even if they cost 12 dollars.

**Think of it like this:** A car's parts: the 20-dollar fuel pump relay is Vital; the cup holder is Desirable - the price tag never told that story.

## When to reach for it

- Setting stock and control policy for maintenance inventory
- Arguing against managing a 12-dollar part like a 12-dollar part

## Try it with supplycm

```python
from supplycm.inventory import spare_parts_ved

result = spare_parts_ved(criticality_scores=[('relay', 0.95), ('housing', 0.4), ('knob', 0.1)])
print(result)
```

You should see something like:

```text
[['relay', 'V'], ['housing', 'E'], ['knob', 'D']]
```

Classes come back - the cheap relay lands Vital and earns a spare on the shelf; the pricey-looking housing stays merely Essential.

## Check yourself

1. How is criticality measured objectively?
2. A Vital part is also a Non-mover (FSN). Stock it or not?
3. Who should own VED scores?

<details>
<summary>Show answers</summary>

1. Downtime impact, safety consequences, redundancy available - often a scored assessment by engineering, not a purchase price.

2. Usually stock at least one - the consequence of absence is catastrophic; that's the VED lens overriding the FSN lens.

3. Engineering and maintenance jointly - criticality is technical truth, not purchasing opinion.

</details>

## Try this now

Score 6 real spares on criticality, cross them with your FSN guesses, and write one policy line for the Vital-Non-movers.

---
[← Spare Parts: FSN Classification](spare_parts_fsn.md) · [Back to Inventory library](README.md) · [Spare Parts: HML Classification →](spare_parts_hml.md)
