---
title: "Rural Postman Problem | supplycm Algorithm Library"
description: "Plain-English explanation of rural_postman from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, rural_postman, supply chain, plain english, routing & transportation"
---

# Rural Postman Problem

> **Call it:** `from supplycm.routing import rural_postman` · **Level:** Advanced · **You need:** basic arithmetic only

Only SOME streets need coverage - the required subset - while others are optional connectors. The rural postman serves all required edges at minimum cost, using optional roads only when they help. Subtly harder than the Chinese Postman, endlessly practical.

**Think of it like this:** A groundskeeper must line every soccer pitch (required) but may cut across any path (optional) - the mowing plan only pays for the pitches.

## When to reach for it

- Winter gritting of designated priority roads
- Inspection rounds covering only regulated assets

## Try it with supplycm

```python
from supplycm.routing import rural_postman

result = rural_postman(adjacency={0: [(1, 2), (2, 2)], 1: [(0, 2), (2, 3)], 2: [(0, 2), (1, 3)]}, required_edges={(0, 1), (1, 2)})
print(result)
```

You should see something like:

```text
[[0, 1, 2], 10.0]
```

The route and cost - required edges all covered; optional edges joined the tour only where they connected cheaply.

## Check yourself

1. What makes rural postman harder than Chinese postman?
2. When does it collapse to the Chinese Postman?
3. How would you model 'grit only priority roads'?

<details>
<summary>Show answers</summary>

1. Choosing WHICH optional edges to use is part of the problem - it bundles a design decision into the route.

2. When ALL edges are required - no selection remains, and the classic algorithm applies.

3. Priority roads = required edges; everything else = optional zero-obligation connectors - exactly this problem's inputs.

</details>

## Try this now

Mark only two required edges, rerun, and see which optional edge the route borrowed as a connector - and its price.

---
[← Chinese Postman Problem](chinese_postman.md) · [Back to Routing & Transportation library](README.md) · [Steiner Tree →](steiner_tree.md)
