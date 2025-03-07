# Problem Statement
You are given the names and grades for a class of N students. Your task is to store these records in a nested list and print the names of any students having the second lowest grade. If there are multiple students with the second lowest grade, order their names alphabetically and print each name on a new line.

#### Example
Given the records:
```
records = [["chi", 20.0], ["beta", 50.0], ["alpha", 50.0]]
```
The ordered list of scores is [20.0, 50.0], so the second lowest score is 50.0. There are two students with that score: ["beta", "alpha"]. Ordered alphabetically, the names are printed as:
```
alpha
beta
```

#### Input Format
- The first line contains an integer, N, the number of students.
- The 2N subsequent lines describe each student over 2 lines:
  - The first line contains a student's name.
  - The second line contains their grade.

#### Constraints
- 2 <= N <= 5
- There will always be one or more students having the second lowest grade.

#### Output Format
Print the name(s) of any student(s) having the second lowest grade. If there are multiple students, order their names alphabetically and print each one on a new line.

### Detailed Description of the Code

```python
if __name__ == '__main__':
    records = []  # Initialize an empty list to store student records.
    for _ in range(int(input())):  # Read the number of students.
        name = input()  # Read the student's name.
        score = float(input())  # Read the student's grade.
        records.append([name, score])  # Append the student's name and grade as a sublist to the records list.
    
    # Extract all the grades and remove duplicates
    grades = sorted(set([score for name, score in records]))  # Create a sorted list of unique grades.
    
    # Get the second lowest grade
    second_lowest_grade = grades[1]  # Find the second lowest grade by accessing the second element of the sorted grades list.
    
    # Find the names of students with the second lowest grade
    second_lowest_students = sorted([name for name, score in records if score == second_lowest_grade])  # Create a list of names with the second lowest grade and sort it alphabetically.
    
    for student in second_lowest_students:  # Print each student's name on a new line.
        print(student)
```

### Explanation

1. **Input Reading**:
    - The code reads the number of students and initializes an empty list called `records` to store the student records.
    - It then reads each student's name and grade, and stores them as sublists within the `records` list.

2. **Extracting Grades**:
    - The code extracts all the unique grades from the records list and sorts them in ascending order.

3. **Finding the Second Lowest Grade**:
    - By accessing the second element of the sorted list of unique grades, the code finds the second lowest grade.

4. **Finding Students with the Second Lowest Grade**:
    - The code creates a list of names of students who have the second lowest grade and sorts this list alphabetically.

5. **Printing the Results**:
    - Finally, the code prints each name from the list of students with the second lowest grade on a new line.

