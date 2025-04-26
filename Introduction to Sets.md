

# Problem Statement:
**Distinct Heights Average Calculation**  
Ms. Gabriel Williams, a botany professor, wants to analyze the heights of plants in her greenhouse. She asks her student, Mickey, to compute the **average height of all distinct plants**. Duplicate heights should not be considered in the average calculation, as each unique height is counted only once.

## Formula:
The average height is calculated as:
\[
\text{Average} = \frac{\text{Sum of Distinct Heights}}{\text{Number of Distinct Heights}}
\]

### Input:
- The first line contains \( N \), the number of elements in the array (natural number, \( 0 < N \leq 100 \)).
- The second line contains \( N \) space-separated integers representing plant heights.

### Output:
- A single floating-point number representing the average of distinct plant heights, rounded to 3 decimal places.

### Constraints:
- The array elements are integers \( 1 \leq \text{height} \leq 100 \).

---

# Code Explanation:

Below is the Python code with a detailed walkthrough:

```python
def average(array):
    # Convert the array to a set to remove duplicates
    distinct_elements = set(array)
    # Calculate the average of distinct elements
    avg = sum(distinct_elements) / len(distinct_elements)
    # Return the result
    return avg

if __name__ == '__main__':
    n = int(input())  # Input number of elements in the array
    arr = list(map(int, input().split()))  # Input the array elements
    result = average(arr)  # Call the function to calculate the average
    print(f"{result:.3f}")  # Print the result rounded to 3 decimal places
```

---

### Detailed Explanation:

1. **Understanding the Function**:
   - The `average` function takes an array of integers as input.
   - Inside the function, the `set()` method is used to eliminate duplicate elements from the array, leaving only unique values.
   - The `sum()` function calculates the sum of these distinct values.
   - The `len()` function determines the number of distinct elements.
   - The average is computed as the sum divided by the count of distinct values.

2. **Main Program Execution**:
   - The `__name__ == '__main__'` ensures the program's entry point is clear.
   - `n` is the number of elements in the input array (not directly used in computation but ensures correct input format).
   - `arr` is the list of integers (heights) provided as input.
   - The result is formatted using `f"{result:.3f}"` to round the output to 3 decimal places.

3. **Key Methods**:
   - `set()`: Removes duplicate entries from the input list.
   - `sum()` and `len()`: Used to compute the sum and count of unique heights, respectively.
   - `round()`: Used indirectly for formatting output to 3 decimal places.

---

### Example:

#### Input:
```
7
3 5 7 7 9 3 1
```

#### Process:
1. Original array: \([3, 5, 7, 7, 9, 3, 1]\)
2. Convert to set (distinct heights): \(\{3, 5, 7, 9, 1\}\)
3. Sum of distinct heights: \(3 + 5 + 7 + 9 + 1 = 25\)
4. Number of distinct heights: \(5\)
5. Average: \(\frac{25}{5} = 5.0\)

#### Output:
```
5.000
```

---

### Edge Case Examples:
1. **All Duplicate Heights:**
   - Input:
     ```
     5
     4 4 4 4 4
     ```
   - Process:
     - Distinct heights: \(\{4\}\)
     - Average: \(4\)
   - Output:
     ```
     4.000
     ```

2. **Single Plant Height:**
   - Input:
     ```
     1
     7
     ```
   - Process:
     - Distinct heights: \(\{7\}\)
     - Average: \(7\)
   - Output:
     ```
     7.000
     ```

3. **Maximum Heights with No Duplicates:**
   - Input:
     ```
     5
     100 99 98 97 96
     ```
   - Process:
     - Distinct heights: \(\{100, 99, 98, 97, 96\}\)
     - Sum: \(490\)
     - Average: \(98.0\)
   - Output:
     ```
     98.000
     ```

This explanation ensures all aspects of the problem and the code are understood. Let me know if you'd like further clarification or assistance!
