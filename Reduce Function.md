### Problem Statement

You are given a list of rational numbers, represented as fractions. The task is to calculate the product of all the fractions in the list and return the result in its simplest form, i.e., the numerator and denominator should have no common divisor other than 1.

### Code

Here's the completed code again for clarity:

```python
from fractions import Fraction
from functools import reduce

def product(fracs):
    t = reduce(lambda x, y: x * y, fracs)  # Using reduce to multiply the fractions
    return t.numerator, t.denominator

if __name__ == '__main__':
    fracs = []
    for _ in range(int(input())):
        fracs.append(Fraction(*map(int, input().split())))
    result = product(fracs)
    print(*result)
```

---

### Detailed Explanation

#### 1. **Modules Used**
   - **`fractions` Module**: The `Fraction` class is used to handle rational numbers. It automatically simplifies fractions as they are created or manipulated.
   - **`functools` Module**: The `reduce` function applies a cumulative operation (in this case, multiplication) on elements of a list from left to right.

#### 2. **`product()` Function**
   - **Purpose**: This function calculates the product of all the fractions provided in the list `fracs` and returns the numerator and denominator of the final product in its simplest form.
   - **Key Line**: `reduce(lambda x, y: x * y, fracs)`
     - `reduce` applies the lambda function `x * y` to successive pairs of fractions in the list `fracs`.
     - Fractions are multiplied cumulatively: first two fractions are multiplied, then the result is multiplied with the next fraction, and so on.
   - The result of this operation (`t`) is a `Fraction` object.
   - `.numerator` and `.denominator`: These attributes of the `Fraction` object return the numerator and denominator of the fraction, respectively.

#### 3. **Input Handling**
   - `fracs = []`: Initializes an empty list to store the fractions.
   - `for _ in range(int(input()))`: Loops to collect `n` fractions from the user, where `n` is the number of rational numbers.
   - `Fraction(*map(int, input().split()))`: For each input, splits the numerator and denominator, converts them to integers, and creates a `Fraction` object using those values.

#### 4. **Output**
   - `result = product(fracs)`: Calls the `product()` function, passing the list of fractions, and stores the result as a tuple `(numerator, denominator)`.
   - `print(*result)`: Prints the numerator and denominator separated by a space.

---

### How the Code Works Step by Step

1. **Input Reading**:
   - The user specifies the number of fractions, `n`.
   - For each fraction, they provide two integers: numerator and denominator.

2. **Creating `Fraction` Objects**:
   - The `Fraction` class simplifies the fractions as they are created. For instance, `Fraction(4, 8)` becomes `Fraction(1, 2)`.

3. **Multiplying Fractions**:
   - The `reduce` function applies the multiplication operation cumulatively across all fractions in the list.
   - For example, given fractions `1/2`, `2/3`, and `3/4`, the computation proceeds as:
     - Multiply `1/2` and `2/3` → Result: `2/6` = `1/3` (simplified)
     - Multiply `1/3` and `3/4` → Result: `3/12` = `1/4` (simplified)
   - The final fraction is `1/4`.

4. **Output in Simplest Form**:
   - The numerator and denominator of the final fraction are extracted using `.numerator` and `.denominator`.
   - These values are printed as the result.

---

### Example Execution

**Input**:
```
3
1 2
2 3
3 4
```

**Output**:
```
1 4
```

**Explanation**:
- Fractions: `1/2`, `2/3`, `3/4`
- Product:
  - Multiply `1/2` and `2/3` → `1/3` (simplified)
  - Multiply `1/3` and `3/4` → `1/4` (simplified)
- Final result: `1 4`.

---

Let me know if you'd like help testing or extending this code! 😊
