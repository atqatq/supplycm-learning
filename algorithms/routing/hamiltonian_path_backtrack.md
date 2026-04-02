---
title: "Hamiltonian Path (Backtracking) | supplycm Algorithm Library"
description: "Plain-English explanation of hamiltonian_path_backtrack from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, hamiltonian_path_backtrack, supply chain, plain english, routing & transportation"
---

# Hamiltonian Path (Backtracking)

> **Call it:** `from supplycm.routing import hamiltonian_path_backtrack` · **Level:** Advanced · **You need:** basic arithmetic only

Visit every node EXACTLY once - a path touching all stops with no repeats. Deciding whether such a path exists is famously hard; backtracking simply tries branches and abandons dead ends. On small graphs it answers cleanly; its hardness founded complexity theory's favorite problems.

**Think of it like this:** Designing a pub crawl visiting each pub once: some maps allow it, some don't - and checking every promising order is the only honest method known.

## When to reach for it

- One-visit-each route existence questions on small networks
- Understanding why some 'obvious' routing wishes are formally hard

## Try it with supplycm

```python
from supplycm.routing import hamiltonian_path_backtrack

result = hamiltonian_path_backtrack({0: [1], 1: [2], 2: [0]})
print(result)
```

You should see something like:

```text
[0, 1, 2]
```

A valid path (or None) - each node appears exactly once; tweak one edge and the answer can flip from found to impossible.

## Check yourself

1. Hamiltonian path vs Eulerian tour - what's the difference?
2. Why is this problem so hard computationally?
3. Where does it appear in logistics?

<details>
<summary>Show answers</summary>

1. Nodes vs edges: Hamiltonian visits each NODE once; Eulerian covers each EDGE once - one is hard, the other easy to detect.

2. No known efficient general test - existence questions multiply combinatorially, and the best methods still explore in the worst case.

3. Sequential tour puzzles - one visit per stop with strict uniqueness - though practice usually relaxes to optimization versions.

</details>

## Try this now

Remove one edge from the example graph and watch the path vanish - then restore a different edge and recover it.

---
[← Steiner Tree](steiner_tree.md) · [Back to Routing & Transportation library](README.md)
