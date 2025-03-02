Of course! Let's break down the problem and the solution step by step.

### Problem Explanation
You are given a list of scores from a sports event. You need to find the runner-up score, which is the second-highest score in the list. 

### Input Details
- The first line of input contains `n`, the number of scores.
- The second line of input contains `n` integers, which are the scores separated by spaces.

### Constraints
- \( 2 \leq n \leq 10 \)
- \( -100 \leq A[i] \leq 100 \)

### Output
- You need to print the second-highest score (the runner-up score).

### Example
**Input:**
```
5
2 3 6 6 5
```

**Output:**
```
5
```

**Explanation:** The highest score is 6. The second-highest score (runner-up) is 5.

### Code Explanation

Here is the complete code along with an explanation:

```python
if __name__ == '__main__':
    n = int(input())  # Read the number of scores
    arr = list(map(int, input().split()))  # Read the scores and convert them into a list of integers
    
    # Remove duplicates by converting the list to a set and back to a list
    arr = list(set(arr))
    
    # Sort the list in descending order
    arr.sort(reverse=True)
    
    # The second element in the sorted list is the runner-up score
    runner_up_score = arr[1]
    
    # Print the runner-up score
    print(runner_up_score)
```

### Detailed Explanation

1. **Reading Input:**
   - `n = int(input())` reads the first line of input, which is the number of scores.
   - `arr = list(map(int, input().split()))` reads the second line of input, splits it into individual strings, maps them to integers, and converts them into a list.

2. **Removing Duplicates:**
   - `arr = list(set(arr))` converts the list to a set to remove any duplicate scores, and then converts it back to a list.

3. **Sorting:**
   - `arr.sort(reverse=True)` sorts the list in descending order so that the highest score is at the beginning of the list.

4. **Finding the Runner-Up Score:**
   - `runner_up_score = arr[1]` accesses the second element in the sorted list, which is the runner-up score.

5. **Printing the Runner-Up Score:**
   - `print(runner_up_score)` prints the runner-up score.

This code ensures that you get the correct runner-up score even if there are duplicate scores in the input. Feel free to run the code and let me know if you have any questions! 😊
