# Module 7: Making Good Stuff (Quality)

## The Big Idea

Quality means making products that meet customer expectations. Bad quality loses customers. Good quality keeps them.

## Why Does It Matter?

- Bad products get returned (costs money)
- Bad reviews scare away new customers
- Reworking bad products wastes time
- Good quality builds brand loyalty

## Six Sigma: The Goal of Near-Perfection

Six Sigma is a quality goal: only 3.4 defects per million products. That is 99.99966% perfect.

Most companies operate at 3 Sigma (about 66,800 defects per million). Reaching Six Sigma is a big improvement.

## Measuring Quality: DPMO

DPMO stands for Defects Per Million Opportunities.

### The Formula in Python Notation

```python
dpmo = (defects / (units * opportunities_per_unit)) * 1_000_000
```

### Try it with supplycm

```python
from supplycm.quality import dpmo, sigma_level

units = 1000           # toys made
opportunities = 10     # ways each toy can be defective
defects = 50           # defects found

dpmo_value = dpmo(defects, units, opportunities)
sigma = sigma_level(dpmo_value)

print(f"DPMO: {dpmo_value}")
print(f"Sigma level: {sigma}")
```

## Control Charts: Watching Your Process

A control chart is like a heartbeat monitor for your production. It shows if your process is stable or if something is wrong.

### X-bar Chart

Tracks the average of your product measurements over time. If the average goes outside the control limits, something changed.

### Try it with supplycm

```python
from supplycm.quality import x_bar_chart

# Samples from 3 production runs
samples = [
    [10.1, 10.2, 9.9],  # run 1
    [10.0, 10.1, 10.2],  # run 2
    [10.3, 10.1, 10.0],  # run 3
]

means, upper_limit, lower_limit = x_bar_chart(samples)
print(f"Average of each run: {means}")
print(f"Upper control limit: {upper_limit:.2f}")
print(f"Lower control limit: {lower_limit:.2f}")
```

If any average goes above the upper limit or below the lower limit, your process is out of control.

## Process Capability: Can You Meet Specs?

Your customer wants products within a certain range (specification limits). Can your process deliver?

### Cp: Potential Capability

In Python notation:

```python
cp = (upper_spec - lower_spec) / (6 * std_dev)
```

Where:
- `upper_spec` = Upper Specification Limit
- `lower_spec` = Lower Specification Limit
- `std_dev` = your process standard deviation

### Cpk: Actual Capability

Cpk considers whether your process is centered between the limits.

In Python notation:

```python
cp_upper = (upper_spec - mean) / (3 * std_dev)
cp_lower = (mean - lower_spec) / (3 * std_dev)
cpk = min(cp_upper, cp_lower)
```

### Try it with supplycm

```python
from supplycm.quality import process_capability_cp, process_capability_cpk

upper_spec = 12    # customer wants max 12
lower_spec = 8     # customer wants min 8
mean = 10          # your process averages 10
std_dev = 0.5      # your process std dev

cp = process_capability_cp(upper_spec, lower_spec, std_dev)
cpk = process_capability_cpk(upper_spec, lower_spec, mean, std_dev)

print(f"Cp: {cp:.2f} (potential)")
print(f"Cpk: {cpk:.2f} (actual)")
```

**Interpretation:**
- `cp` or `cpk >= 1.33`: Process is capable
- `1.0` to `1.33`: Marginally capable
- Below `1.0`: Not capable

## The DMAIC Process

Six Sigma uses DMAIC to improve processes:

1. **D**efine: What is the problem?
2. **M**easure: How big is the problem?
3. **A**nalyze: What causes the problem?
4. **I**mprove: How can we fix it?
5. **C**ontrol: How do we keep it fixed?

## Quick Quiz

1. What is the Six Sigma goal for defects per million?
2. What does DPMO stand for?
3. What is the difference between Cp and Cpk?
4. What does DMAIC stand for?

<details>
<summary>Click to reveal answers</summary>

1. 3.4 defects per million
2. Defects Per Million Opportunities
3. Cp measures potential; Cpk measures actual (including centering)
4. Define, Measure, Analyze, Improve, Control

</details>

## Exercise

You run a cookie factory.

1. `units = 5000` cookies per day
2. `opportunities = 5` things that could go wrong per cookie
3. `defects = 100` defective cookies per day

Calculate:
- The DPMO
- The sigma level
- Is your process at Six Sigma level?

## Key Words

- **Quality**: Meeting customer expectations
- **Six Sigma**: A goal of 3.4 defects per million
- **DPMO**: Defects Per Million Opportunities
- **Control chart**: A chart to monitor process stability
- **Cp/Cpk**: Measures of process capability
- **DMAIC**: The Six Sigma improvement process

## What's Next?

Quality is about doing things right. Lean is about doing things efficiently. The next lesson covers lean.

Next: [Module 8 - Working Smart (Lean)](08_lean.md)
