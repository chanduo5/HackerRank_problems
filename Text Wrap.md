### Problem Statement:
You are given a string `S` and an integer `w` that represents the maximum width of each line. The task is to format or "wrap" the string `S` into multiple lines such that no line exceeds the given width `w`. The wrapped text should use newline characters (`\n`) to separate the lines, maintaining the word boundaries.

This functionality is commonly used in text editors and terminal outputs, where long strings need to be displayed within a fixed-width view.

---

### Explanation of the Problem:
Imagine a scenario where you have a single long sentence or paragraph, but you want to make it readable by splitting it into multiple lines of equal width without breaking words in between. For example:

- Input:
  - `S`: "This is a sample string for testing the text wrapping functionality."
  - `w`: 8 (width)

- Output:
  ```
  This is
  a sample
  string
  for
  testing
  the text
  wrapping
  functionality.
  ```

Here, the text is divided into lines such that no line exceeds the width of 8 characters, and words remain intact.

---

### Detailed Code and Explanation:

The given problem is solved using Python's `textwrap` module, which is designed for text formatting.

```python
import textwrap

def wrap(string, max_width):
    # Use textwrap.wrap to split the string into lines of max_width
    return "\n".join(textwrap.wrap(string, max_width))

if __name__ == '__main__':
    # Take input for the string and maximum width
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```

#### Step-by-Step Explanation of the Code:

1. **Import the `textwrap` Module:**
   - The `textwrap` module provides tools to wrap and format text. It's perfect for this task as it handles splitting lines and maintaining word boundaries.

2. **Define the `wrap` Function:**
   - The `wrap` function takes two inputs:
     - `string`: The input string to be wrapped.
     - `max_width`: The maximum width for each line.
   - Inside the function:
     - `textwrap.wrap(string, max_width)` splits the input string into a list of strings (lines), ensuring that each line is at most `max_width` characters wide.
     - `"\n".join(...)` combines the list of lines into a single string with newline characters separating each line.

3. **Input Handling in the Main Block:**
   - The code takes two inputs from the user:
     - A string (to be wrapped).
     - An integer (maximum width of the lines).
   - These inputs are passed to the `wrap` function, and the result is printed.

4. **Output:**
   - The function outputs the wrapped string as a single string with newline-separated lines.

---

### Example Inputs and Outputs:

#### Input 1:
```
string: This is a test string for wrapping.
max_width: 7
```

#### Output 1:
```
This is
a test
string
for
wrapping.
```

#### Input 2:
```
string: HelloWorld!WelcomeToPython.
max_width: 10
```

#### Output 2:
```
HelloWorld!
WelcomeTo
Python.
```

