### Problem Description:
You are tasked with manipulating a string in Python by performing two specific operations:
1. Splitting the string into a list of words using a **space** (" ") as a delimiter.
2. Joining the resulting list of words back into a single string, with each word separated by a **hyphen** ("-").

This problem requires implementing a function named `split_and_join`, which accepts a single input string, performs the specified operations, and returns the resultant string.

---

### **Problem Statement:**
Write a Python function called `split_and_join`. 

**Function Signature:**
```python
def split_and_join(line):
```

**Parameters:**
- `line` (string): A string of space-separated words.  

**Returns:**
- (string): A string where words from the input are joined by hyphens.

---

### **Input Format:**
The input is a single line, which is a string consisting of space-separated words.

### **Output Format:**
The output is a single string, where the words are joined by hyphens.

---

### **Examples:**

#### **Example 1:**
Input:
```
this is a string
```

Output:
```
this-is-a-string
```

#### Explanation:
1. The input string is split into a list: `['this', 'is', 'a', 'string']`.
2. These words are joined together with hyphens, resulting in the output `this-is-a-string`.

---

### **Code Implementation:**
Here's the complete Python code for the solution:

```python
def split_and_join(line):
    # Split the input string on spaces to create a list of words
    words = line.split(" ")
    # Join the list of words with hyphens and return the resulting string
    return "-".join(words)

if __name__ == '__main__':
    # Take input from the user
    line = input()
    # Call the split_and_join function
    result = split_and_join(line)
    # Print the result
    print(result)
```

---

### **Step-by-Step Explanation of the Code:**
1. **Splitting:** The method `line.split(" ")` splits the input string `line` into a list of words by using the space character as a delimiter.
   - Example: `"this is a string".split(" ")` → `['this', 'is', 'a', 'string']`.

2. **Joining:** The method `"-".join(words)` combines the list of words into a single string, with each word separated by a hyphen.
   - Example: `"-".join(['this', 'is', 'a', 'string'])` → `"this-is-a-string"`.

3. The function returns the resultant string.

4. The `if __name__ == '__main__':` block ensures the code runs only when executed directly, not when imported as a module. Here, it:
   - Accepts input from the user.
   - Processes the input using the `split_and_join` function.
   - Prints the final output.

---

Let me know if you need further clarification! 🚀
