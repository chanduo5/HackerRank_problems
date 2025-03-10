
---

### **Problem Statement**
You are given a string, and your task is to modify it by swapping the case of each character:
- All lowercase letters should be converted to uppercase.
- All uppercase letters should be converted to lowercase.
Other characters, such as digits, punctuation, and spaces, should remain unchanged.

#### **Example Inputs and Outputs:**
1. Input: `"Www.HackerRank.com"`
   - Output: `"wWW.hACKERrANK.COM"`
2. Input: `"Pythonist 2"`
   - Output: `"pYTHONIST 2"`

---

### **Code Implementation**
Here is the Python implementation of the solution:

```python
def swap_case(s):
    return s.swapcase()

if __name__ == '__main__':
    s = input()
    result = swap_case(s)
    print(result)
```

---

### **Detailed Explanation of the Code**
#### **1. Function Definition**:
```python
def swap_case(s):
```
This line defines a function named `swap_case`. It takes one parameter `s`, which is expected to be a string.

#### **2. String Method: `.swapcase()`**
```python
return s.swapcase()
```
This uses Python's built-in string method `swapcase()` to process the input string:
- For every character in the string:
  - If it's lowercase, it is converted to uppercase.
  - If it's uppercase, it is converted to lowercase.
- The modified string is then returned as the output.

#### **3. Input Handling**:
```python
if __name__ == '__main__':
    s = input()
```
- This part of the code is the entry point when the script is run directly.
- It prompts the user to input a string `s` using the `input()` function.

#### **4. Calling the Function and Printing Output**:
```python
result = swap_case(s)
print(result)
```
- The function `swap_case(s)` is called with the user's input string, and the result is stored in the variable `result`.
- Finally, `result` is printed to the console.

---

### **How the Code Works with Examples**
1. **Example 1**:
   - Input: `"Www.HackerRank.com"`
   - `swap_case("Www.HackerRank.com")`:
     - `W` → `w`, `w` → `W`, `w` → `W`, `.` remains `.`, `H` → `h`, `a` → `A`, ..., `m` → `M`.
   - Output: `"wWW.hACKERrANK.COM"`

2. **Example 2**:
   - Input: `"Pythonist 2"`
   - `swap_case("Pythonist 2")`:
     - `P` → `p`, `y` → `Y`, `t` → `T`, ..., `2` remains `2`.
   - Output: `"pYTHONIST 2"`

---

### **Key Features of This Approach**
1. **Efficiency**:
   - The `swapcase()` method is highly optimized and processes strings in linear time, O(n), where `n` is the length of the string.
2. **Simplicity**:
   - Using Python's built-in string method keeps the code concise and readable.
3. **Handles Constraints**:
   - The solution works for strings with lengths up to 1000 characters, as specified in the problem.

---

Feel free to test the code with different inputs! Let me know if you'd like further clarification. 😊
