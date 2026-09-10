---
title: "Closeness Centrality | supplycm Algorithm Library"
description: "Plain-English explanation of closeness_centrality from the supplycm Networks module - a reserved slot in supplycm v1.2.1 - with a teaching example and self-check questions."
keywords: "supplycm, network, closeness_centrality, supply chain, plain english, networks"
---

# Closeness Centrality

> **Call it:** `supplycm.network.closeness_centrality` - **a reserved slot in supplycm v1.2.1** (the file ships as a stub, so there is nothing to import yet - see below) · **Level:** Intermediate · **You need:** basic arithmetic only

Degree counted HOW MANY links a node has. Closeness asks a sharper question: how CLOSE is this node to EVERYONE else? Add up the shortest-path hops from one node to all the others, and you get its total farness. A small total means the node sits near the middle of everything - that is the node you want running point. It answers one very supply-chain question: "how fast can this spot reach the whole network?"

**Think of it like this:** Choosing where to live in a city. A home that is 10 minutes from the airport, the office, AND the market beats a bigger home stuck 60 minutes from everything. Closeness is the "everything is near me" score - not the size of the house, but the reach from the doorstep.

## When to reach for it

- Picking a pilot site, a hub, or a spare-parts depot that should reach every other node in few hops
- Comparing candidate locations on reach speed, not just on link count
- Finding slow corners of a network: low closeness nodes are the ones waiting on everyone else

## Try it with supplycm

Honest note first: in supplycm v1.2.1, `network/closeness_centrality.py` is a placeholder - a docstring and two imports, no function yet. The package reserved the name, and the README counts it among its 397 algorithm slots. So this page teaches the IDEA with a tiny stand-in you can run today; the day the real function lands, the swap is one line - `from supplycm.network import closeness_centrality`.

```python
# Teaching stand-in for the reserved supplycm slot (pure standard library).
from collections import deque

def closeness(graph, start):
    dist = {start: 0}
    queue = deque([start])
    while queue:                      # walk outward in rings, like BFS
        node = queue.popleft()
        for nxt in graph[node]:
            if nxt not in dist:
                dist[nxt] = dist[node] + 1
                queue.append(nxt)
    total = sum(dist.values())        # total hops to reach everyone
    return round((len(dist) - 1) / total, 4) if total else 0.0

network = {0: [1], 1: [0, 2], 2: [1, 3], 3: [2, 4], 4: [3]}  # a line: 0-1-2-3-4
print(closeness(network, 0))  # an END of the line
print(closeness(network, 2))  # the MIDDLE of the line
```

You should see something like:

```text
0.4
0.6667
```

Same line, different seats. From the end node 0, the other nodes sit 1, 2, 3, and 4 hops away - 10 hops in total, so 4 ÷ 10 = 0.4. From the middle node 2, every target is 1 or 2 hops away: 6 hops total, so 4 ÷ 6 = 0.6667. The middle node reaches everyone in fewer hops on average - closeness sees POSITION, not just link counts.

## Check yourself

1. Degree counts links. What does closeness count?
2. In supply chain words, what does a high-closeness warehouse give you?
3. Both ends of a line have 1 link each. Why does closeness still rate the middle node higher?

<details>
<summary>Show answers</summary>

1. Shortest hops to EVERYONE. Degree counts direct links; closeness averages the shortest paths to all other nodes - so a well-placed node can beat a busier one stuck at the edge.

2. Speed of reach. Fewer hops to every store, plant, or customer means faster service, quicker rebalancing, and less time in transit when something goes wrong.

3. Because the middle sits near everyone. The two ends are far from each other, but the middle is 1-2 hops from ALL four others. Links alone can't see that - distance can.

</details>

## Try this now

Draw a line of 5 stores: A-B-C-D-E. Guess first which store, B or C, is closer to everyone - then check with basic arithmetic. Count the hops from each to all four other stores, add them up, and divide 4 by each total (round to 4 decimals). B's total is 7, C's total is 6 - so C wins, 0.5714 to 0.6667. If your guess was B because B comes first in the alphabet, you just learned why we measure instead of guess.

---
[← Degree Centrality](degree_centrality.md) · [Back to Networks library](README.md) · [Betweenness Centrality →](betweenness_centrality.md)
