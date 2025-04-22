# Problem Explanation:
The task is to process two groups of words and find the occurrence positions of each word from **Group B** in **Group A**. If a word from Group B is present in Group A, we print the indices (positions) where it appears. If it is not found, we print `-1`.



#### Problem Input and Output:
1. **Input**:
   - First line: Two integers `n` (number of words in Group A) and `m` (number of words in Group B).
   - Next `n` lines: Words of Group A.
   - Next `m` lines: Words of Group B.

2. **Output**:
   - For each word in Group B:
     - Print the positions (indices) where it appears in Group A, separated by spaces.
     - If the word does not appear, print `-1`.

## Example:
**Input**:
```
5 2
a
b
a
c
a
a
d
```
**Output**:
```
1 3 5
-1
```



**Explanation**:
- `a` in Group B appears in positions 1, 3, 5 of Group A.
- `d` in Group B does not appear in Group A, so `-1` is printed.

---

# Python Code:
Here's the code to solve this problem using the `defaultdict` container.

```python
from collections import defaultdict

# Input n (number of words in Group A) and m (number of words in Group B)
n, m = map(int, input().split())

# Initialize defaultdict for Group A and list for Group B
group_a = defaultdict(list)
group_b = []

# Populate Group A
for i in range(1, n + 1):
    word = input()
    group_a[word].append(i)  # Store index of the word (1-based index)

# Populate Group B
for _ in range(m):
    word = input()
    group_b.append(word)

# Check occurrences of words in Group B
for word in group_b:
    if word in group_a:  # If the word exists in Group A
        print(" ".join(map(str, group_a[word])))  # Print indices separated by spaces
    else:
        print(-1)  # Print -1 if the word is not found
```

---

## Code Explanation:

1. **Using `defaultdict`**:
   - A `defaultdict` from the `collections` module is initialized as `group_a`. It automatically creates a list for each key when it's first accessed, avoiding the need to check if the key exists.

2. **Input Handling**:
   - `n, m = map(int, input().split())`: Reads the number of words in Group A and Group B.
   - **Group A**: A loop runs from 1 to `n`, and for every word input, its index (1-based) is appended to the list in `group_a`.
   - **Group B**: Words of Group B are stored in a simple list.

3. **Finding Occurrences**:
   - For each word in Group B, the program checks:
     - If the word exists in `group_a`, the stored list of indices is retrieved and printed as a space-separated string.
     - If the word is not found, `-1` is printed.

4. **Output**:
   - The `join()` function is used to format the indices of Group A words as a single line of space-separated integers.

---

