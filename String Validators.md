# Problem Statement:
Given a string `S`, determine the following:
1. Does `S` contain any alphanumeric characters?
2. Does `S` contain any alphabetical characters?
3. Does `S` contain any digits?
4. Does `S` contain any lowercase characters?
5. Does `S` contain any uppercase characters?

The input is a single line containing the string `S` (0 < len(S) < 1000). The program should output:
- A line with `True` or `False` indicating the presence of alphanumeric characters in `S`.
- A line with `True` or `False` indicating the presence of alphabetical characters in `S`.
- A line with `True` or `False` indicating the presence of digits in `S`.
- A line with `True` or `False` indicating the presence of lowercase characters in `S`.
- A line with `True` or `False` indicating the presence of uppercase characters in `S`.

---

## Code Explanation:
```python
if __name__ == '__main__':
    s = input()
    print(any(char.isalnum() for char in s))  # Checks for alphanumeric characters
    print(any(char.isalpha() for char in s))  # Checks for alphabetical characters
    print(any(char.isdigit() for char in s))  # Checks for digits
    print(any(char.islower() for char in s))  # Checks for lowercase characters
    print(any(char.isupper() for char in s))  # Checks for uppercase characters
```

## Detailed Explanation:
1. **`if __name__ == '__main__':`**  
   This line ensures that the code inside the block runs only when the script is executed directly and not when it is imported as a module in another script.

2. **`s = input()`**  
   This line takes a single line of input from the user, which is stored as the string `s`.

3. **`any(char.isalnum() for char in s)`**  
   - `isalnum()` is a string method that returns `True` if a character is alphanumeric (a-z, A-Z, or 0-9).
   - The `any()` function iterates over each character in the string `s` to check if at least one character satisfies the `isalnum()` condition. If found, it returns `True`; otherwise, `False`.

4. **`any(char.isalpha() for char in s)`**  
   - Similar to the above, `isalpha()` checks if a character is an alphabet (a-z or A-Z).
   - The `any()` function ensures that if at least one character in `s` is an alphabet, it returns `True`.

5. **`any(char.isdigit() for char in s)`**  
   - `isdigit()` checks if a character is a digit (0-9).
   - `any()` iterates through `s` to find any numeric digit and returns `True` if found.

6. **`any(char.islower() for char in s)`**  
   - `islower()` checks if a character is a lowercase letter (a-z).
   - The `any()` function looks for at least one lowercase character and returns `True` if present.

7. **`any(char.isupper() for char in s)`**  
   - `isupper()` checks if a character is an uppercase letter (A-Z).
   - The `any()` function verifies the existence of any uppercase character and returns `True` if one exists.

## Sample Input:
```
aBc123#
```

## Output:
```
True
True
True
True
True
```

## Explanation of Output:
- **Alphanumeric Characters**: `aBc123#` contains `a`, `B`, `c`, `1`, `2`, and `3`, so it returns `True`.
- **Alphabetical Characters**: `aBc123#` contains `a`, `B`, and `c`, so it returns `True`.
- **Digits**: `aBc123#` contains `1`, `2`, and `3`, so it returns `True`.
- **Lowercase Characters**: `aBc123#` contains `a` and `c`, so it returns `True`.
- **Uppercase Characters**: `aBc123#` contains `B`, so it returns `True`.
