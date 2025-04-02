### Problem Statement
A multinational brand plans to base its company logo on the top three most common characters in its name. Your task is to determine these characters along with their occurrence counts, adhering to the following rules:
- Sort the characters in **descending order** of occurrence count.
- If two or more characters have the same count, sort them **alphabetically**.

### Constraints:
1. The length of the input string \( S \) is between 4 and 10,000 characters.
2. The string contains at least three distinct characters.
3. The string consists of **lowercase letters** only.

### Input Format:
A single line containing the company name \( S \).

### Output Format:
The top three most common characters in \( S \), along with their occurrence counts. Each character-count pair is printed on a separate line.

---

### Detailed Code with Explanation

Here's the complete code for solving the problem, with step-by-step explanations:

```python
#!/bin/python3

from collections import Counter  # Import Counter to count occurrences of characters efficiently

# Entry point of the program
if __name__ == '__main__':
    # Step 1: Read input string (company name)
    s = input().strip()
    
    # Step 2: Count occurrences of each character in the string
    # 'Counter' creates a dictionary where keys are characters and values are their counts
    char_count = Counter(s)
    
    # Step 3: Sort the characters by their occurrence count (descending) and alphabetically for ties
    # 'sorted()' function returns a sorted list based on the provided key
    # Sorting rules:
    #   - First, sort by negative of occurrence count (-x[1]) to get descending order
    #   - Second, sort alphabetically (x[0]) in case of ties
    sorted_chars = sorted(char_count.items(), key=lambda x: (-x[1], x[0]))
    
    # Step 4: Print the top three characters along with their counts
    for char, count in sorted_chars[:3]:  # Slice to get the first three elements
        print(f"{char} {count}")
```

---

### Step-by-Step Explanation of Code

1. **Importing `Counter`**:
   - `Counter` is a powerful utility from Python's `collections` module.
   - It counts occurrences of elements in an iterable (in this case, characters in a string) and stores the results in a dictionary-like object.

2. **Reading Input**:
   - The input string \( s \) is read using `input()` and stripped of any surrounding whitespace using `.strip()`.

3. **Counting Characters**:
   - `char_count = Counter(s)` creates a dictionary where:
     - Keys: Unique characters in \( s \).
     - Values: Their occurrence counts.

4. **Sorting**:
   - The `sorted()` function is used to arrange items from `char_count.items()` based on a custom sorting key:
     - `key=lambda x: (-x[1], x[0])`: This ensures the following:
       - Characters are sorted by **descending occurrence count** (`-x[1]`).
       - Characters with the same occurrence count are sorted **alphabetically** (`x[0]`).
   - The result is stored in the list `sorted_chars`.

5. **Output Top Three**:
   - The first three elements of the sorted list (`sorted_chars[:3]`) are selected.
   - A `for` loop prints each character along with its count in the format `character count`.

---

### Example Input and Output

#### Input:
```
google
```

#### Explanation of Steps:
1. Character counts using `Counter`:
   ```
   {'g': 2, 'o': 2, 'l': 1, 'e': 1}
   ```
2. Sorting:
   ```
   [('g', 2), ('o', 2), ('e', 1), ('l', 1)]
   ```
   - `g` and `o` have the highest counts (2) and are sorted alphabetically.
   - `e` and `l` each have counts of 1 and are also sorted alphabetically.

#### Output:
```
g 2
o 2
e 1
```

---

This explanation should clarify all parts of the problem and the code. Let me know if you'd like any further breakdown or additional test examples! 🚀
