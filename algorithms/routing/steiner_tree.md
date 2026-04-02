---
title: "Steiner Tree | supplycm Algorithm Library"
description: "Plain-English explanation of steiner_tree from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, steiner_tree, supply chain, plain english, routing & transportation"
---

# Steiner Tree

> **Call it:** `from supplycm.routing import steiner_tree` · **Level:** Advanced · **You need:** basic arithmetic only

Connect a chosen set of terminals as cheaply as possible - possibly through NON-terminal junction points. Unlike the MST (which connects everyone), Steiner picks its intermediate nodes strategically: sometimes a highway junction serves three cities better than three roads.

**Think of it like this:** Building fiber to five offices: you may run cable through exchange boxes nobody works at - if junctions make the network cheaper, use them.

## When to reach for it

- Connecting key sites via optional hubs (network build-out)
- Pipeline or cable layout where junction nodes are legal

## Try it with supplycm

```python
from supplycm.routing import steiner_tree

result = steiner_tree(distances=[[0, 4, 4, 3], [4, 0, 2, 5], [4, 2, 0, 1], [3, 5, 1, 0]], terminals={0, 3})
print(result)
```

You should see something like:

```text
[[[0, 3]], 3.0]
```

The chosen edges and total cost - note which intermediate nodes earned their way in and which the tree ignored.

## Check yourself

1. Steiner tree vs MST - what's the essential difference?
2. Why would a non-terminal node help?
3. What's the computational catch?

<details>
<summary>Show answers</summary>

1. MST must connect ALL nodes; Steiner connects only terminals and CHOOSES helpful intermediates - freedom that buys savings.

2. It can act as a cheap junction - three roads meeting at one point often cost less than pairwise connections.

3. Choosing intermediates is NP-hard - real instances rely on heuristics; small ones get exact answers.

</details>

## Try this now

Compare this Steiner cost against the MST restricted to terminals; name the junction that paid for itself.

---
[← Rural Postman Problem](rural_postman.md) · [Back to Routing & Transportation library](README.md) · [Hamiltonian Path (Backtracking) →](hamiltonian_path_backtrack.md)
