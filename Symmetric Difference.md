# Problem Statement:
You are given two sets of integers, `M` and `N`. Your task is to:
1. Compute the **symmetric difference** of the two sets. The symmetric difference consists of elements that are in either `M` or `N` but not in both.
2. Print these elements in **ascending order**, one element per line.

**Input Format:**
1. The first line contains an integer, `M`, which represents the size of the first set.
2. The second line contains `M` space-separated integers, which are the elements of the first set.
3. The third line contains an integer, `N`, which represents the size of the second set.
4. The fourth line contains `N` space-separated integers, which are the elements of the second set.

**Output Format:**
- Print the elements of the symmetric difference in **ascending order**, one per line.

---

## Code Explanation:
Here is the Python code again, followed by a detailed explanation:

```python
# Read the size of the first set
M = int(input())

# Read the elements of the first set
set_M = set(map(int, input().split()))

# Read the size of the second set
N = int(input())

# Read the elements of the second set
set_N = set(map(int, input().split()))

# Compute the symmetric difference (elements in either set, but not both)
symmetric_difference = set_M.symmetric_difference(set_N)

# Print the symmetric difference elements in ascending order, one per line
for element in sorted(symmetric_difference):
    print(element)
```

#### 1. **Reading Input for Set `M`:**
   ```python
   M = int(input())
   set_M = set(map(int, input().split()))
   ```
   - The first line accepts an integer, `M`, which is the size of the first set. (Note: This value is not used directly in the code since Python sets handle their own size.)
   - The second line contains `M` space-separated integers. These are converted into a set using the following steps:
     - `input().split()` splits the input string into a list of strings (e.g., `"1 2 3"` becomes `['1', '2', '3']`).
     - `map(int, ...)` converts each string in the list to an integer (e.g., `['1', '2', '3']` becomes `[1, 2, 3]`).
     - `set(...)` converts this list into a set (e.g., `[1, 2, 3]` becomes `{1, 2, 3}`).

#### 2. **Reading Input for Set `N`:**
   ```python
   N = int(input())
   set_N = set(map(int, input().split()))
   ```
   - Similarly, the integer `N` is read as the size of the second set (not used directly), and the next line contains `N` space-separated integers that are converted into a set `set_N`.

#### 3. **Finding the Symmetric Difference:**
   ```python
   symmetric_difference = set_M.symmetric_difference(set_N)
   ```
   - The `symmetric_difference()` method computes elements that are in either `set_M` or `set_N`, but **not in both**.
   - Example:
     - `set_M = {2, 4, 5, 9}`
     - `set_N = {2, 4, 11, 12}`
     - Symmetric Difference: `{5, 9, 11, 12}` (since these values are in one of the sets but not both).

#### 4. **Sorting and Printing the Symmetric Difference:**
   ```python
   for element in sorted(symmetric_difference):
       print(element)
   ```
   - The `sorted()` function orders the elements of the symmetric difference in **ascending order**.
   - A `for` loop iterates through this sorted list, printing each element on a new line.

---

## Example Execution:

#### Input:
```
4
2 4 5 9
4
2 4 11 12
```

#### Explanation:
- Step 1: Read input and create sets:
  - `set_M = {2, 4, 5, 9}`
  - `set_N = {2, 4, 11, 12}`
- Step 2: Compute symmetric difference:
  - Elements in either `set_M` or `set_N` but not both: `{5, 9, 11, 12}`.
- Step 3: Sort and print:
  - Sorted symmetric difference: `[5, 9, 11, 12]`.

#### Output:
```
5
9
11
12
```

---

## Key Notes:
- Sets automatically handle duplicates, so each element in a set is unique.
- The `symmetric_difference()` method ensures that only non-overlapping elements are considered.
- The `sorted()` function is used to guarantee that the output is in ascending order, as required by the problem statement.

