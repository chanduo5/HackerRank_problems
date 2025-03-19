
---

## **Problem Statement**
You are tasked to write a Python function called `print_formatted`, which formats and prints the following representations for each integer \( i \) from \( 1 \) to \( n \):

1. **Decimal Representation** (base 10)
2. **Octal Representation** (base 8)
3. **Hexadecimal Representation** (base 16, capitalized)
4. **Binary Representation** (base 2)

For all representations, ensure that:
- They are **right-aligned** based on the width of the binary value of the largest number (\( n \)).
- All the values (Decimal, Octal, Hexadecimal, and Binary) are separated by a single space on the same line.

### **Input Format:**
A single integer \( n \), where:
\[
1 \leq n \leq 99
\]

### **Output Format:**
For each number from \( 1 \) to \( n \), print its decimal, octal, hexadecimal, and binary representations as a single line. Ensure consistent alignment by padding each value to match the width of the binary representation of \( n \).

---

# **Code**
Here's the complete solution in Python:

```python
def print_formatted(number):
    # Calculate the width of the binary representation of the largest number
    width = len(bin(number)[2:])
    
    # Loop through each number from 1 to number (inclusive)
    for i in range(1, number + 1):
        # Format and print decimal, octal, hexadecimal, and binary values
        print(f"{str(i).rjust(width)} {oct(i)[2:].rjust(width)} {hex(i)[2:].upper().rjust(width)} {bin(i)[2:].rjust(width)}")

if __name__ == '__main__':
    n = int(input("Enter a number: "))
    print_formatted(n)
```

---

### **Detailed Code Explanation**
1. **Determine Binary Width**:
   ```python
   width = len(bin(number)[2:])
   ```
   - `bin(number)` returns the binary representation of the integer `number`, prefixed by `0b`.
   - `bin(number)[2:]` removes the `0b` prefix and gives just the binary digits.
   - `len(bin(number)[2:])` calculates the length of the binary representation, which determines the **maximum width** for alignment purposes.

2. **Iterate Through Numbers**:
   ```python
   for i in range(1, number + 1):
   ```
   - Loop through integers from \( 1 \) to \( n \) (inclusive).

3. **Format Each Representation**:
   ```python
   str(i).rjust(width)
   ```
   - `str(i)` converts the number to a string (for decimal).
   - `.rjust(width)` right-aligns the string to the specified `width` by adding spaces to the left if necessary.

   Similarly:
   - `oct(i)[2:]` removes the `0o` prefix of octal numbers.
   - `hex(i)[2:].upper()` converts the hexadecimal representation to uppercase and removes the `0x` prefix.
   - `bin(i)[2:]` removes the `0b` prefix of binary numbers.

4. **Print All Representations in One Line**:
   ```python
   print(f"{str(i).rjust(width)} {oct(i)[2:].rjust(width)} {hex(i)[2:].upper().rjust(width)} {bin(i)[2:].rjust(width)}")
   ```
   - Each representation is right-aligned to match the calculated `width`.
   - Values are separated by a single space using the formatted string (f-string).

5. **Main Functionality**:
   ```python
   if __name__ == '__main__':
       n = int(input("Enter a number: "))
       print_formatted(n)
   ```
   - When the script is executed directly, it takes an integer input, \( n \), and calls `print_formatted` with it.

---

### **Example Output**

#### Input:
```
5
```

#### Output:
```
    1     1     1     1
    2     2     2    10
    3     3     3    11
    4     4     4   100
    5     5     5   101
```

### Explanation:
- For \( n = 5 \), the binary width of the largest number (5 in binary) is 3 (`101`).
- Each representation (Decimal, Octal, Hexadecimal, Binary) is aligned to the width of 3 spaces, ensuring a clean, organized output.

---

### **Takeaways**
This problem demonstrates how to:
- Work with multiple numeral systems in Python.
- Use Python string formatting for alignment and spacing.
- Efficiently handle inputs and outputs to create a polished user experience.
