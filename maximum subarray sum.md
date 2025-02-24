### Problem

Write a function `max_subarray_sum` that takes a list of integers and returns the sum of the maximum subarray. A subarray is a contiguous part of an array. 

### Example
```python


# Example usage
nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
print(f"The maximum subarray sum is: {max_subarray_sum(nums)}")
# Output: 6
```
**Explanation:** The subarray `[4, -1, 2, 1]` has the largest sum = 6.

### Constraints
- The function should handle lists of varying lengths, including very large lists efficiently.
- You can assume that the input list will contain at least one number.

### Solution
You can solve this problem using Kadane's Algorithm, which operates in linear time.

### Code
```python
def max_subarray_sum(nums):
    max_current = max_global = nums[0]
    
    for num in nums[1:]:
        max_current = max(num, max_current + num)
        if max_current > max_global:
            max_global = max_current
            
    return max_global
```

### Explanation
1. Initialize `max_current` and `max_global` to the first element of the list.
2. Iterate through the list starting from the second element.
3. Update `max_current` to the maximum of the current number and the sum of `max_current` and the current number.
4. If `max_current` is greater than `max_global`, update `max_global`.
5. At the end of the iteration, `max_global` holds the sum of the maximum subarray.

Feel free to test this code with different input lists to verify its correctness!