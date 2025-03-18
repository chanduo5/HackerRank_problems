# Problem Statement

You need to create a doormat pattern generator based on specific design requirements. Here's the problem:

1. **Input Specifications**:
   - The input consists of two space-separated integers `N` and `M`, where:
     - `N` is the height of the mat and must be an odd natural number.
     - `M` is the width of the mat and must be 3 times `N`.
   - Constraints:
     - `5 < N < 101`
     - `15 < M < 303`
   
2. **Design Specifications**:
   - The mat's dimensions are `N x M`.
   - The design uses the characters `.`, `|`, and `-`.
   - The word "WELCOME" is in the center of the mat.
   - The pattern forms a symmetrical design:
     - The top part increases in complexity (more `. | .` patterns).
     - The middle part displays the word "WELCOME".
     - The bottom part is a mirrored version of the top.

3. **Output**:
   - Print the design pattern based on the input dimensions.

---

## Explanation of the Code
Here’s a line-by-line breakdown of the updated code:

```python
# Input dimensions
N, M = map(int, input("Enter N and M separated by space: ").split())
```
- The user enters two numbers, `N` (height) and `M` (width). The `map` function converts these strings into integers.
- `split()` separates the input based on spaces.

```python
# Validate constraints
if N % 2 == 0 or M != 3 * N:
    print("Invalid input. Ensure that N is an odd number and M is 3 times N.")
```
- Ensures that:
  1. `N` is an odd number.
  2. `M` is exactly 3 times `N`.
- If either condition fails, the code prints an error message.

```python
else:
    # Generate the top half of the doormat
    for i in range(1, N, 2):
        pattern = ".|." * i
        print(pattern.center(M, "-"))
```
- **Top Half**:
  - Loops through odd numbers from `1` to `N-1` (incrementing by 2).
  - Generates the `. | .` pattern by repeating it `i` times.
  - Centers the pattern in the mat’s width (`M`) using the `-` character.

```python
    # Print the middle 'WELCOME' line
    print("WELCOME".center(M, "-"))
```
- **Middle Line**:
  - Centers the word "WELCOME" within the mat’s width, padded with `-`.

```python
    # Generate the bottom half of the doormat
    for i in range(N - 2, 0, -2):
        pattern = ".|." * i
        print(pattern.center(M, "-"))
```
- **Bottom Half**:
  - Loops through odd numbers in reverse order, from `N-2` down to `1` (decrementing by 2).
  - Generates the `. | .` pattern and centers it in the mat’s width.

---

## Sample Input/Output
### Input:
```
9 27
```

### Output:
```
------------.|.------------
---------.|..|..|.---------
------.|..|..|..|..|.------
---.|..|..|..|..|..|..|.---
----------WELCOME----------
---.|..|..|..|..|..|..|.---
------.|..|..|..|..|.------
---------.|..|..|.---------
------------.|.------------
```

---

### Key Points
- **Pattern Symmetry**: The top and bottom halves are mirror images, ensuring a visually balanced design.
- **Center Alignment**: Patterns and text are perfectly centered for consistent formatting.
- **Flexibility**: The code works for any valid `N` and `M` within the constraints.

