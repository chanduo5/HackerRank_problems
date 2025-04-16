# **Problem Statement:**
You are given two integer arrays of size **N × P** and **M × P** (where **N** and **M** are the number of rows, and **P** is the number of columns). Your task is to **concatenate** these arrays along **axis 0 (row-wise stacking)**.

### **Input Format:**
1. The first line contains three space-separated integers **N, M, and P**.
2. The next **N** lines contain **P** space-separated integers representing the first array.
3. The next **M** lines contain **P** space-separated integers representing the second array.

### **Output Format:**
- Print the concatenated array after joining both arrays along **axis 0**.

---

## **Code Explanation**
Here’s the Python code that solves the problem:

```python
import numpy as np

# Read N, M, P
N, M, P = map(int, input().split())

# Read first N rows into array_1
array_1 = np.array([list(map(int, input().split())) for _ in range(N)])

# Read next M rows into array_2
array_2 = np.array([list(map(int, input().split())) for _ in range(M)])

# Concatenate arrays along axis 0
result = np.concatenate((array_1, array_2), axis=0)

# Print the final array
print(result)
```

---

## **Step-by-Step Explanation**

1. **Import NumPy Library:**  
   ```python
   import numpy as np
   ```
   We import NumPy to use its functions for array manipulations.

2. **Read the First Line (N, M, P):**  
   ```python
   N, M, P = map(int, input().split())
   ```
   - `N` → Number of rows in the **first array**.
   - `M` → Number of rows in the **second array**.
   - `P` → Number of columns in both arrays.

3. **Read the First Array (N × P):**  
   ```python
   array_1 = np.array([list(map(int, input().split())) for _ in range(N)])
   ```
   - We take **N** rows of space-separated integers and convert them into a NumPy array.
   - `map(int, input().split())` converts space-separated strings into integers.
   - `list(...)` converts the mapped values into a list.
   - The outer loop `[ ... for _ in range(N)]` runs **N** times, collecting rows.

4. **Read the Second Array (M × P):**  
   ```python
   array_2 = np.array([list(map(int, input().split())) for _ in range(M)])
   ```
   - This follows the same process as `array_1`, but collects **M** rows.

5. **Concatenate the Two Arrays along Axis 0 (Row-wise Joining):**  
   ```python
   result = np.concatenate((array_1, array_2), axis=0)
   ```
   - `np.concatenate((array_1, array_2), axis=0)` merges **array_1** and **array_2** vertically.
   - **`axis=0`** → Stack rows on top of each other.

6. **Print the Final Concatenated Array:**  
   ```python
   print(result)
   ```
   - Displays the merged array.

---

### **Example Run**
#### **Input:**
```
4 2 3
1 2 3
4 5 6
7 8 9
10 11 12
13 14 15
16 17 18
```
#### **Processing:**
- First array (**4 × 3**):
  ```
  1  2  3
  4  5  6
  7  8  9
  10 11 12
  ```
- Second array (**2 × 3**):
  ```
  13 14 15
  16 17 18
  ```
- Concatenated along **axis 0**:
  ```
  1  2  3
  4  5  6
  7  8  9
  10 11 12
  13 14 15
  16 17 18
  ```

#### **Output:**
```
[[ 1  2  3]
 [ 4  5  6]
 [ 7  8  9]
 [10 11 12]
 [13 14 15]
 [16 17 18]]
```

---

### **Key Concepts Used in the Code**
✅ **NumPy Arrays:** Efficient handling of numerical data.  
✅ **List Comprehensions:** Quick input processing.  
✅ **`np.concatenate` Function:** Joins multiple arrays along specified axes.

Let me know if anything needs more clarification! 🚀
