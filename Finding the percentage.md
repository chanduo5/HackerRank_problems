## Problem Description

You are given a dictionary containing key/value pairs where the keys are student names and the values are arrays of marks obtained by each student. You need to read this dictionary from input and print the average of the marks array for the student name provided, formatted to two decimal places.

### Input Format

1. The first line contains the integer `n`, the number of student records.
2. The next `n` lines contain the names and marks obtained by a student, each value separated by a space.
3. The final line contains `query_name`, the name of a student to query.

### Example

Consider the following input:
```
2
alpha 20 30 40
beta 30 50 70
beta
```

The input specifies:
1. `n = 2`: There are two students.
2. Student `alpha` has marks `[20, 30, 40]`.
3. Student `beta` has marks `[30, 50, 70]`.
4. We need to find the average marks for the student named `beta`.

The average score for `beta` is calculated as follows:
```
(30 + 50 + 70) / 3 = 50.00
```
Therefore, the output should be `50.00`.

### Code Solution

Here is the complete code to solve the problem:

```python
if __name__ == '__main__':
    # Read the number of student records
    n = int(input())
    
    # Initialize an empty dictionary to store student marks
    student_marks = {}
    
    # Read the student names and their respective marks
    for _ in range(n):
        name, *line = input().split()
        # Convert marks from strings to floats
        scores = list(map(float, line))
        # Store the marks in the dictionary with student name as the key
        student_marks[name] = scores
    
    # Read the query student name
    query_name = input()
    
    # Check if the query_name is in the dictionary
    if query_name in student_marks:
        # Calculate the average marks for the queried student
        average_marks = sum(student_marks[query_name]) / len(student_marks[query_name])
        # Print the average marks, formatted to 2 decimal places
        print(f"{average_marks:.2f}")
```

This code performs the following steps:

1. Reads the number of student records.
2. Initializes a dictionary to store the student names and their corresponding marks.
3. Reads the input for each student, splits the input into the name and marks, converts the marks to floating-point numbers, and stores them in the dictionary.
4. Reads the query name.
5. Checks if the query name is in the dictionary.
6. Calculates the average of the marks for the queried student.
7. Prints the average marks, formatted to two decimal places.
