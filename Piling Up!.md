
---

# **Problem Statement**
You are given a horizontal row of `n` cubes. Each cube has a unique `sideLength`. You need to construct a new **vertical pile** of cubes by following **these rules**:
1. If cube `i` is placed on top of cube `j`, then **sideLength[i] ≤ sideLength[j]** (the top cube must be smaller than or equal to the cube below it).
2. At any step, you can pick only the **leftmost** or **rightmost** cube from the horizontal row.

Your task is to determine whether it's **possible** to construct such a vertical pile of cubes using the given rules. 

---

## **Input Format**
1. The first line contains an integer, `T` (number of test cases).
2. For each test case:
   - The first line contains an integer, `n` (number of cubes).
   - The second line contains `n` space-separated integers representing the `sideLength` of each cube.

---

### **Output Format**
Print `Yes` if it's possible to stack the cubes in the described manner for the test case. Otherwise, print `No`.

---

### **Constraints**
1. \( 1 < n < 10^5 \) (number of cubes in each test case).
2. \( 1 \leq \text{sideLength[i]} \leq 2^{31} - 1 \) (size of each cube).

---

### **Explanation**
The goal is to determine whether we can build a stack while following the rules. At each step:
- You can only pick the leftmost or rightmost cube.
- You must ensure that the picked cube can be placed on top of the stack.

**Challenges**:
- Selecting cubes in the correct order (either leftmost or rightmost) while adhering to the stacking rule.
- Handling large inputs efficiently.

**Approach**:
1. Start with an infinitely large cube size (no constraints for the first cube).
2. At each step, choose the larger of the two available cubes (leftmost or rightmost), as long as it satisfies the condition to be placed on the stack.
3. If neither cube satisfies the condition, print `No`.
4. If all cubes are placed successfully, print `Yes`.

---

### **Example**
#### **Input**:
```
2
6
4 3 2 1 3 4
3
1 3 2
```

#### **Output**:
```
Yes
No
```

#### **Explanation**:
**Test Case 1**: `[4, 3, 2, 1, 3, 4]`
- Pick cubes: 4 → 4 → 3 → 3 → 2 → 1 (successfully stacked).

**Test Case 2**: `[1, 3, 2]`
- Pick cubes: Start with 3, then pick 2. This violates the rule as 2 > 1. Hence, `No`.

---

### **Python Code Implementation**
Here's the optimized solution:

```python
def can_stack_cubes(test_cases):
    results = []
    for case in test_cases:
        n, side_lengths = case
        left = 0
        right = n - 1
        top_cube = float('inf')  # Start with an infinitely large cube as the top

        while left <= right:
            # Select the larger cube from either end that meets the condition
            if side_lengths[left] > side_lengths[right]:
                next_cube = side_lengths[left]
                left += 1
            else:
                next_cube = side_lengths[right]
                right -= 1

            # Check if the selected cube can be placed on top
            if next_cube <= top_cube:
                top_cube = next_cube
            else:
                results.append("No")
                break
        else:
            results.append("Yes")
    
    return results

# Input handling
T = int(input())
test_cases = []
for _ in range(T):
    n = int(input())
    side_lengths = list(map(int, input().split()))
    test_cases.append((n, side_lengths))

# Run the function and print results
results = can_stack_cubes(test_cases)
for result in results:
    print(result)
```

---

### **Step-by-Step Explanation of Code**
1. **Initialization**:
   - Start with `top_cube = infinity` (since no cube has been placed yet).
   - Use `left` and `right` pointers to manage cubes at both ends.

2. **Selecting Cubes**:
   - Compare cubes at the `left` and `right` pointers. Pick the larger one.
   - Update the pointer (`left` or `right`) accordingly.

3. **Stack Condition**:
   - Before placing the cube, ensure that its size is **≤ top_cube**.
   - If this condition fails, append "No" and break the loop.

4. **Finalizing Results**:
   - If the loop completes successfully without breaking, append "Yes".

---

### **Edge Cases**
1. **All cubes are equal**:
   Input: `1 1 1 1`
   Output: `Yes` (All cubes can stack successfully).

2. **Strictly increasing cubes**:
   Input: `1 2 3 4 5`
   Output: `No` (Cannot stack after placing the first cube).

3. **Strictly decreasing cubes**:
   Input: `5 4 3 2 1`
   Output: `Yes` (Stack in reverse order).

---

Let me know if you'd like me to clarify any step further or test more cases! 😊
