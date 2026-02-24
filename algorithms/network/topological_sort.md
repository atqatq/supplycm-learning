---
title: "Topological Sort | supplycm Algorithm Library"
description: "Plain-English explanation of topological_sort from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, topological_sort, supply chain, plain english, networks"
---

# Topological Sort

> **Call it:** `from supplycm.network import topological_sort` · **Level:** Intermediate · **You need:** basic arithmetic only

For dependency networks (task A before task B...), topological sort lines up all nodes so every prerequisite comes first. It answers 'a valid order to do everything in' - the checklist behind build systems, course prerequisites, and assembly steps.

**Think of it like this:** Getting dressed: socks before shoes, shirt before jacket - any order obeying the rules works; the sort finds one.

## When to reach for it

- Sequencing tasks with dependencies (BOM steps, onboarding plans)
- Detecting impossible requirements (circular dependencies)

## Try it with supplycm

```python
from supplycm.network import topological_sort

result = topological_sort(graph={0: [1, 2], 1: [3], 2: [3], 3: []})
print(result)
```

You should see something like:

```text
[0, 1, 2, 3]
```

A valid order: 0 first (nothing depends on it), 3 last (it depends on everything) - every arrow points forward.

## Check yourself

1. What makes an order 'valid'?
2. What happens with a dependency cycle?
3. Why does BOM planning care?

<details>
<summary>Show answers</summary>

1. Every edge points from earlier to later - no task precedes its own prerequisite.

2. No valid order exists - the sort comes up short; the cycle is a design bug to unwind.

3. Exploding a BOM requires parents before children in planning logic - topological order guarantees it.

</details>

## Try this now

Add a circular dependency (1 needs 2, 2 needs 1) and verify no ordering exists; then break the cycle and retry.

---
[← Maximal Clique (Bron-Kerbosch)](maximal_clique_bron_kerbosch.md) · [Back to Networks library](README.md) · [Articulation Points →](articulation_points.md)
