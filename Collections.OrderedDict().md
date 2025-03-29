Sure! Let me break this down into three main parts: the **problem statement**, the **code**, and a **detailed explanation of the code**.

---

### Problem Statement:
You are the manager of a supermarket. Each day, you keep track of the items sold and their prices. Sometimes, the same item is sold multiple times at the same or different prices. Your task is to calculate the total price of each item (net price) in the order they were first sold and display them.

#### Input:
1. The first line contains an integer **N** (number of items sold on that day).
2. The next **N** lines contain the name of the item and its price (separated by a space).

#### Output:
For each unique item, print the name of the item and its total price (net price) in the order of their first occurrence.

#### Constraints:
- \(0 < N \leq 100\)
- The item's name is a string, and the price is an integer.

#### Example:
Input:
```
6
apple 30
banana 10
apple 20
orange 40
banana 20
apple 10
```

Output:
```
apple 60
banana 30
orange 40
```

---

### Code:

```python
from collections import OrderedDict

# Create an OrderedDict to store item names and net prices
ordered_dict = OrderedDict()

# Take input for the number of items
N = int(input("Enter the number of items: "))

# Process each item
for _ in range(N):
    item = input("Enter item name and price (e.g., apple 30): ").rsplit(' ', 1)
    item_name = item[0]
    item_price = int(item[1])
    if item_name in ordered_dict:
        ordered_dict[item_name] += item_price
    else:
        ordered_dict[item_name] = item_price

# Print results in the order of first occurrence
for item_name, net_price in ordered_dict.items():
    print(item_name, net_price)
```

---

### Code Explanation:

1. **Importing `OrderedDict`:**
   - The `OrderedDict` class from the `collections` module is used to maintain the order of insertion. Unlike a regular dictionary (prior to Python 3.7), `OrderedDict` remembers the order in which items are added.

2. **Reading Input:**
   - The first line takes the integer input `N`, which specifies the number of items sold.
   - A `for` loop is used to process the next `N` lines, which contain the item name and price.

3. **Splitting the Input:**
   - `rsplit(' ', 1)` splits each input line into two parts: the item name and the price. The `1` ensures the split happens only at the last space, so item names with spaces are handled correctly.

4. **Adding to `OrderedDict`:**
   - If the item name already exists in the `OrderedDict`, its price is updated by adding the new price (net price calculation).
   - If the item name is not in the `OrderedDict`, it is added with its current price.

5. **Output Results:**
   - The final loop iterates through the `OrderedDict` and prints each item name along with its total (net) price in the order they were first inserted.

---

### How the Example Works:

#### Input:
```
6
apple 30
banana 10
apple 20
orange 40
banana 20
apple 10
```

#### Execution Steps:
- `OrderedDict` starts empty.
- `apple 30`: Add `apple` to the dictionary → `{'apple': 30}`
- `banana 10`: Add `banana` → `{'apple': 30, 'banana': 10}`
- `apple 20`: Update `apple` price → `{'apple': 50, 'banana': 10}`
- `orange 40`: Add `orange` → `{'apple': 50, 'banana': 10, 'orange': 40}`
- `banana 20`: Update `banana` price → `{'apple': 50, 'banana': 30, 'orange': 40}`
- `apple 10`: Update `apple` price → `{'apple': 60, 'banana': 30, 'orange': 40}`

#### Output:
```
apple 60
banana 30
orange 40
```

---

Let me know if you'd like further clarification or if you want me to modify the code for specific scenarios! 😊
