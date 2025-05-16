

---

# ✅ Problem Statement: **"Distinct Country Stamps"**

Your friend **Rupal** has a collection of **country stamps**. Some of the stamps might come from the same country, and she wants to know **how many different countries** her stamps are from.

### You are given:

* A number `N` — the total number of stamps in the collection.
* Then `N` lines follow, each containing the **name of a country**.

### Your task:

Help Rupal **count the total number of **distinct** countries** represented in her collection.

---

## ✅ Input Format

```
Line 1: Integer N (number of stamps)
Next N lines: Each line contains the name of a country.
```

---

### ✅ Constraints

```
0 < N < 1000
```

---

### ✅ Output Format

```
Print the total number of distinct country stamps.
```

---

### ✅ Sample Input

```
7
UK
China
USA
France
New Zealand
UK
France
```

---

### ✅ Sample Output

```
5
```

### ✅ Explanation:

Although Rupal has **7** stamps, some of them are from the same country (`UK`, `France` appear twice).

The distinct countries are:

* UK
* China
* USA
* France
* New Zealand

So, the answer is **5**.

---

# ✅ Python Code

```python
# Step 1: Read the number of stamps
n = int(input())

# Step 2: Create an empty set to store country names
country_stamps = set()

# Step 3: Iterate through the N country names
for _ in range(n):
    country = input().strip()  # Read and strip any extra spaces
    country_stamps.add(country)  # Add the country to the set

# Step 4: Output the number of distinct countries
print(len(country_stamps))
```

---

## ✅ Detailed Explanation of Each Line

```python
n = int(input())
```

* Reads the number of country stamps (how many lines to expect).
* Converts it from string to integer.

```python
country_stamps = set()
```

* Creates an **empty set** to store unique country names.
* Sets **automatically eliminate duplicates**.

```python
for _ in range(n):
    country = input().strip()
    country_stamps.add(country)
```

* Loops `n` times to read each country name.
* `.strip()` removes any leading/trailing spaces.
* `.add()` inserts the country name into the set:

  * If it’s a new country, it’s added.
  * If it’s already in the set, it’s ignored (duplicates are removed automatically).

```python
print(len(country_stamps))
```

* Finally, `len()` returns the number of unique entries in the set.
* That’s your answer — the total number of distinct country stamps.

---

## ✅ Why Use a Set?

* Sets are perfect when you want to **remove duplicates**.
* Inserting an element into a set is very fast (average time complexity: **O(1)**).
* You don’t need to manually check if a country already exists.

---

## ✅ Alternate Thoughts

You could also solve this using a `list` and checking for duplicates manually — but it would be slower and more code. Using a `set` is clean, simple, and efficient.

---

Would you like this logic wrapped into a function or modified to read from a file for larger inputs?
