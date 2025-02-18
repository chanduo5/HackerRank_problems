# Problem #

The task is to read an integer n from standard input. For all non-negative integers i less than n, print the square of each number on a separate line.

## Solution ##

To solve this problem, we need to:

- Read an integer n from standard input.

- Loop through all non-negative integers i such that i is less than n.

- Print the square of each integer i during each iteration of the loop.

Here's the detailed explanation along with the code:
python

    if __name__ == '__main__':
         n = int(input())  # Read an integer 'n' from standard input
         for i in range(n):  # Loop through non-negative integers less than 'n'
         print(i * i)  # Print the square of each integer 'i'
## Explanation ##

- Reading the Input:

  n = int(input()): This line reads an integer from standard input. The input()
  function reads a line of text from the user, and int() converts that text to an
  integer. This integer is stored in the variable n.

- Looping through Non-negative Integers:

  for i in range(n): This line initiates a for loop that will iterate over a range of
  integers starting from 0 up to, but not including, n. The range(n) function
  generates a sequence of numbers from 0 to n-1.

- Printing the Square of Each Integer:

  print(i * i): This line calculates the square of the current integer i (i.e., i * i)
  and prints the result. The print() function outputs the result to the standard output.

## Example ##

Let's take an example to understand how the code works. If we input n = 3, the sequence of non-negative integers less than 3 is [0, 1, 2]. The code will print the square of each of these integers:

     0  # 0*0
     1  # 1*1
     4  # 2*2

So the output for n = 3 will be:

    0
    1
    4

This code effectively solves the problem by utilizing a loop to process each integer less than n and print its square.

