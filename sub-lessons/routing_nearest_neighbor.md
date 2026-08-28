---
title: "Nearest Neighbor Algorithm Explained Step by Step"
description: "Learn how the nearest neighbor algorithm works for solving TSP. Step-by-step routing example."
keywords: "nearest neighbor algorithm, TSP heuristic, routing algorithm, traveling salesman, greedy algorithm"
---

# How Nearest Neighbor Works

## The Problem

You need to visit 5 houses and return home. What order should you visit them in to travel the shortest distance?

## The Nearest Neighbor Method

1. Start at home
2. Go to the nearest unvisited house
3. Repeat until all houses are visited
4. Return home

## Step by Step Example

```python
# 5 locations (0 = home, 1-4 = houses)
distances = [
    [0,  10, 15, 20, 25],  # from home
    [10, 0,  35, 25, 30],  # from house 1
    [15, 35, 0,  30, 20],  # from house 2
    [20, 25, 30, 0,  15],  # from house 3
    [25, 30, 20, 15, 0],   # from house 4
]
```

### Step 1: Start at Home (location 0)

```python
current = 0
visited = [0]
total_distance = 0

print(f'Start at: Home (location {current})')
```

### Step 2: Find Nearest Unvisited

```python
# From home (0), distances are: [0, 10, 15, 20, 25]
# Nearest unvisited is house 1 (distance 10)

nearest = 1
distance = 10

total_distance += distance
visited.append(nearest)
current = nearest

print(f'Go to: House {nearest} (distance: {distance})')
print(f'Visited: {visited}')
print(f'Total distance so far: {total_distance}')
```

### Step 3: Repeat

```python
# From house 1, distances are: [10, 0, 35, 25, 30]
# Nearest unvisited: house 0 (visited), house 2 (35), house 3 (25), house 4 (30)
# Nearest is house 3 (distance 25)

current = 3
total_distance += 25
visited.append(3)

print(f'Go to: House 3 (distance: 25)')
print(f'Total: {total_distance}')
```

Continue until all houses are visited, then return home.

### Full Solution with supplycm

```python
from supplycm.routing import tsp_nearest_neighbor

distances = [
    [0,  10, 15, 20, 25],
    [10, 0,  35, 25, 30],
    [15, 35, 0,  30, 20],
    [20, 25, 30, 0,  15],
    [25, 30, 20, 15, 0],
]

route, total = tsp_nearest_neighbor(distances)
print(f'Route: {route}')
print(f'Total distance: {total}')
```

## Is Nearest Neighbor the Best?

Not always! It can get stuck because it only looks at the next step, not the whole picture.

```python
# Nearest neighbor might give a route like:
# Home -> 1 -> 3 -> 4 -> 2 -> Home
# Total: 10 + 25 + 15 + 20 + 15 = 85

# But a better route might be:
# Home -> 1 -> 2 -> 4 -> 3 -> Home
# Total: 10 + 35 + 20 + 15 + 20 = 100 (worse!)

# Or:
# Home -> 2 -> 1 -> 3 -> 4 -> Home
# Total: 15 + 35 + 25 + 15 + 25 = 115 (even worse!)
```

To find a better route, use 2-opt:

```python
from supplycm.routing import tsp_two_opt

route, total = tsp_two_opt(distances)
print(f'Improved route: {route}')
print(f'Total distance: {total}')
```

## Key Takeaway

Nearest Neighbor:
1. Start at home
2. Go to nearest unvisited
3. Repeat
4. Return home

It is fast and simple, but not always the best. Use 2-opt to improve it.
