
---

## 🧾 Problem Statement: **Students and Newspaper Subscriptions**

### 🎯 Objective:

You are given two sets of student roll numbers:

* One set contains students who have subscribed to the **English** newspaper.
* The other set contains students who have subscribed to the **French** newspaper.

Some students might have subscribed to **both newspapers**, and therefore appear in **both sets**.

**Your task:**
Determine how many **unique** students have subscribed to **at least one** newspaper.

---

## 🔡 Input Format:

1. First line: An integer `n`, the number of students subscribed to the English newspaper.
2. Second line: `n` space-separated integers – the roll numbers of those students.
3. Third line: An integer `b`, the number of students subscribed to the French newspaper.
4. Fourth line: `b` space-separated integers – the roll numbers of those students.

---

## ✅ Constraints:

* All roll numbers are **distinct within a set**.
* `0 < Total number of students < 1000`

---

## 📤 Output Format:

* Print a single integer: the **total number of students** who have subscribed to **at least one** newspaper.

---

## 🧠 Understanding the Set `.union()` Operation

In Python, the `.union()` method (or `|` operator) combines two sets and returns a new set containing **all unique elements** from both sets.

For example:

```python
a = set([1, 2, 3])
b = set([3, 4, 5])

print(a.union(b))  # Output: {1, 2, 3, 4, 5}
print(len(a.union(b)))  # Output: 5
```

So, using `.union()` helps us determine how many **distinct students** are there in either English or French subscriptions (or both).

---

## 💻 Python Code:

```python
# Step 1: Read number of students who subscribed to English
n = int(input())

# Step 2: Read roll numbers of English newspaper subscribers
english_subs = set(map(int, input().split()))

# Step 3: Read number of students who subscribed to French
b = int(input())

# Step 4: Read roll numbers of French newspaper subscribers
french_subs = set(map(int, input().split()))

# Step 5: Take the union of both sets to get all unique subscribers
total_unique_subs = english_subs.union(french_subs)

# Step 6: Print the number of unique subscribers
print(len(total_unique_subs))
```

---

## 🧪 Example Test Case

### **Input:**

```
4
1 2 3 4
3
3 4 5
```

### **Step-by-Step Execution:**

* English subscribers: `{1, 2, 3, 4}`
* French subscribers: `{3, 4, 5}`
* Union of both sets: `{1, 2, 3, 4, 5}`
* Total unique students = `5`

### **Output:**

```
5
```

---

## 🧾 Summary

### 📌 Problem Goal:

Count how many **students** are subscribed to **at least one** newspaper (English or French).

### 🧰 Tools Used:

* Python `set`
* `.union()` method to merge sets without duplicates
* `len()` to count total elements in the resulting set

### 📈 What You Learn:

* Handling sets in Python
* Understanding how `.union()` works
* Basic input parsing and output formatting in Python

---

Would you like a version of this wrapped in a function for testing or automation purposes?
