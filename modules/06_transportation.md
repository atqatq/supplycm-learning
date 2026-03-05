# Module 6: Moving Stuff Around (Transportation)

## The Big Idea

Transportation is how you move products from one place to another. The goal is to do it fast, cheap, and reliably.

## Why Does It Matter?

Transportation is often the biggest cost in a supply chain. Bad routing means:

- More fuel used
- More time wasted
- Late deliveries
- Unhappy customers

Good routing means lower costs and faster deliveries.

## The Traveling Salesman Problem (TSP)

The TSP asks: "What is the shortest route to visit all locations and return to start?"

Imagine a delivery driver who needs to visit 5 houses. What order should they visit them in?

There are many possible orders. For 5 houses, there are 120 different routes. For 10 houses, there are over 3 million routes. You cannot check them all.

### Try it with supplycm

```python
from supplycm.routing import tsp_nearest_neighbor

# Distance matrix between 4 locations
distances = [
    [0,  10, 15, 20],  # from location 0
    [10, 0,  35, 25],  # from location 1
    [15, 35, 0,  30],  # from location 2
    [20, 25, 30, 0],   # from location 3
]

route, total_distance = tsp_nearest_neighbor(distances)
print(f"Route: {route}")
print(f"Total distance: {total_distance}")
```

The nearest neighbor method always goes to the closest unvisited location. It is fast but not always the best.

## Improving Routes: 2-opt

The 2-opt method takes an existing route and tries to make it better by swapping parts of the route.

### Try it with supplycm

```python
from supplycm.routing import tsp_two_opt

route, distance = tsp_two_opt(distances)
print(f"Improved route: {route}")
print(f"Total distance: {distance}")
```

## Vehicle Routing Problem (VRP)

What if you have multiple delivery trucks? Each truck can only carry so much. This is the VRP.

### Try it with supplycm

```python
from supplycm.routing import vrp_capacitated_greedy

# 5 customers need delivery (index 0 is the warehouse)
demands = [0, 5, 10, 8, 12]  # how much each customer needs
distances = [
    [0,  5, 10, 8,  12],
    [5,  0, 6,  7,  9],
    [10, 6, 0,  5,  8],
    [8,  7, 5,  0,  4],
    [12, 9, 8,  4,  0],
]

routes = vrp_capacitated_greedy(distances, demands, vehicle_capacity=15)
for i, route in enumerate(routes):
    print(f"Truck {i+1}: {route}")
```

## The Assignment Problem

Sometimes you need to assign workers to jobs. Each worker is better at some jobs than others. You want the best overall assignment.

The Hungarian Algorithm solves this perfectly.

### Try it with supplycm

```python
from supplycm.routing import assignment_problem_hungarian

# Cost matrix: worker x job
# Lower cost = better fit
costs = [
    [10, 15, 20],  # Worker 0
    [5,  12, 8],   # Worker 1
    [14, 7,  11],  # Worker 2
]

assignments, total_cost = assignment_problem_hungarian(costs)
print(f"Assignments: {assignments}")
print(f"Total cost: {total_cost}")
```

## Choosing Transport Mode

Different ways to transport have different pros and cons:

| Mode | Speed | Cost | Best for |
|------|-------|------|----------|
| Air | Very fast | Very expensive | Urgent, valuable items |
| Truck | Fast | Medium | Most deliveries |
| Train | Medium | Cheap | Heavy, bulk items |
| Ship | Slow | Very cheap | International, huge volumes |

## Quick Quiz

1. What does TSP stand for?
2. Why is the nearest neighbor method not always the best?
3. What is the difference between TSP and VRP?
4. Which transport mode is best for urgent valuable items?

<details>
<summary>Click to reveal answers</summary>

1. Traveling Salesman Problem
2. Because it always picks the closest next stop, which might lead to a bad overall route
3. VRP has multiple vehicles with capacity limits; TSP has one vehicle
4. Air transport

</details>

## Exercise

You are a delivery dispatcher. You have:

- 1 truck with capacity of 20 units
- 5 customers at different locations
- Each customer needs a different amount

1. Create a distance matrix
2. Use VRP to plan the route
3. Calculate total distance traveled

## Key Words

- **TSP**: Traveling Salesman Problem - shortest route visiting all locations
- **VRP**: Vehicle Routing Problem - TSP with multiple vehicles and capacity
- **Nearest neighbor**: A simple routing method
- **2-opt**: A method to improve routes
- **Hungarian Algorithm**: Solves the assignment problem

## What's Next?

Now stuff is moving. But is it good stuff? The next lesson is about quality.

Next: [Module 7 - Making Good Stuff (Quality)](07_quality.md)
