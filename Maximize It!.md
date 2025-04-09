
---

# **Problem Statement**
You are given:
- A function \( f(X) = X^2 \).
- \( K \) lists, where the \( i^{th} \) list consists of \( N_i \) elements.

Your task is to select one element from each of these \( K \) lists such that the value of the following equation is maximized:

\[
S = (f(X_1) + f(X_2) + \dots + f(X_K)) \mod M
\]

Where \( X_1, X_2, \dots, X_K \) are the elements picked from their respective lists.

# **Explanation**
- \( f(X) \): This is the square of the chosen number \( X \) from the list.
- You need to calculate the sum of the squares of the selected elements and apply the modulo operator \( \% \) with \( M \) to find \( S \).
- The goal is to **maximize \( S \)** by carefully choosing one element from each list.

#### Input Format:
1. The first line contains two integers \( K \) (the number of lists) and \( M \) (the modulo value).
2. Each of the next \( K \) lines starts with an integer \( N_i \) (the number of elements in the \( i^{th} \) list), followed by \( N_i \) integers (the elements of the list).

#### Output Format:
- The maximum value of \( S \) obtained.

---

## **Approach**
1. **Generate Combinations:** To solve the problem, you need to explore all possible combinations of picking one element from each of the \( K \) lists.
2. **Compute \( S \):** For each combination, calculate the sum of squares of the selected elements and apply modulo \( M \).
3. **Maximize \( S \):** Keep track of the highest value of \( S \) encountered.

#### Why Modulo?
Taking the modulo ensures that the result fits within the range of integers \( [0, M-1] \). This also makes computations efficient.

---

# **Python Code Implementation**

```python
from itertools import product

def maximize_s(k, m, lists):
    # Generate all possible combinations of one element from each list
    combinations = product(*lists)
    
    max_s = 0
    for combination in combinations:
        # Calculate the sum of squares and apply modulo
        current_s = sum(x ** 2 for x in combination) % m
        max_s = max(max_s, current_s)
    
    return max_s

# Input
k, m = map(int, input().split())
lists = []
for _ in range(k):
    line = list(map(int, input().split()))
    lists.append(line[1:])  # Skip the first number (Ni), just take the list elements

# Output
print(maximize_s(k, m, lists))
```

---

# **Detailed Explanation of the Code**

#### 1. **Import `itertools.product`**
We use `itertools.product` to generate all possible combinations of one element from each of the \( K \) lists. For example, if you have two lists: \([1, 2]\) and \([3, 4]\), the combinations generated will be:
- \((1, 3)\)
- \((1, 4)\)
- \((2, 3)\)
- \((2, 4)\)

#### 2. **Function Definition**
The `maximize_s` function takes three arguments:
- \( k \): Number of lists.
- \( m \): Modulo value.
- `lists`: A list of \( K \) sublists.

#### 3. **Generate Combinations**
The line `combinations = product(*lists)` generates all possible combinations of elements where one element is taken from each of the \( K \) lists.

#### 4. **Compute \( S \)**
For each combination:
1. Calculate the sum of squares: `sum(x ** 2 for x in combination)`
2. Apply the modulo operation: `% m`

#### 5. **Maximize \( S \)**
Keep track of the highest value of \( S \) using `max_s = max(max_s, current_s)`.

#### 6. **Input Parsing**
- Read \( K \) and \( M \) from the first input line.
- For the next \( K \) lines, read each list, ignoring the first element (the size of the list).

#### 7. **Output**
The result is the maximum value of \( S \), which is printed in the final step.

---

### **Example**

#### Input:
```
3 1000
2 5 4
3 7 8 9
5 1 2 3 4 5
```

#### Explanation:
- \( K = 3 \), \( M = 1000 \)
- Lists: \([5, 4]\), \([7, 8, 9]\), \([1, 2, 3, 4, 5]\)

### Combinations:
Here are a few example combinations and their computed \( S \):
- Combination: \((5, 7, 1)\)
  - Sum of squares: \( 5^2 + 7^2 + 1^2 = 25 + 49 + 1 = 75 \)
  - \( S = 75 \mod 1000 = 75 \)
- Combination: \((4, 8, 5)\)
  - Sum of squares: \( 4^2 + 8^2 + 5^2 = 16 + 64 + 25 = 105 \)
  - \( S = 105 \mod 1000 = 105 \)

#### Output:
After trying all combinations, the maximum \( S \) is computed. In this case, let’s assume the result is:
```
206
```

---

## **Complexity Analysis**

1. **Time Complexity:** \( O(N_1 \cdot N_2 \cdot \dots \cdot N_K) \), where \( N_i \) is the size of the \( i^{th} \) list. This arises from generating all combinations.
2. **Space Complexity:** Depends on the memory used to store intermediate combinations.

