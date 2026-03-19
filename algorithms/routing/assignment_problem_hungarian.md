---
title: "Hungarian Algorithm (Assignment) | supplycm Algorithm Library"
description: "Plain-English explanation of assignment_problem_hungarian from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, assignment_problem_hungarian, supply chain, plain english, routing & transportation"
---

# Hungarian Algorithm (Assignment)

> **Call it:** `from supplycm.routing import assignment_problem_hungarian` · **Level:** Intermediate · **You need:** basic arithmetic only

N workers, N tasks, a cost for every pairing: find the one-to-one assignment with the MINIMUM total cost. The Hungarian algorithm does it exactly and efficiently - the legendary optimal answer to 'who does what' questions.

**Think of it like this:** Matching six translators to six documents by skill and topic - each translator takes exactly one document, and the total effort lands at its provable minimum.

## When to reach for it

- Optimal assignment: technicians to jobs, drivers to vehicles
- Any one-to-one matching with a full cost matrix

## Try it with supplycm

```python
from supplycm.routing import assignment_problem_hungarian

result = assignment_problem_hungarian(cost_matrix=[[4, 1, 3], [2, 0, 5], [3, 2, 2]])
print(result)
```

You should see something like:

```text
[[[1, 0], [0, 1], [2, 2]], 5.0]
```

The chosen pairs and total cost 5 - each worker got exactly one task, and no other assignment beats the total.

## Check yourself

1. What kind of problems does Hungarian solve exactly?
2. What if a worker can take TWO tasks?
3. Where does the matrix come from in practice?

<details>
<summary>Show answers</summary>

1. Square one-to-one assignments - optimal, not heuristic, in fast polynomial time.

2. Duplicate the worker's row - capacity 2 becomes two identical rows; the math absorbs it happily.

3. Time-and-motion data or fit scores - the algorithm is only as honest as the costs you feed it.

</details>

## Try this now

Assign 4 techs to 4 jobs with your own cost matrix; verify optimality by trying two hand-made alternatives.

---
[← TSP Christofides Algorithm](tsp_christofides.md) · [Back to Routing & Transportation library](README.md) · [Northwest Corner Method →](northwest_corner_method.md)
