
---

# **Problem Statement**

You are given a string, and you need to modify it by replacing the character at a specific index with a new character. Since strings in Python are immutable (cannot be changed directly), you will need to implement a solution that works around this limitation.

Your task is to write a function, `mutate_string`, that modifies the string based on the following input:
1. A string, `string` – the original text.
2. An integer, `position` – the index where the replacement occurs.
3. A character, `character` – the new character to be inserted.

The function should return the modified string after making the desired change.

---

### **Input Format**
1. The first line contains the string, `string`.
2. The second line contains two space-separated values:
   - An integer, `position` – the index location of the character to replace.
   - A single character, `character` – the new character to insert.

---

### **Output Format**
Return the modified string after performing the substitution.

---

### **Constraints**
- The `position` will always be a valid index within the bounds of the string.
- The `character` will always be a single character.

---

## **Example Input and Output**

#### Example 1:
**Input:**
```
abracadabra
5 k
```

**Output:**
```
abrackdabra
```

#### Explanation:
1. The initial string is `"abracadabra"`.
2. At index `5`, the character is `'a'`.
3. Replace `'a'` with `'k'`.
4. The modified string becomes `"abrackdabra"`.

---

### **Detailed Code Explanation**

Here’s the complete code, followed by a detailed explanation of how it works:

```python
def mutate_string(string, position, character):
    # Use string slicing to replace the character at the given position
    return string[:position] + character + string[position + 1:]

if __name__ == '__main__':
    # Take input for the original string
    s = input()
    # Take input for position and replacement character, split into variables
    i, c = input().split()
    # Call the function with the given inputs
    s_new = mutate_string(s, int(i), c)
    # Print the modified string
    print(s_new)
```

#### Explanation of the Code:
1. **The Function `mutate_string`**:
   - In Python, strings are immutable, so we cannot directly change a character at a specific index.
   - To modify a string, we can use string slicing:
     - `string[:position]`: Slices the string from the beginning up to (but not including) the specified `position`.
     - `character`: Adds the replacement character at the specified index.
     - `string[position + 1:]`: Slices the string from the index after the specified `position` to the end.
   - These parts are concatenated (`+`) to form the modified string.

2. **Input Handling**:
   - The `input()` function is used to read the string and the second line of inputs (position and character).
   - The `split()` method splits the second input (e.g., `"5 k"`) into two separate variables:
     - `i`: The position of the character to be replaced (as a string).
     - `c`: The replacement character.
   - Since positions must be integers, `i` is converted to an integer using `int(i)`.

3. **Processing and Output**:
   - The function `mutate_string` is called with the string, position, and replacement character.
   - The returned modified string is stored in the variable `s_new`.
   - Finally, the modified string is printed to the console.

#### Example Step-by-Step Execution:
**Input:**
```
abracadabra
5 k
```

1. The string `s` is initialized to `"abracadabra"`.
2. The position `i` is `5` (converted from a string to an integer).
3. The character `c` is `'k'`.
4. Inside the function:
   - Slicing occurs as follows:
     - `string[:5]`: `"abrac"`
     - `character`: `"k"`
     - `string[6:]`: `"dabra"`
   - Concatenation: `"abrac" + "k" + "dabra" = "abrackdabra"`.
5. The modified string `"abrackdabra"` is returned and printed.

---

### **Why Use Slicing?**
- Strings in Python are immutable, so you cannot directly modify them like lists.
- Slicing creates substrings without modifying the original string, allowing you to insert or replace characters efficiently.

---

### **Alternate Approach**
You could also convert the string into a list, replace the desired character, and then convert it back to a string:
```python
def mutate_string(string, position, character):
    l = list(string)  # Convert string to list
    l[position] = character  # Replace the character at the position
    return ''.join(l)  # Join the list back into a string
```

While this approach works, it is less efficient than slicing for small modifications, as it involves creating a list and performing additional operations.

---

I hope this detailed breakdown helps! Do let me know if you’d like me to clarify or expand further. 😊
