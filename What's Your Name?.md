# Problem Statement:
You are given two inputs: a person's first name and last name, each on a separate line. Your task is to write a Python function, `print_full_name`, which takes these two strings as input parameters and outputs a formatted message that greets the person and indicates they are delving into Python. 

The output format must be:
```
Hello firstname lastname! You just delved into python.
```
Here, `firstname` and `lastname` are placeholders that should be replaced with the actual values of the first name and last name provided as input.

### Constraints:
- The length of both the first name and last name is less than or equal to 10.

### Input:
- First line: A string representing the first name.
- Second line: A string representing the last name.

### Output:
- A single line with the following formatted text: `Hello firstname lastname! You just delved into python.`

---

### Complete Code:
```python
def print_full_name(first, last):
    # Write your code here
    print(f"Hello {first} {last}! You just delved into python.")

if __name__ == '__main__':
    first_name = input()  # Read the first name from input
    last_name = input()   # Read the last name from input
    print_full_name(first_name, last_name)
```

---

### Code Explanation:

1. **Function Definition:**
   ```python
   def print_full_name(first, last):
   ```
   - This defines a function named `print_full_name` that takes two parameters:
     - `first`: A string representing the first name.
     - `last`: A string representing the last name.

2. **Printing the Message:**
   ```python
   print(f"Hello {first} {last}! You just delved into python.")
   ```
   - Inside the function, we use an **f-string** (formatted string literal), which allows us to embed expressions inside string literals using curly braces `{}`.
   - The `{first}` placeholder is replaced with the value of the `first` parameter, and `{last}` is replaced with the value of the `last` parameter.
   - This generates the formatted output: `"Hello firstname lastname! You just delved into python."`.

3. **Main Section (`if __name__ == '__main__'):** 
   ```python
   if __name__ == '__main__':
   ```
   - This block ensures that the code inside it runs only when the script is executed directly (not when imported as a module into another Python program).

4. **Input Handling:**
   ```python
   first_name = input()
   last_name = input()
   ```
   - The `input()` function reads a string from the user. Here, it takes two inputs:
     - `first_name`: The first name of the user.
     - `last_name`: The last name of the user.

5. **Calling the Function:**
   ```python
   print_full_name(first_name, last_name)
   ```
   - The `print_full_name` function is called with the input values (`first_name` and `last_name`) passed as arguments.
   - This results in printing the formatted greeting message.

---

## Example:

#### Input:
```
John
Doe
```

### Execution:
- The `first_name` is `"John"`, and the `last_name` is `"Doe"`.
- The function `print_full_name("John", "Doe")` is called.
- Inside the function, the message `Hello John Doe! You just delved into python.` is printed.

### Output:
```
Hello John Doe! You just delved into python.
```

---
