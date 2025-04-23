-----------------------------------
### Problem Statement
You are given three integers \( x \), \( y \), and \( z \) representing the dimensions of a cuboid, along with an integer \( n \). Your task is to print a list of all possible coordinates \((i, j, k)\) on a 3D grid such that the sum of \( i + j + k \) is not equal to \( n \). The range of \( i \), \( j \), and \( k \) are defined as follows:
- 0
≤
𝑖
≤
𝑥

- 0
≤
𝑗
≤
𝑦

- 0
≤
𝑘
≤
𝑧

The coordinates should be printed in lexicographic increasing order.
-------------------------------------------------------------------------
### Example
Given the inputs:
```
x = 1
y = 1
z = 2
n = 3
```

We need to generate all the coordinates within the specified ranges. Then we filter out the coordinates where the sum \( i + j + k \) equals \( n \).

All permutations of \([i, j, k]\) are:
```
[[0, 0, 0], [0, 0, 1], [0, 0, 2], [0, 1, 0], [0, 1, 1], [0, 1, 2], 
 [1, 0, 0], [1, 0, 1], [1, 0, 2], [1, 1, 0], [1, 1, 1], [1, 1, 2]]
```

After filtering out the coordinates where the sum equals 3:
```
[[0, 0, 0], [0, 0, 1], [0, 0, 2], [0, 1, 0], [0, 1, 1], 
 [1, 0, 0], [1, 0, 1], [1, 1, 0], [1, 1, 2]]
```

### Detailed Explanation of the Code
Here’s the code:
```python
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())

    # List comprehension to generate the coordinates
    result = [[i, j, k] for i in range(x + 1) for j in range(y + 1) for k in range(z + 1) if i + j + k != n]

    print(result)
```

Let's break it down:

1. **Input Reading**
    ```python
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())
    ```
    The code reads four integers from the user input which represent the dimensions \( x \), \( y \), and \( z \), as well as the integer \( n \).

2. **List Comprehension**
    ```python
    result = [[i, j, k] for i in range(x + 1) for j in range(y + 1) for k in range(z + 1) if i + j + k != n]
    ```
    This line generates all possible coordinates \((i, j, k)\) within the specified ranges using nested list comprehensions. The `if` clause filters out the coordinates where \( i + j + k \) equals \( n \).

    Here's a more detailed breakdown of the list comprehension:
    - `for i in range(x + 1)`: Iterates over all possible values of \( i \) from 0 to \( x \).
    - `for j in range(y + 1)`: Iterates over all possible values of \( j \) from 0 to \( y \).
    - `for k in range(z + 1)`: Iterates over all possible values of \( k \) from 0 to \( z \).
    - `if i + j + k != n`: Includes only those coordinates where the sum \( i + j + k \) is not equal to \( n \).

3. **Printing the Result**
    ```python
    print(result)
    ```
    The final line prints the resulting list of coordinates.

