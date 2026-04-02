---
title: "Eulerian Tour | supplycm Algorithm Library"
description: "Plain-English explanation of eulerian_tour from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, eulerian_tour, supply chain, plain english, routing & transportation"
---

# Eulerian Tour

> **Call it:** `from supplycm.routing import eulerian_tour` · **Level:** Intermediate · **You need:** basic arithmetic only

Walk every EDGE of a network exactly once and return to start - possible exactly when every node has an even number of connections. It is the mathematical soul of route inspection: cover every street, never repeat a step.

**Think of it like this:** A snowplow clever enough to plow every street once and end at the depot - the bridge-crossing puzzle, solved by Euler in 1736.

## When to reach for it

- Street sweeping, snow clearing, meter reading - edge-coverage work
- Checking whether a full-coverage no-repeat route even exists

## Try it with supplycm

```python
from supplycm.routing import eulerian_tour

result = eulerian_tour({0: [1, 2], 1: [0, 2], 2: [0, 1]})
print(result)
```

You should see something like:

```text
[0, 2, 1, 0]
```

A node sequence traversing every edge once - count the edges against the network to verify nothing repeated, nothing missed.

## Check yourself

1. What does 'even degree' guarantee?
2. How does this differ from the TSP?
3. What if the graph has odd-degree nodes?

<details>
<summary>Show answers</summary>

1. A closed tour using every edge once exists - the Euler condition; one odd node and it's impossible without duplication.

2. TSP minimizes visiting NODES; Eulerian tours cover EDGES exactly once - different object, different problem.

3. Some edges must be traversed twice - the Chinese Postman Problem computes the cheapest way to add those repeats.

</details>

## Try this now

Add one pendant node to the graph and prove no Eulerian tour exists; then explain what must be doubled.

---
[← Dial-a-Ride](dial_a_ride.md) · [Back to Routing & Transportation library](README.md) · [Chinese Postman Problem →](chinese_postman.md)
