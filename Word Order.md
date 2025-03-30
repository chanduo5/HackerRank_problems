
---

# Problem Statement

You are given **n words**, where some words may repeat. The task is to:

1. Count the number of **distinct words** present in the input.
2. Count how many times each **distinct word** occurs, in the same order as they appear for the first time in the input.

---

### **Constraints**:
- \(1 < n < 10^5\)
- The sum of the lengths of all the words does not exceed \(10^6\).
- Words consist of only **lowercase English letters**.

---

#### **Input Format**:
1. The first line contains an integer \(n\), the number of words.
2. The next \(n\) lines each contain a word.

#### **Output Format**:
1. On the first line, print the number of **distinct words**.
2. On the second line, print the **number of occurrences** for each distinct word, in the order of their first appearance in the input.

---

### Example Input and Output

#### **Input:**

```
6
apple
banana
apple
orange
banana
apple
```

#### **Output:**

```
3
3 2 1
```

#### **Explanation:**
- Distinct words: `apple`, `banana`, `orange`.
- Number of occurrences:
  - `apple` appears 3 times.
  - `banana` appears 2 times.
  - `orange` appears 1 time.

---

# Detailed Explanation of the Code

Here’s the code again, followed by its breakdown:

```python
from collections import Counter

def count_word_occurrences():
    # Input number of words
    n = int(input().strip())
    
    # Input the words
    words = []
    for _ in range(n):
        words.append(input().strip())
    
    # Count occurrences preserving order of appearance
    word_count = Counter(words)
    
    # Output the number of distinct words
    print(len(word_count))
    
    # Output the occurrences in the order of appearance
    occurrences = [word_count[word] for word in word_count.keys()]
    print(*occurrences)

# Call the function
count_word_occurrences()
```

---

### Step-by-Step Breakdown of the Code

1. **Importing the `Counter` class**:
   - The `collections.Counter` is a convenient class in Python that helps count the occurrences of elements in a list.
   - Example: `Counter(['a', 'b', 'a'])` produces `{'a': 2, 'b': 1}`.

---

2. **Taking input**:
   - `n = int(input().strip())` reads the integer \(n\) from the first line, which is the number of words.
   - `words.append(input().strip())` reads each word (one per line) and appends it to a list called `words`.

   At this point, if the input was:
   ```
   6
   apple
   banana
   apple
   orange
   banana
   apple
   ```
   The `words` list would look like:
   ```python
   ['apple', 'banana', 'apple', 'orange', 'banana', 'apple']
   ```

---

3. **Using `Counter` to count words**:
   - `word_count = Counter(words)` counts the number of occurrences of each word.
   - The `Counter` automatically preserves the order of first appearances of words (from Python 3.7 onwards).

   After running `Counter(words)` for the above input:
   ```python
   word_count = {'apple': 3, 'banana': 2, 'orange': 1}
   ```

---

4. **Outputting the number of distinct words**:
   - `len(word_count)` gives the count of distinct words.
   - Example:
     - For the input: `['apple', 'banana', 'apple', 'orange', 'banana', 'apple']`
     - The distinct words are `['apple', 'banana', 'orange']`.
     - Output: `3`.

---

5. **Outputting occurrences in the input order**:
   - `occurrences = [word_count[word] for word in word_count.keys()]`:
     - The `.keys()` method of the `Counter` gives the words in the order they first appear.
     - The `occurrences` list contains the count of each word in this order.
   - Example:
     - For `word_count = {'apple': 3, 'banana': 2, 'orange': 1}`
     - `occurrences = [3, 2, 1]`.

   - The `print(*occurrences)` prints the counts in one line, separated by spaces:
     - Output: `3 2 1`.

---

6. **Final Outputs**:
   - The code first prints the count of distinct words:
     ```
     3
     ```
   - Then it prints the occurrences of each word in the order they appear:
     ```
     3 2 1
     ```

---

