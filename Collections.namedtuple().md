# Problem Statement:
Dr. John Wesley has a spreadsheet containing details of students, including their IDs, marks, class, and names. Your task is to help Dr. Wesley calculate the **average marks** of the students. The spreadsheet columns can appear in any order and are labeled as `ID`, `MARKS`, `CLASS`, and `NAME`. The column names are consistent but their order may vary. You need to write a Python program to calculate and output the average marks, rounded to two decimal places.

---

### Code:

```python
from collections import namedtuple

# Input the number of students
N = int(input())

# Input the column names
columns = input().split()

# Create a namedtuple with the column names
Student = namedtuple('Student', columns)

# Initialize the total marks
total_marks = 0

# Loop through each student's data
for _ in range(N):
    data = input().split()
    student = Student(*data)
    total_marks += int(student.MARKS)

# Calculate the average and print the result rounded to 2 decimal places
average_marks = total_marks / N
print(f"{average_marks:.2f}")
```

---

### Code Explanation:

#### **1. `from collections import namedtuple`**
This imports the `namedtuple` feature from Python's `collections` module. A `namedtuple` allows creating tuple-like objects with named fields, making the code more readable.

#### **2. `N = int(input())`**
Reads the number of students from the input and stores it in `N`.

#### **3. `columns = input().split()`**
Reads the names of the spreadsheet columns. These could be in any order (e.g., `ID MARKS CLASS NAME`). The `.split()` function splits the input string into a list of column names.

#### **4. `Student = namedtuple('Student', columns)`**
Creates a `namedtuple` class called `Student`. The field names of this tuple are dynamically set based on the column names provided in the input. For example, if the input column names are `ID MARKS CLASS NAME`, the `Student` tuple will have the fields: `ID`, `MARKS`, `CLASS`, and `NAME`.

#### **5. `total_marks = 0`**
Initializes a variable to store the total marks of all students.

#### **6. Loop:**
```python
for _ in range(N):
    data = input().split()
    student = Student(*data)
    total_marks += int(student.MARKS)
```
- The loop runs `N` times, once for each student's data.
- Each line of student data is read as a string (e.g., `"1 85 A John"`), split into a list (e.g., `['1', '85', 'A', 'John']`), and passed to the `Student` namedtuple.
- The field `MARKS` is accessed using `student.MARKS` and converted to an integer before adding it to `total_marks`.

#### **7. Calculate Average:**
```python
average_marks = total_marks / N
```
The average is computed by dividing `total_marks` by the number of students `N`.

#### **8. Print Result:**
```python
print(f"{average_marks:.2f}")
```
The result is printed, rounded to two decimal places using Python's formatted string feature (`f"{:.2f}"`).

---

### Example:

#### Input:
```
3
ID MARKS NAME CLASS
1 85 John A
2 90 Jane B
3 78 Doe C
```

#### Execution:
1. Number of students: `3`.
2. Columns: `ID MARKS NAME CLASS`.
3. Read student data:
   - Student 1: Marks = 85
   - Student 2: Marks = 90
   - Student 3: Marks = 78
4. Total marks = `85 + 90 + 78 = 253`.
5. Average marks = `253 / 3 = 84.33`.

#### Output:
```
84.33
```

---

This program adapts flexibly to varying column orders while ensuring clarity through the use of `namedtuple`. Would you like help testing or customizing the code further? 😊
