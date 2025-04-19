### Problem
Given an integer array `nums` where every element appears twice except for one. Find that single one. You must implement a solution with a linear runtime complexity and use only constant extra space


-----------------
### Solution
You can use the XOR operator to solve this problem. XOR of all elements gives us the number with a single occurrence. Here’s how it works:
- XOR of a number with itself is 0.
- XOR of a number with 0 is the number itself.
- XOR is commutative and associative, so the order of operations doesn’t matter.

### Code
```python


  def singleNumber(nums):
    result = 0
    for num in nums:
        result ^= num
    return result

# Example usage
nums = [2, 2, 1]
print(f"The single number is: {singleNumber(nums)}")
```
-------------------
### Explanation
- Initialize `result` to 0.
- Iterate through each number in the list `nums`.
- XOR each number with `result`.
- At the end of the iteration, `result` will hold the single number that appears once.

This solution has linear runtime complexity \( O(n) \) and uses constant extra space \( O(1) \).