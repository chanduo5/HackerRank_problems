### **Problem Statement:**
You are given an integer \( N \). Your task is to print an alphabet rangoli of size \( N \). A rangoli is a form of Indian folk art based on symmetrical and decorative patterns.

#### **Constraints:**
- The rangoli should be made using lowercase English letters.
- The center of the rangoli contains the letter 'a', while the outermost layer contains the \( N \)-th letter of the alphabet.
- The rangoli should be symmetrical vertically and horizontally.

#### **Example Output:**
For \( N = 5 \):

```
--------e--------
------e-d-e------
----e-d-c-d-e----
--e-d-c-b-c-d-e--
e-d-c-b-a-b-c-d-e
--e-d-c-b-c-d-e--
----e-d-c-d-e----
------e-d-e------
--------e--------
```

---

### **Code Explanation:**
```python
import string
```
- The `string` module is imported to easily access lowercase English letters.

```python
def print_rangoli(size):
    # Get the lowercase alphabet
    alphabet = string.ascii_lowercase
```
- We use `string.ascii_lowercase` to get all lowercase letters (`'abcdefghijklmnopqrstuvwxyz'`).
- This helps in fetching the required letters dynamically based on `size`.

```python
    # Create the pattern rows
    lines = []
    for i in range(size):
        letters = alphabet[size-1:i:-1] + alphabet[i:size]  # Form the required sequence of letters
        line = '-'.join(letters)  # Join letters with '-'
        lines.append(line.center(4*size-3, '-'))  # Center align with '-' padding
```
- We iterate `i` from `0` to `size-1` to generate rows of the pattern.
- The letters for each row are selected symmetrically using slicing.
- `'-'.join(letters)` ensures the required format.
- `line.center(4*size-3, '-')` centers the string with `-` padding.

```python
    # Print the full pattern
    print('\n'.join(lines[::-1] + lines[1:]))  # Correct order to match expected output
```
- We first print the rows in reverse order (`lines[::-1]`), forming the top half.
- The second half (`lines[1:]`) is appended to mirror the first half (excluding the first line to avoid repetition).

```python
if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```
- This takes user input `n` and calls `print_rangoli(n)` to print the alphabet rangoli.
