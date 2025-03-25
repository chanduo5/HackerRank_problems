# Problem Statement:
Raghu owns a shoe shop with `X` shoes in inventory. He maintains a list of shoe sizes available. `N` customers arrive, each requesting a specific shoe size and offering a price for it. If Raghu has the requested shoe size in inventory, he sells it to the customer for the offered price and removes that size from his inventory. If the requested size is not available, Raghu cannot complete the sale. Your task is to calculate the total earnings Raghu makes after serving all customers.

### Code:
Below is the Python code with explanations for each part:

```python
from collections import Counter  # Importing the Counter class from the collections module.

# Step 1: Input the number of shoes
X = int(input("Enter the number of shoes available in the shop: "))  

# Step 2: Input the list of shoe sizes in the shop
shoe_sizes = list(map(int, input("Enter the shoe sizes (space-separated): ").split()))

# Step 3: Create a Counter object to manage the inventory
shoe_inventory = Counter(shoe_sizes)  # Counts occurrences of each shoe size.

# Step 4: Input the number of customers
N = int(input("Enter the number of customers: "))

# Step 5: Initialize a variable to track total earnings
earnings = 0

# Step 6: Process each customer's request
for _ in range(N):
    # Step 6.1: Input the desired shoe size and offered price
    size, price = map(int, input("Enter the desired shoe size and offered price: ").split())

    # Step 6.2: Check if the desired size is available in inventory
    if shoe_inventory[size] > 0:  # If size is available
        earnings += price  # Add the offered price to earnings
        shoe_inventory[size] -= 1  # Reduce the count for that shoe size in inventory

# Step 7: Print the total earnings
print("Total Earnings:", earnings)
```

### Explanation of Code:
#### **Imports**:
- `Counter` from the `collections` module: Used to track the count of each shoe size efficiently.

#### **Inputs**:
1. **Number of Shoes (`X`)**: Total number of shoes in the shop.
2. **Shoe Sizes List**: List of all shoe sizes available in the shop. We convert the input string to a list of integers using `map(int, input().split())`.
3. **Number of Customers (`N`)**: Number of customers arriving at the shop.

#### **Inventory Management**:
- The `Counter` object `shoe_inventory` is initialized with the list of shoe sizes. This creates a dictionary-like object where:
  - Keys are shoe sizes.
  - Values are the counts of each size.

#### **Processing Customer Requests**:
- For each customer, their desired shoe size and the price they offer are collected.
- The program checks if the desired shoe size exists in the inventory (`if shoe_inventory[size] > 0`).
  - If available:
    - Adds the offered price to the `earnings` total.
    - Updates the `shoe_inventory` by decrementing the count for the sold shoe size.
  - If not available:
    - The transaction cannot proceed.

#### **Output**:
- The total earnings after serving all customers are printed.

This step-by-step code ensures efficiency and accuracy when managing inventory and calculating earnings. Let me know if you'd like further assistance with testing or debugging!
