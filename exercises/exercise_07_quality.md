# Exercise 7: Quality

## Problem

Your factory makes 2000 toys per day. Each toy has 8 quality checkpoints. Yesterday you found 30 defects.

### Tasks

1. Calculate DPMO
2. What is the sigma level?
3. Is your process at Six Sigma level?
4. What would DPMO be at Six Sigma?

## Your Answer

```
DPMO: ___
Sigma level: ___
At Six Sigma? ___
Six Sigma DPMO: ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.quality import dpmo, sigma_level

dpmo_value = dpmo(30, 2000, 8)
sigma = sigma_level(dpmo_value)

print(f"DPMO: {dpmo_value}")
print(f"Sigma level: {sigma}")
print(f"At Six Sigma? {'Yes' if sigma >= 6 else 'No'}")
print(f"Six Sigma DPMO target: 3.4")
```

### Expected Results

1. DPMO = (30 / (2000 * 8)) * 1,000,000 = 1875
2. Sigma level: about 4.4 (between 4 and 5)
3. Not at Six Sigma (need 3.4 DPMO)
4. Six Sigma target: 3.4 DPMO

</details>
