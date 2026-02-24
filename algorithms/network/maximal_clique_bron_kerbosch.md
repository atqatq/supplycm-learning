---
title: "Maximal Clique (Bron-Kerbosch) | supplycm Algorithm Library"
description: "Plain-English explanation of maximal_clique_bron_kerbosch from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, maximal_clique_bron_kerbosch, supply chain, plain english, networks"
---

# Maximal Clique (Bron-Kerbosch)

> **Call it:** `from supplycm.network import maximal_clique_bron_kerbosch` · **Level:** Advanced · **You need:** basic arithmetic only

Finds cliques - groups where EVERYONE is connected to everyone. In supply terms: fully interoperable clusters, e.g. products that can share one machine group, or suppliers who can each substitute for one another. Bron-Kerbosch enumerates them exactly with a pivot trick that prunes dead ends.

**Think of it like this:** Party photos: a clique is the group where everyone would appear in a group shot - everyone knows everyone; strangers break the frame.

## When to reach for it

- Finding fully interchangeable product or supplier groups
- Detecting tightly coupled clusters (machine cells, component families)

## Try it with supplycm

```python
from supplycm.network import maximal_clique_bron_kerbosch

result = maximal_clique_bron_kerbosch(graph={0: [1, 2], 1: [0, 2], 2: [0, 1], 3: [4], 4: [3]})
print(result)
```

You should see something like:

```text
[[0, 1, 2], [3, 4]]
```

Cliques as node lists - {0,1,2} is a triangle of full interconnection; {3,4} forms its own mutual pair.

## Check yourself

1. What makes a group a 'clique'?
2. Why 'maximal' and not 'maximum'?
3. What supply chain question is a clique question?

<details>
<summary>Show answers</summary>

1. Complete interconnection - every member connects to every other; remove one link and it stops being maximal.

2. Maximal: can't add anyone more; maximum: the largest possible size. Bron-Kerbosch lists ALL maximal ones, from which the maximum is read off.

3. 'Which SKUs can run on the SAME line configuration with zero changeover between any pair?' - full mutual compatibility.

</details>

## Try this now

Map product-line compatibility for 5 products; find the largest clique and propose the cell layout it implies.

---
[← Strongly Connected Components](strongly_connected_components.md) · [Back to Networks library](README.md) · [Topological Sort →](topological_sort.md)
