### Problem Statement
You are tasked with performing several operations on a list. You are given an integer `N`, which represents the number of commands to process. For each command, you will perform a specific operation on the list. The possible commands are:
1. **insert i e**: Insert integer `e` at position `i`.
2. **print**: Print the list.
3. **remove e**: Remove the first occurrence of integer `e`.
4. **append e**: Append integer `e` at the end of the list.
5. **sort**: Sort the list in ascending order.
6. **pop**: Remove the last element from the list.
7. **reverse**: Reverse the list.

The task is to process all the commands in order and perform the specified operations on the list.

---

### Code

Here is the Python code:

```python
if __name__ == '__main__':
    N = int(input())
    arr = []

    for _ in range(N):
        command = input().split()
        operation = command[0]

        if operation == "insert":
            index = int(command[1])
            element = int(command[2])
            arr.insert(index, element)
        elif operation == "print":
            print(arr)
        elif operation == "remove":
            element = int(command[1])
            arr.remove(element)
        elif operation == "append":
            element = int(command[1])
            arr.append(element)
        elif operation == "sort":
            arr.sort()
        elif operation == "pop":
            arr.pop()
        elif operation == "reverse":
            arr.reverse()
```

---

### Explanation of the Code

1. **Input Handling**:
   - First, the code reads `N`, which indicates the number of commands to process.
   - An empty list `arr` is initialized to perform operations on it.

2. **Command Processing**:
   - Each command is read as input and split into a list using `split()`. The first part (`operation`) specifies the type of operation, and the subsequent parts provide arguments (if any).

3. **Command Execution**:
   - **`insert i e`**: Inserts the integer `e` at the specified index `i` using the `insert()` method.
   - **`print`**: Prints the current state of the list.
   - **`remove e`**: Removes the first occurrence of the integer `e` using the `remove()` method.
   - **`append e`**: Adds the integer `e` to the end of the list using the `append()` method.
   - **`sort`**: Sorts the list in ascending order using the `sort()` method.
   - **`pop`**: Removes the last element of the list using the `pop()` method.
   - **`reverse`**: Reverses the list using the `reverse()` method.

4. **Iterating Through Commands**:
   - The loop runs `N` times, processing each command in the sequence provided.

---

### Example Execution

#### Input:
```
4
append 1
append 2
insert 1 3
print
```

#### Execution:
1. **`append 1`**: Adds `1` to the list → `arr = [1]`.
2. **`append 2`**: Adds `2` to the list → `arr = [1, 2]`.
3. **`insert 1 3`**: Inserts `3` at index `1` → `arr = [1, 3, 2]`.
4. **`print`**: Prints the list → `[1, 3, 2]`.

---

Let me know if you'd like further explanations or enhancements to the solution! 🚀
