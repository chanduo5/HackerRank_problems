# Problem Statement
You are given a string and a substring. Your task is to determine how many times the substring occurs in the string. String traversal will take place from left to right, and the matching is case-sensitive.

### Input Format:
1. The first line contains the main string.
2. The second line contains the substring.

### Constraints:
- 1 ≤ length of the main string ≤ 200
- Characters are ASCII, and the matching is case-sensitive.

#### Output:
An integer that represents the total number of occurrences of the substring in the main string.

#### Sample Input:
```
ABCDCDC
CDC
```

#### Sample Output:
```
2
```

---

# Explanation of the Code:

#### Completed Code:
```python
def count_substring(string, sub_string):
    count = 0
    for i in range(len(string) - len(sub_string) + 1):  # Iterate through the string
        if string[i:i+len(sub_string)] == sub_string:  # Check substring in sliced part
            count += 1  # Increment count for each match
    return count

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
```

---

#### Explanation in Detail:

1. **Function Definition:**
   - `count_substring(string, sub_string)`: This function calculates the number of times `sub_string` appears in `string`.

2. **Loop Logic:**
   - `for i in range(len(string) - len(sub_string) + 1)`:
     - We use the `range()` function to loop through the string. The upper limit ensures we don't exceed the bounds of the main string when slicing it for comparisons.
     - Example: If the string has 7 characters (`ABCDCDC`) and the substring has 3 characters (`CDC`), the loop will iterate from index 0 to 4 (inclusive).

3. **String Slicing:**
   - `string[i:i+len(sub_string)]`:
     - This extracts a slice of the string of the same length as `sub_string`.
     - For instance, when `i = 2`, this will extract the substring `CDC` from `ABCDCDC`.

4. **Condition Checking:**
   - `if string[i:i+len(sub_string)] == sub_string`:
     - This checks if the current slice of the string matches the `sub_string`.

5. **Counter Update:**
   - `count += 1`: The counter is incremented by 1 every time a match is found.

6. **Return Statement:**
   - The function returns the total count of occurrences of the `sub_string` in the `string`.

7. **Main Program:**
   - It takes the input for the main string and the substring from the user.
   - Calls the `count_substring` function and prints the result.

---

#### Example Walkthrough:
Let’s walk through the provided sample input:

- **Input:**
  - Main string: `ABCDCDC`
  - Substring: `CDC`

- **Loop Iterations:**
  - `i = 0`: Slice is `ABC` (No match).
  - `i = 1`: Slice is `BCD` (No match).
  - `i = 2`: Slice is `CDC` (Match! Increment count to 1).
  - `i = 3`: Slice is `DCD` (No match).
  - `i = 4`: Slice is `CDC` (Match! Increment count to 2).

- **Output:**
  - Total matches = 2

---

This approach ensures an efficient way to find overlapping substrings. If you have further questions or need enhancements to the code, let me know! 😊
