# Module 5: Storing Stuff (Warehouses)

## The Big Idea

A warehouse is a big building where you keep stuff before it goes to customers. How you arrange things inside matters a lot.

## Why Does It Matter?

A messy warehouse means:

- Hard to find things
- Slow to pick orders
- More mistakes
- Wasted space

A well-organized warehouse means:

- Fast order picking
- Fewer mistakes
- Happy customers
- Lower costs

## Where to Put Things: ABC Slotting

Not all products are picked equally often. Put the popular ones near the door.

Use ABC analysis (from Module 3) to decide:

- **A items** (top sellers): Put near the shipping door, at waist height
- **B items** (medium sellers): Put in the middle of the warehouse
- **C items** (slow sellers): Put in the back, up high

### Try it with supplycm

```python
from supplycm.warehouse import warehouse_slotting_abc

items = [
    ('Popular Toy', 1000, 1),  # name, demand, size
    ('Medium Toy', 100, 1),
    ('Slow Toy', 10, 1),
]

slotting = warehouse_slotting_abc(items, num_zones=3)
for item, zone in slotting:
    print(f"{item}: Zone {zone} (0 = closest to door)")
```

## Picking Orders Efficiently

When a customer orders 5 different products, you need to walk around the warehouse to collect them. The route you take matters.

A bad route wastes time. A good route saves time.

### Try it with supplycm

```python
from supplycm.warehouse import traveling_salesman_picking

# Locations of items to pick (x, y coordinates)
pick_locations = [(1, 1), (3, 5), (2, 8), (7, 2), (5, 6)]
depot = (0, 0)  # where you start and end

route = traveling_salesman_picking(pick_locations, depot)
print(f"Pick in this order: {route}")
```

## Cross-Docking: Skip the Storage

Sometimes you do not need to store things at all. Cross-docking means:

1. Truck arrives with stuff
2. You sort it immediately
3. Another truck takes it away

No storage needed. This saves time and space.

### When to use cross-docking:

- Perishable goods (food)
- High-demand items
- Promotional items

## Pallet Building: Stacking Boxes

When you ship many boxes, you stack them on a pallet. The way you stack matters:

- Heavy boxes on the bottom
- Light boxes on top
- Fill the pallet completely

### Try it with supplycm

```python
from supplycm.warehouse import pallet_building

# Items as (length, width, height)
items = [(2, 2, 2), (1, 1, 1), (3, 3, 3), (1, 1, 1), (2, 2, 2)]
pallet_capacity = 8  # cubic units

pallets = pallet_building(items, pallet_capacity)
for i, pallet in enumerate(pallets):
    print(f"Pallet {i+1}: {len(pallet)} items")
```

## Warehouse Layout

A good warehouse layout has:

1. **Receiving area**: Where trucks unload
2. **Storage area**: Where things are kept
3. **Picking area**: Where orders are collected
4. **Packing area**: Where orders are boxed
5. **Shipping area**: Where trucks load

### Try it with supplycm

```python
from supplycm.warehouse import warehouse_layout_optimization

items = [
    ('Top Seller', 500),
    ('Medium Seller', 200),
    ('Slow Seller', 50),
]

slots = [
    ('Slot A', 1),   # closest to door
    ('Slot B', 5),
    ('Slot C', 10),  # farthest from door
]

assignment = warehouse_layout_optimization(items, slots)
print(assignment)
# Top Seller goes to Slot A (closest)
```

## Putaway: Where to Put New Stuff

When new inventory arrives, you need to decide where to put it. Good putaway means:

- Fast items go to easy-to-reach spots
- Heavy items go to lower shelves
- Similar items are stored together

## Quick Quiz

1. Where should you put your most popular items in a warehouse?
2. What is cross-docking?
3. Why does the order-picking route matter?
4. Name the 5 areas of a warehouse layout.

<details>
<summary>Click to reveal answers</summary>

1. Near the shipping door, at waist height
2. Moving goods directly from receiving to shipping without storage
3. A good route saves time and walking
4. Receiving, storage, picking, packing, shipping

</details>

## Exercise

Design a warehouse for a small online toy store.

1. List 10 toys and their monthly sales
2. Use ABC analysis to classify them
3. Decide where each toy goes in the warehouse
4. Draw a simple map of your warehouse layout

## Key Words

- **Warehouse**: A building for storing products
- **ABC slotting**: Putting popular items in easy-to-reach spots
- **Cross-docking**: Moving goods directly from receiving to shipping
- **Picking**: Collecting items for an order
- **Putaway**: Deciding where to store new inventory

## What's Next?

Stuff is in the warehouse. Now how do you get it to customers? The next lesson is about transportation.

Next: [Module 6 - Moving Stuff Around (Transportation)](06_transportation.md)
